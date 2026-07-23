---
title: Running the dashboard
weight: 2
description: "Running FRC Match Dashboard"
---

> [!IMPORTANT]
>
> Before running the dashboard, ensure that you have sourced the virtual environment and have installed the required dependencies

> [!WARNING]
>
> While the dashboard is able to be used with both Windows and Linux in a testing capacity, this project only contains the packages for a production deployment on Linux at this time.

## Running on Windows



### Running as a development server

Run from the root of the project:

```powershell
python app.py
```

## Running on Linux

### Running as a development server

```shell
# Run the development server
python app.py
```

### Running as a production server

```shell
# Run the production server
gunicorn -w 1 -b 0.0.0.0:5000 app:app
```

### Run under systemd with gunicorn

Create the service at the path `/etc/systemd/system/frc-dashboard.service`

```shell
[Unit]
Description=FRC Match Dashboard
After=network-online.target
Wants=network-online.target

[Service]
Type=simple
User=pi
WorkingDirectory=/home/pi/FRC-Match-dashboard
ExecStart=/home/pi/FRC-Match-dashboard/venv/bin/gunicorn -w 1 --timeout 120 -b 0.0.0.0:5000 app:app
Restart=always
RestartSec=3

[Install]
WantedBy=multi-user.target
```

Register the service:

```shell
sudo systemctl daemon-reload
sudo systemctl start frc-dashboard
sudo systemctl status frc-dashboard
```

Start the service:

```shell
sudo systemctl start frc-dashboard    # Start the service
sudo systemctl stop frc-dashboard     # Stop the service
```


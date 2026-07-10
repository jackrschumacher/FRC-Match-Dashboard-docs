---
title: Running the dashboard
weight: 2
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


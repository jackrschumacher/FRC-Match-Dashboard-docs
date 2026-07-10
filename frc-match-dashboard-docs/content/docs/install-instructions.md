---
title: Installation and Setup Instructions
weight: 1
---

## pip packages installation

To set up this project, you must install flask and the request package.

Follow the [flask python installation instructions](https://flask.palletsprojects.com/en/stable/installation/#python-version) for your specific operating system.

### Windows installation

#### Create the environment

```powershell
mkdir frc-match-dashboard
cd frc-match-dashboard
py -3 -m venv .venv
```

#### Activate the environment

```powershell
# Activate the enviroment
.venv\Scripts\activate
pip install -r requirements.txt
```



### Linux/MacOS installation

#### Create the environment

```shell
mkdir myproject   
cd myproject
python3 -m venv .venv
```

#### Activate the environment

```shell
# Activate the enviroment
. .venv/bin/activate
# Convert requirements.txt to UTF-8 encoding and install packages
iconv -f UTF-16 -t UTF-8 requirements.txt -o requirements.txt
pip install -r requirements.txt
```

## Using the TBA API

### Creating a TBA API Key

Follow the steps below to create a TBA Read API v3 key. To create a TBA API key, you must have a TBA account. 

1. Go to the 'More' menu on the TBA main page, and then go to 'Account'
2. Scroll down on the the 'Account' page until you reach the 'Read API Keys section'
3. Provide a description for the key, something like `frc-match-dashboard` would be sufficient. You have now created a TBA Read API key

### Adding your TBA API key to your .env file

To ensure that your TBA key is only known to you, 

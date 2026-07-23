---
title: Debugging
weight: 999
description: "FRC Dashboard Installation and Setup instructions"
---

## Python

{{< details title="Removing and Recreating the .venv" closed="true" >}}

Sometimes the virtual environment that contains the packages that run the app can encounter an issue. Use the commands below to recreate it. 

### Windows

```powershell
deactivate 2>$null; python -m venv .venv; .\.venv\Scripts\Activate.ps1; pip install -r requirements.txt
```





### Linux

```shell
deactivate 2>/dev/null; python3 -m venv .venv && source .venv/bin/activate && pip install -r requirements.txt
```



{{< /details >}}

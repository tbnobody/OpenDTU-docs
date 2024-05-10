# OpenDTU documentation

## Read the documentation

The published documentation can be found at [opendtu-onbattery.net](https://opendtu-onbattery.net/).

## Testing for professionals

Install the required dependencies:

```sh
python3 -m venv venv
source ./venv/bin/activate
pip3 install -r requirements.txt
```

Run a local webserver:

```sh
mkdocs serve
```

## Testing for beginners

Install Python3 Programming Language

Create a Virtual Environment:   
Open Any Terminal (cmd.exe), switch to the drive & subdirectory of your choice and run below command:
```sh
python -m venv venv
```
The above command will create a Virtual Environment in the subdirectory venv in the drive & subdirectory you have chosen.

Activate the Virtual Environment:
- For Linux Based OS Or Mac-OS: source venv/bin/activate
- For Windows With CMD: venv\Scripts\activate.bat
- For Windows With Power shell: .\venv\Scripts\activate.ps1
- For Windows With Unix Like Shells For Example Git Bash CLI: source venv/Scripts/activate

Download the OpenDTU-OnBattery-docs ZIP file and expamd it inside the venv directory.
Using the command editor (cmd.exe), switch to that directory and give the command:
```sh
pip3 install -r requirements.txt
```

Now it is time to clone the project to your local disk.
You need to install Git on your PC https://git-scm.com/downloads
Start Git and clone Repository to a subdirectory on your hard disk.

Using the command editor (cmd.exe), switch to that directory you saved the cloned repository and type the command:
```sh
mkdocs serve
```
Project settings are configured by default using a YAML configuration file in the project directory named mkdocs.yml. You can specify another path for it by using the -f/--config-file option (see mkdocs build --help).


```

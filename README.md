<h1>Starting a New VS Code Project with a Virtual Environment Using PowerShell
</h1>Note this guide assumes you have Git, VS Code, and the Python extension for VS Code installed
I'm working on embedding helpful images, but for now you an see them in the imgs folder in this repo.
<h3>Step 1
</h3>First you'll want to open a file, folder, or Git repo that you'll be working in.
<h3>Step 2
</h3>Once in your workspace, open the terminal (PowerShell by default) and run (or equivalent for your system)

```
py -m venv .venv_name
```

This will create a new venv in the root folder of the workspace.
<h3>Step 3
</h3>In the bottom right corner there will be a popup, I have been clicking yes to automatically select the newly recognized virtual environment for the current workspace.
<h3>Step 4
</h3>Start the virtual environment using

```
\venv_name\Scripts\Activate.ps1
```

**NOTE** if this does not work due to permissions issues, run

```
Set-ExecutionPolicy -ExecutionPolicy Unrestricted -Scope CurrentUser
```

first and then try to activate the venv again.
<h3>Step 5
</h3>Make sure in any Jupityr Notebooks and other places code is being executed that the kernal chosen is the one from the venv and NOT from your local machine.
Your terminal should be showing that it is running the venv.<br>
Thats it!<br><br>
For further reference I followed <a href="https://dev.to/aka_anoop/enabling-virtualenv-in-windows-powershell-ka3" target="_blank">this guide</a>.

- - -

<h1>Using Git with VS Code
</h1>I just followed <a href="https://www.youtube.com/watch?v=F2DBSH2VoHQ" target="_blank">this YouTube tutorial</a> to learn about it, I found it very thorough!
Basically on the left hand side of VS Code, third button down is **Source Control**, this is where you can create, connect to, push, pull etc to a git repo! This section also tracks all the file changes where they can be reverted, viewed, or commited.
<br>
<br>
Thats really it for git source control!

- - -

<h1>Geopandas Installation on Windows Fix
</h1>Due to pip not having the Fiona, GDAL, and other dependencies on Windows we must download and install them manually. I followed <a href="https://iotespresso.com/how-to-install-geopandas-on-windows/" target="_blank">this guide</a> myself if you'd like to check it out.<br><br>

The first thing to do is go to <a href="https://www.lfd.uci.edu/~gohlke/pythonlibs/" target="_blank">Christoph Gohlke</a>'s website of dependency binaries for Windows. On this website the binaries for your particular version of Python and your computers architecture (most computers nowadays are 64 bit).
For example:

```
PC: 64 bit
Python: v3.10
Download: Fiona-1.8.21-cp310-cp310-win\_amd64.whl
```

Once the desired package binaries are downloaded, install them starting with GDAL using

```
pip install file/location/GDAL-3.4.2-cp310-cp310-win\_amd64.whl
pip install file/location/Fiona-1.8.21-cp310-cp310-win\_amd64.whl
```

Geopandas should now install properly!

- - -

<br>
<br>

## Run the Python Script
    python3 hello.py

## To create a virtual environment
    python3 -m venv <directory>

## To activate a virtual environment
    source <directory>/bin/activate

## To display a list of all installed Python packages and their versions (ensure you are in the virtual environment)
    pip3 list

## To install a python tool locally, within your virtual environment (you need to be in the directory where the 'setup.py' or 'pyproject.toml' file is located)
    pip3 install .
    pip3 install <directory>

## To deactivate a virtual environment
    deactivate

## To install a specific package (ensure you are in the virtual environment)
    pip3 install -y <package_name>

## To install all the packages listed in the 'requirements.txt' (ensure you are in the virtual environment)
    pip3 install -r requirements.txt
    
## To uninstall a specific package (ensure you are in the virtual environment)
    pip3 uninstall -y <package_name>

## To install a Python package from a specified Git repository URL using pipx
    pipx install git+https://<repository-url>

## To install a Python package locally using pipx (you need to be in the directory where the 'pyproject.toml', 'setup.py', or 'setup.cfg' file is located)
    pipx install .
    pipx install <directory>

## To uninstall a Python package using pipx
    pipx uninstall <package_name>

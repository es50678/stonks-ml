Hobby Project to gain an understand TensorflowS

# Running as Docker container
Run `docker-compose up` in the project directory
- This will build an image from Dockerfile if one does not already exist and start the service
- This also sets a volume link between the local project directory and the project directory in the container
  - currently - this just means you don't have to restart the container for file changes to be propagated to the container
  - in the future - this will allow us to use some kind of hot reloading to restart the script automatically on changes

## What's in the image Dockerfile builds?
- a `tensorflow` distribution(from latest version)
- a `finnhub-python` distribution(from latest version)
- sets the default starting command to `python bootstrapper.py`
  - this is what all new containers will run when starting, unless told otherwise

## What is .python-version?
this is used by pyenv to lock the projects python version to a specific python version
- in this case stonks_ml is a virtual environment installed via `pyenv virtualenv 3.8.3 stonks_ml`
-- `pyenv virtualenv 3.8.3 stonks_ml` should be ran locally to ensure python versions are the same accross machines

## What is requirements.txt?
the equivalent of a package-json or gemfile - pip can use this to install dependencies
- pip install -r requirements.txt
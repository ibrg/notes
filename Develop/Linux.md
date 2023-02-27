## Setting up python, pipenv and jupyter notebook on Ubuntu
```
# Install pip and pipenv
sudo apt install python3-pip python3-dev
pip3 install --user pipenv

# Add pipenv (and other python scripts) to PATH
echo "PATH=$HOME/.local/bin:$PATH" >> ~/.bashrc
source ~/.bashrc
```

Create a new project and install some dependencies (include jupyter)
```
mkdir project-name && cd project-name
pipenv install numpy matplotlib jupyter
```

Start a jupyter notebook
```
pipenv run jupyter notebook
```

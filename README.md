# Practice

### Attach IDE (Visual Studio Code/Jupyter Notebook)
- Open Visual Studio IDE in Java devcontainer:
```
Install "Remote-Containers" extension: https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers
Install Lombok extension
rm -rf .devcontainer/
docker builder prune && docker image prune && docker container prune
Open Visual Studio Code --> F1 key --> Enter "Remote-Containers: Reopen in Container" 
mvn clean package
```

#### Setup Gemfire
```
mkdir -p gemfire
tar -xzvf /var/lib/pivotal-gemfire-9.10.15.tgz -C gemfire
PATH=$PATH:$JAVA_HOME/bin:gemfire/pivotal-gemfire-9.10.15/bin
export PATH
source gemfire/pivotal-gemfire-9.10.15/bin/gfsh-completion.bash
```

#### Notes:

- Sample "show metrics" command: 
```

```

- Deploy to Gemfire cluster:
```
mvn clean deploy
gfsh -e "connect" -e "deploy --jar=target/python-geode-function-1.0-SNAPSHOT.jar"
```

#### Install CPython 3
```
brew install pyenv (on Mac)
pyenv install 3.10.3
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bash_profile
echo 'export PATH="$PYENV_ROOT/shims:$PATH"' >> ~/.bash_profile
echo -e 'if command -v pyenv 1>/dev/null 2>&1; then\n  eval "$(pyenv init -)"\nfi' >> ~/.bash_profile
reset
pyenv global 3.10.3
pyenv versions
```

#### Generate JEP-compatible wrapper code for CPython scripts: Install JEP
Run
```
pip3 install -r requirements.txt
```
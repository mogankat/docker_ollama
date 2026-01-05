README.md


1. If you ain't got em: install em:
# homebrew
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# docker desktop
brew install --cask docker

2. Launch docker desktop and skip through the registration nonsense. 

3. Edit Settings >  Resources > Resource Allocation > Memory Limit > 16GB (at least if you wanna ball hard)

4. Check the docker-compose.yml file. I added 6 models, feel free to change them if you want, or remove some, or add some, or whatever you want
    # ollama libray: https://ollama.com/library

5. If you edited number of models in the docker-compose.yml file, update the nginx.conf to reflect the models you're using

6. Start that shit in your terminal at extracted directory:
    cd /path/where/these/files/live/
    docker compose up -d

7. Model downloads are going to take forever, check the progress with: 
    docker logs -f ollama-model-importer-1

8. Use your own ai in browser:
    http://localhost:8081/


Done playing?
1. Stop services:
    docker compose down
2. Restart services
    docker compose up -d

3. Compeltely blow it away so it and all models is gone forever and don't do this unless you are trying to kill Skynet:
    docker compose down --volumes --rmi all --remove-orphans



Got problems?
1. Check docker status: 
    docker compose ps
    docker stats
2. Hit dozzle (logs) in browser:
    http://localhost:8888
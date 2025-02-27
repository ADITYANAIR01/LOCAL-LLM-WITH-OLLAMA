# 1. Setup WSL (Windows)

# Install WSL and Ubuntu

        wsl --install

# Connect to a WSL Instance in a New Window

        wsl -d Ubuntu

# 2. Install Ollama

# Download and install Ollama from the official website:
# https://ollama.com/download
# Ollama with Ubuntu using curl command
        curl -fsSL https://ollama.com/install.sh | sh

# Add a Model to Ollama
        ollama pull llama3.1


# 3. Watch GPU Performance in Linux
 To monitor GPU performance, use the following command
        
        watch -n 0.5 nvidia-smi

# 4. Install Docker

# Add Docker's official GPG key:
Copy all the below code:

sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

echo \
"deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
$(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update

# Install Docker
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

# 5. Run Open WebUI Docker Container
docker run -d --network=host -v open-webui:/app/backend/data -e OLLAMA_BASE_URL=http://127.0.0.1:11434 --name open-webui --restart always ghcr.io/open-webui/open-webui:main

# 5. Add the local llm in Vs Code 
* visit: https://www.continue.dev/
* Download Vs code extension Continue
* Now add llm to the continue workspace

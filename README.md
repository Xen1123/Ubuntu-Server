<h1 align=center>Ubuntu Server Help</h1>
<h3 align=center>With a LOT of Docker</h3>

## Repository Contents 📂

- Scripts
- Guides

## What is Docker? 

- Docker is a program that creates containers for individual apps, most self hosted apps have their normal versions you install, but Docker makes everything easy to manage. It is also more secure, as each container is in its own sandbox.

<details>
    <summary><b>Docker Installation On Ubuntu Server</b></summary>

- You'd think it's just `sudo apt install docker`, but it isn't. This is directly from Docker's website.

```bash
sudo apt update
sudo apt install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

sudo tee /etc/apt/sources.list.d/docker.sources <<EOF
Types: deb
URIs: https://download.docker.com/linux/ubuntu
Suites: $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}")
Components: stable
Architectures: $(dpkg --print-architecture)
Signed-By: /etc/apt/keyrings/docker.asc
EOF

sudo apt update

sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

- This installs and sets up Docker correctly!

</details>
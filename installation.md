# Installation

## 1. Update Ubuntu system

```bash
sudp apt update
sudo apt upgrade -y

---

## 2. Install Docker

Docker was installed using Ubuntu's package repository. 

```bash
sudo apt install -y docker.io docker-compose-v2
```

---

## 3. enable Docker

Docker was configured to start automatically whenever the Raspberry Pi boots. 

```bash
sudo systemctl enable --now docker
```

---

## 4. Configure User Permissions

The current user was added to the Docker group to allow Docker commands without using `sudo`. 

```bash 
sudo usermod -aG docker $USER
sudo reboot
```



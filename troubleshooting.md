# Troubleshooting

## Issue 1: Docker CE packages unavailable

### Problem

While following the official Docker installation guide, the Docker CE packages were unavailable for my Ubunut Server release.

Error:
```
Candidate: (none)
```

### Cause

The Raspberry Pi was running a never Ubuntu release, and the official Docker repository did no provide Docker CE packages fo the release.

### Solution

Intalled docker using Ubuntu's package repository instead.

```bash
sudo apt install -y docker.io docker-compose-v2
```

---

## Issue 2: Portainer web interface inaccessible

### Problem

Portainer deployed successfully, but I could not access the web interface from my laptop. 

### Investigation

Verified the container was running:

```bash
dcoker ps
```

Verified the Raspberry Pi IP address:

```bash
hostname -I
```
Attempted to reach the Raspberry Pi from my laptop:

```test
Destination host unreachable
```

### Cause

The school network prevented communication between deviced (likely client isolation or firewall rules).

### Resolution

Confirmed that Portainer was functioning correctly on the Raspberry Pi. The issue was related to the network environment rather than Docker or Portainer.

---

## Lesson Learned

- Verify services locally before assuming an application has failed. 
- Separate application issues from network issues during troubleshooting.
- Use commands such as `docker ps`, `curl`, `hostname -I`, and `ping` to isolate problems. 
- Enterprise and school networks may block device-to-device communication for security reasons.

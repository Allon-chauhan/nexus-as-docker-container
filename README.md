# 🚀 Deploying Nexus as a Docker Container

### 🛠️ Technologies Used:
1. **Docker** 🐳
2. **Nexus** 📦
3. **DigitalOcean Droplet** ☁️
4. **Linux** 🐧

---

## ✅ Prerequisites
1. A **DigitalOcean account** with available credits to start a Linux droplet.
2. **SSH key** configured on your local machine for secure access to the DigitalOcean droplet.

---

## ⚙️ Setting Up and Configuring a Server on DigitalOcean
1. **Create a small, cost-effective droplet** in your nearest region.
2. Choose **SSH** as the authentication method.
3. **Generate a new SSH key**, copy the public key from your local machine, and save the changes.
4. Once the droplet is ready, **note down the public IPv4 address**.
5. Connect to the server via terminal:
   ```bash
   ssh root@<droplet-ipv4>
   ```
   *If SSH is configured correctly, you'll be logged in as the root user.*

---

## 🐳 Installing Docker on DigitalOcean Droplet
Run the following command to install Docker:
```bash
snap install docker
```

---

## 📦 Starting a New Nexus Container
1. **Create a Docker volume** to persist Nexus data:
   ```bash
   docker volume create --name nexus-data
   ```
2. **Run the Nexus container**:
   ```bash
   docker run -d -p 8081:8081 --name nexus -v nexus-data:/nexus-data sonatype/nexus3
   ```

Once the container is running, you can access the **Nexus Repository Manager** at:
```
http://<droplet-public-ipv4>:8081
```

🚀 **Nexus is now deployed and ready to use!** 🎉

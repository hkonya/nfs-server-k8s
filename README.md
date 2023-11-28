### TR
### NFS Sunucusu Kurulumu
1. Güncellemeleri kontrol edin ve yükleyin: `sudo apt update`
2. NFS kernel sunucusunu yükleyin: `sudo apt install nfs-kernel-server`
3. Sunucu durumunu kontrol edin: `sudo systemctl status nfs-kernel-server.service`
4. Paylaşım için bir dizin oluşturun ve izinleri ayarlayın.
5. NFS ayarlarını yapılandırın.
6. NFS sunucusunu yeniden başlatın ve güvenlik duvarı ayarlarını yapılandırın.

### NFS İstemcisi Kurulumu
1. NFS ortak kullanım araçlarını yükleyin: `sudo apt install nfs-common`
2. NFS sunucusuna bağlanmak için bir bağlama noktası oluşturun.
3. NFS sunucusuna bağlanın (Sunucunun dahili IP adresini kullanın).

### Kubernetes StorageClass ve NFS-Provisioner Oluşturma
1. `class.yaml` dosyasını oluşturun ve aşağıdaki içeriği ekleyin:
   ```yaml
   apiVersion: storage.k8s.io/v1
   kind: StorageClass
   metadata:
     name: managed-nfs-storage
   provisioner: nfs-provisioner
   parameters:
     archiveOnDelete: "false"
   ```
2. `deployment.yaml` dosyasını oluşturun ve aşağıdaki içeriği ekleyin:
   ```yaml
   [deployment.yaml içeriği]
   ```
3. `rbac.yaml` dosyasını oluşturun ve aşağıdaki içeriği ekleyin:
   ```yaml
   [rbac.yaml içeriği]
   ```

### EN
### NFS Server Setup
1. Check for and install updates: `sudo apt update`
2. Install the NFS kernel server: `sudo apt install nfs-kernel-server`
3. Check the server status: `sudo systemctl status nfs-kernel-server.service`
4. Create a directory for sharing and set permissions.
5. Configure NFS settings.
6. Restart the NFS server and configure firewall settings.

### NFS Client Setup
1. Install NFS common utilities: `sudo apt install nfs-common`
2. Create a mount point to connect to the NFS server.
3. Connect to the NFS server (Use the internal IP address of the server).

### Kubernetes StorageClass and NFS-Provisioner Setup
1. Create a `class.yaml` file and add the following content:
   ```yaml
   apiVersion: storage.k8s.io/v1
   kind: StorageClass
   metadata:
     name: managed-nfs-storage
   provisioner: nfs-provisioner
   parameters:
     archiveOnDelete: "false"
   ```
2. Create a `deployment.yaml` file and add the following content:
   ```yaml
   [deployment.yaml content]
   ```
3. Create a `rbac.yaml` file and add the following content:
   ```yaml
   [rbac.yaml content]
   ```
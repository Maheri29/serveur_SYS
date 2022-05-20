<h1>NFS?</h1>
    <p>NFS est l'abréviation de Network File System, c'est-à-dire système de fichiers réseau. Ce système de fichiers en 
        réseau permet de partager des données principalement entre systèmes de type 
        UNIX mais des versions existent également pour Microsoft Windows™ et Mac.
    </p>

   <h2>NFS, pour faire quoi?</h2>
                <p>NFS peut être utilisé pour partager des répertoires de fichiers entre plusieurs utilisateurs sur un même réseau.
                </p>

 <h2>Installer NFS</h2>
                <p>Coté serveur:  </p>
                   <p>apt-get nfs-kernel-server</p> 
                   <p>apt install nfs-kernel-server</p> 
<h2>Configuration</h2>
                  
                    
  <p>Partie Client:</p>
                    <p>Pour la paverrtie cliente, on installe les paquets adéquats :</p>
                    <p>$ apt install nfs-common $ mkdir -p /media/nfs mount -t nfs 192.168.21.200:/media/partage /media/nfs</p>
                    <p> Avec la commande df, on peut voir que tout est monté :</p>
                    <p>$ df -h Filesystem Size Used Avail Use% Mounted on 192.168.21.200:/media/partage 20G 985M 18G 5% /media/nfs</p>
                    <p> Quelques options de montage utiles:</p>
                    <p>Au travail, j'utilise un partage NFS pour étendre du stockage pour un coût peu élevé.</p>
                    <p>Mais le système se comporte bizarrement lorsque le partage NFS est indisponible (reboot du NAS, perte temporaire de réseau).</p>
                    <p>Pour cela, on peut monter le partage NFS avec les options soft, retrans et timeo. Je choisis 2 retransmissions en cas d'échec et 5 dixièmes de secondes (500 ms) de timeout (le NAS et le serveur sont dans le même sous-réseau, sur le même switch):</p>
                    <p>$ mount -t nfs4 192.168.21.200:/media/partage /media/nfs -o soft,retrans=2,timeo=5</p>
                    <p>Ou dans /etc/fstab :</p>
                    <p>$ 192.168.21.200:/media/partage /media/nfs nfs auto,_netdev,nofail,soft,retrans=2,timeo=5 0 0</p>

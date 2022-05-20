<h1>SAMBA?</h1>
<p>Samba est une implémentation à source ouverte des protocoles SMB (Server Message Block) et CIFS 
    (Common Internet File System), qui fournit des services de fichiers et d'impression entre des 
    clients de différents systèmes d'exploitation.</p>

    <h2>Samba, pour faire quoi?</h2>
    <p>Un serveur Linux-Samba permet d'organiser les autorisations de partage de données et
         autres services en réseau (comme un serveur Windows), mais aussi de prendre en charge
          le rôle d'Active Directory Domain Controllers.</p>

          <h2>Comment l'installer?</h2>
          <p>Saisissez la commande suivante dans un terminal :

            sudo apt-get install samba
            apt install samba</p>

            <h2>Configurer Samba</h2>

            <p>Remplacer utilisateur1 avec l'utilisateur de partage samba pour créer. Définissez le mot 
                de passe utilisateur et confirmez. $ sudo smbpasswd -a user1 Nouveau mot de passe SMB: Retapez 
                le nouveau mot de passe SMB: Utilisateur ajouté user1.</p>

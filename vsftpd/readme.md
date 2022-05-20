<h1>VSFTPD?</h1>
<p>Very Secure FTP Daemon, est un serveur FTP qui mise beaucoup sur la sécurité. Il est l'un des premiers logiciels serveurs à mettre en œuvre la séparation des privilèges, minimisant ainsi les risques de piratage.</p>
<p>FTP veut dire « File Transfert Protocol » ou Protocole de transfert de Fichier. C’est un langage qui va permettre l’échange de fichiers entre 2 ordinateurs, et plus exactement entre un serveur et un client.</p>
<p>serveur FTP: Le serveur FTP est un logiciel qui va répondre aux demandes des clients. Lorsque le serveur reçoit une demande, il vérifie les droits et si le client à les droits suffisants, il répond à cette demande sinon la demande est rejetée.</p>
<p>client FTP: C’est lui qui va être à l’initiative de toutes les transactions. Il se connecte au serveur FTP, effectue les commandes (récupération ou dépôt de fichiers) puis se déconnecte.</p>

<h2>Pourquoi l'utiliser?</h2>
<p>Dispose d'une sauvegarde automatique.</p>
<p>Il donne le contrôle sur le transfert. Autrement dit, on peut choisir le mode dans lequel les données sont transférées sur le réseau.</p>
<p>On peut travailler avec les répertoires sur les systèmes distants, supprimer ou renommer les fichiers distants tout en transférant les données entre 2 hôtes.</p>

<h2>Installation</h2>
<p>Saisir dans le terminal</p>
<p>sudo apt install vsftpd</p>
<p>Une fois installé, nous commencerons par faire une copie du fichier de configuration d'origine. En cas de problème, les paramètres par défaut peuvent être restaurés.</p>
<p>sudo cp /etc/vsftpd.conf /etc/vsftpd.conf_default</p>
<p>Maintenant, nous allons démarrer le service avec la commande:</p>
<p>sudo systemctl start vsftpd</p>
<p>Nous confirmons qu'il fonctionne avec:</p>
<p>    
sudo systemctl enable vsftpd</p>
<p>Compte utilisateur FTP</p>
<p>Avec ça Nous pouvons utiliser n'importe quel client FTP pour accéder aux fichiers hébergés sur le serveur via vsftpd. Dans le terminal (Ctrl + Alt + T), nous n'aurons qu'à utiliser la commande:</p>
<p>1
sudo useradd –m nombre-usuario</p>
<p>Remplace 'Nom d'utilisateur'par votre nom d'utilisateur prévu. Maintenant nous allons définir un mot de passe:</p>
<p>    
sudo passwd nombre-usuario</p>
<p>Après nous allons passer au dossier utilisateur nouvellement créé:</p>
<p>cd /home/nombre-usuario</p>
<p>Idéalement, FTP devrait être limité à un répertoire spécifique pour des raisons de sécurité. Vsftpd utilise des cages chroot pour y parvenir. Avec le chroot activé, un utilisateur local est limité à son répertoire personnel (par défaut). Pour cet exemple, nous allons créer un répertoire ftp qui agira comme un chroot, avec un répertoire de fichiers modifiables.</p>
<p>Pour commencer nous créons le dossier FTP:</p>
<p>    
sudo mkdir ftp</p>
<p>Nous définirons la propriété du dossier avec cette autre commande:</p>
<p>sudo chown nobody:nogroup /home/nombre-usuario/ftp</p>
<p>maintenant nous supprimons les autorisations d'écriture de ce dossier:</p>
<p>sudo chmod a-w /home/nombre-usuario/ftp</p>
<p>Nous continuons à créer le répertoire du conteneur de fichiers et nous attribuerons la propriété:</p>
<p>sudo mkdir /home/nombre-usuario/ftp/files </p>
<p>sudo chown nombre-usuario:nombre-usuario /home/nombre-usuario/ftp/files</p>
<p>À ce stade, nous allons créer un fichier de test dans le dossier des fichiers:</p>
<p>cho "vsftpd archivo de ejemplo" | sudo tee /home/nombre-usuario/ftp/files/ejemplo.txt</p>

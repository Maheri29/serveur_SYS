<h1>NGINX?</h1>
<p>C'est un serveur web open-source qui, depuis son succès initial en tant que serveur web, est maintenant aussi utilisé comme reverse proxy, cache HTTP, et load balancer.</p>
<p>Reverse proxy : c'est un type de serveur, habituellement placé en frontal de serveurs web.</p>
<p>Cache HTTP : les performances des sites et applications web peuvent être significativement améliorées en réutilisant les ressources déjà collectées précédemment.</p>
<p>Load balencer : elle désigne le processus de répartition d’un ensemble de tâches sur un ensemble de ressources.</p>

<h2>Pourquoi l'utiliser?</h2>
<p>plus performant qu'Apache dans le traitement de nombreuses connexions simultanées.</p>
<p>nginx utilise considérablement moins de stockage par connexion client.</p>
<p>mieux lorsqu’il s’agit de traiter un contenu statique</p>
<p>Surpasse Apache dans la gestion du contenu statique</p>

<h2>Installation</h2>
<p>1. Avec la commande suivante, vous actualisez les différents éléments du paquet NGINX de manière à posséder les versions les plus récentes (actualisation lancée via la deuxième ligne du code) :</p>
<p>sudo apt-get update</p>
<p>sudo apt-get install nginx</p>
<p>2. NGINX se lance généralement directement à la suite de cette actualisation. Afin de vérifier si le logiciel fonctionne en bonne et due forme, chargez la landingpage de NGINX via le nom de domaine de votre serveur ou l’adresse IP correspondante dans votre navigateur Internet. Si l’installation est réussie, vous obtenez le message suivant :</p> 
<h1>Welcome to nginx!</h1>

<h2>Configuration</h2>
<p>Tout ce dont vous aurez besoin pour la configuration de votre serveur NGINX se trouve dans le dossier /etc/nginx et dans le fichier de configuration nginx.conf. A chaque fois que vous effectuez des modifications dans ces fichiers, il est nécessaire de redémarrer le serveur à l’aide de l’une des commandes suivantes pour qu’elles soient prises en compte :</p>
<p>sudo service nginx reload</p>
<p>sudo service nginx restart</p>

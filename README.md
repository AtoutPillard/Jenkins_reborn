# Jenkins


<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_fr/logo.png" style="width:40%">
</p>

# I - Introduction

<br>

## **A - Présentation**

Jenkins est un outil d'**automatisation** open source écrit en Java utilisé pour construire et implémenter les principes d'**intégration continue**.

Jenkins construit et teste nos projets logiciels, ce qui facilite en permanence l'intégration des **modifications** du projet par les développeurs et facilite l'obtention d'une **nouvelle version** par les utilisateurs.

Cela nous permet également de fournir en **continu** notre logiciel en s'intégrant à un grand nombre de technologies de test et de **déploiement**.

Il offre un moyen simple de configurer un environnement d'intégration continue ou de **livraison continue** pour presque tous les langages et les référentiels de code source (comme GitHub, GitLab...) à l'aide de **pipelines**, ainsi que d'automatiser la plupart des tâches de développement.

Grâce à cet outil, les organisations peuvent accélérer le processus de développement logiciel grâce à l'automatisation. Jenkins ajoute des **processus** de cycle de vie de développement de toutes sortes, y compris la construction, la documentation, le test, le package, la mise en scène, le déploiement d'analyses statiques et bien plus encore.

Si une organisation développe un projet, **Jenkins** testera en permanence les **versions** de notre projet et mettra en lumière les erreurs dans les premières étapes de notre développement.

Les étapes possibles exécutées par Jenkins sont par exemple :

- Effectuer une construction de logiciel à l'aide d'un système de construction comme **Gradle** ou **Maven Apache**

- Exécuter un **script** shell

- Archiver un résultat de génération

- Exécution de tests logiciels

## **B - Histoire de Jenkins**

En 2011 Oracle qui possédait la société Sun Microsystems a eu un différend avec la communauté open source d'Hudson. Hudson avait une vision bien différente d'Oracle en terme d'engineering et a décidé de bifurquer le projet et d'inaugurer **Jenkins**.

Hudson et Jenkins ont continué à fonctionner de manière indépendante. Mais en peu de temps, Jenkins a acquis beaucoup de contributeurs et de projets tandis qu'Hudson n'a conservé que 32 projets. Puis avec le temps, Jenkins est devenu plus populaire, et Hudson n'est depuis plus maintenu.

<div class="alert alert-info">Jenkins est l'un des outils de <b>de l'intégration continue</b> open source les plus utilisés. Il permet aux développeurs d'implémenter des pipelines CI/CD dans l'environnement de développement de manière complète.</div>

## **C - Intégration continue - Livraison continue - Déploiement continu**

Le **CI/CD** (intégration continue/livraison continue) est un processus DevOps holistique (qui s'intéresse à son objet dans sa globalité) et se concentre sur la création d'un mélange compatible entre le **cycle de développement** et le **processus d'exploitation**.

Cela se fait en automatisant les **flux de travail** et en déployant des mises à jour **automatiques** pour améliorer le retour sur investissement. La mise en œuvre du pipeline CI/CD facilite le processus d'introduction du produit sur le marché plus rapidement que jamais.

### c.1 - Qu'est-ce que l'intégration continue ?

CI pour **Continue Integration** n'est pas entièrement une condition préalable essentielle requise pour créer un produit logiciel stable. Cependant, il joue certainement un rôle important lors du développement de produits logiciels ou de composants nécessitant des modifications fréquentes. De plus, cela garantit également que tous les composants d'une application sont correctement intégrés.

L'intégration continue est une pratique de développement dans laquelle les développeurs doivent **valider** les **modifications** apportées au code source dans un référentiel partagé à intervalles réguliers. Chaque `commit` effectué dans le référentiel est ensuite construit. Cela permet aux équipes de développement de détecter les problèmes en amont.

L'intégration continue nécessite que les développeurs aient des versions **régulière**s. La pratique générale est que chaque fois qu'une validation de code se produit, une génération doit être déclenchée.

<div class="alert alert-info">L'intégration continue, qui a d'abord été proposée comme terme par Gary Booch, intègre le code source au référentiel. Cela permet aux développeurs de mener à bien le processus de développement de manière rapide et sophistiquée.</div>

Dans le SDLC (**Software Development Life Cycle** ou Cycle de vie de développement), CI couvre principalement les phases **Source** et **Build**.

Un pipeline **CI** implique généralement ces étapes :

> 1 - Détecter les changements dans le code
>
> 2 - Analyser la qualité du code source
>
> 3 - Construire le code
>
> 4 - Exécuter tous les tests unitaires
>
> 5 - Exécuter tous les tests d'intégration
>
> 6 - Générer des artefacts déployables
>
> 7 - État du rapport

Si l'une des étapes ci-dessus échoue, l'intégration s'arrête immédiatement et l'équipe est informée du résultat.

### c.2 - Qu'est-ce que la livraison continue ?

La livraison continue, quant à elle, est un ensemble de pratiques de développement logiciel qui garantit le déploiement du code en production tout en effectuant des tests efficaces au cours du processus. Plus précisément, CD commence là où CI se termine. La livraison continue est chargée de pousser le code vers l'environnement de test où différents tests tels que les tests système, les tests unitaires et les tests d'intégration sont effectués.

Un pipeline CI/CD typique fonctionne en 4 phases répertoriées ci-dessous :

- **Phase 1** : **Commit** - il s'agit de la phase réelle au cours de laquelle les développeurs valident les modifications apportées au code.

- **Phase 2** : **Build** - dans cette phase, le code source est intégré dans la build à partir du référentiel.

- **Phase 3** : **Automatisation des tests** - cette étape fait partie intégrante de tout pipeline CI/CD. Le code source préalablement intégré dans le build est soumis à un cycle de test systématique.

- **Phase 4** : **Déploiement** - la version testée est finalement envoyée pour déploiement dans cette phase.

Alors que l'intégration continue couvre les étapes de validation et de construction, la livraison continue, quant à elle, assure l'**automatisation** des processus ainsi que les tests jusqu'à la **phase de déploiement** en environnement de **développement**, de test et de qualité.

La livraison en **production** quand à elle doit être valider de façon manuelle par un humain dans le processus de livraison continue.

### c.3 - Qu'est-ce que le déploiement continue ?

Le **déploiement continue** est une méthode qui comprend les **même phases** que la **livraison continue**, à la différence qu'elle permet le déploiement automatisé jusqu'à l'environnement de production **sans validation humaine**. Une entreprise utilisera pour un processus CI/CD le déploiement continue ou alors une **livraison continue**.

## **D - Intégration continue avec Jenkins**

Considérons un scénario où le code source complet de l'application a été créé puis déployé sur le serveur de test pour les tests. Cela semble être un moyen parfait de développer des logiciels bien que ce processus présente de nombreux problèmes :

- Les équipes de développeurs doivent attendre que le logiciel **complet** soit développé pour les résultats des tests.

- Il y a de fortes chances que les résultats des tests montrent plusieurs bugs. Il était difficile pour les développeurs de localiser ces bugs car ils devaient vérifier l'**intégralité** du code source de l'application.

- Cela **ralentit** le processus de livraison du logiciel.

- Les commentaires continus concernant des éléments tels que les problèmes d'**architecture** ou de **codage**, les échecs de construction, l'état des tests et les téléchargements de versions de fichiers manquaient, ce qui pouvait entraîner une baisse de la qualité du logiciel.

- L'ensemble du processus était **manuel**, ce qui augmente le risque d'échecs fréquents.

Il ressort clairement des problèmes mentionnés ci-dessus que non seulement le processus de livraison du logiciel est devenu lent, mais que la qualité du logiciel a également diminué. Cela conduit à l'insatisfaction des clients.

Donc, pour corriger ce problème, il était nécessaire d'avoir un système où les développeurs peuvent **déclencher** en permanence une construction et tester chaque modification apportée au code source.

Jenkins permettra donc de résoudre ce problème. Jenkins est un outil d'intégration continue très mature, alors voyons comment l'intégration continue avec Jenkins a surmonté les lacunes ci-dessus.

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/continuous-integration-2.png" style="width:45%">
</p>

- Tout d'abord, un développeur **valide** le code dans le référentiel de code source. Pendant ce temps, le Jenkins vérifie le **référentiel** à intervalles réguliers pour les changements.

- Peu de temps après une validation, le serveur Jenkins trouve les **modifications** qui se sont produites dans le référentiel de code source. Jenkins dessinera ces changements et commencera à préparer une **nouvelle version**.

- Si la construction échoue, l'équipe concernée en sera informée.

- Si la construction réussit, le serveur Jenkins **déploie** la construction dans le serveur de test.

- Après les tests, le serveur Jenkins génère un retour d'information, puis informe les développeurs des résultats de la construction et des tests.

- Il continuera à vérifier le référentiel de code source pour les **modifications** apportées au code source et l'ensemble du processus se répète.

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_fr/CI_CD.png" style="width:75%">
</p>

La publication (**release**) d'un logiciel passe par de nombreuses étapes. La première étape est bien sûr de développer le logiciel en question, ou les nouvelles fonctionnalités. Il faut ensuite souvent passer par une étape de **build**, qui permet de créer une version exécutable du logiciel à partir du code source. Après le **build**, des tests sont réalisés. En cas de succès, le logiciel est **publié** ou **déployé**.

En cas d'échec, il faudra analyser ce qui a provoqué les erreurs et modifier le code en conséquence pour résoudre les bugs. Toutes ces étapes doivent être réalisées avant chaque **release**, ce qui peut devenir très lourd, surtout si les releases sont fréquentes.

C'est là qu'intervient Jenkins, qui permet d'**automatiser les étapes**. En effet, nous modifions les fichiers sources de notre projet et Jenkins nous notifie si les **transformations** sont un succès ou un échec.

De même, nous pouvons aussi déployer une **nouvelle version** d'un logiciel sans difficultés. Ainsi les développeurs disposent de plus de temps pour se concentrer sur les phases demandant plus de réflexion.

Jenkins se démocratise de plus en plus, d'une part grâce à son installation qui s'est simplifiée avec le temps et d'autre part, par son association avec divers logiciels importants comme **Kubernetes**, **Docker** et **Git**. De plus, disposant d'une interface **graphique** depuis le navigateur, son utilisation s'est facilitée.

Enfin, puisqu'il s'agit d'un outil **open-source**, il est régulièrement mis à jour, comme vous pourrez le constater en allant sur leur [GitHub](https://github.com/Jenkinsci/Jenkins) ou leur [Docker Hub](https://hub.docker.com/r/Jenkins/Jenkins).

## **E - Avantages et inconvénients de l'utilisation de Jenkins**

### e.1 - Avantages de Jenkins

- C'est un outil open source et gratuit.

- Il ne nécessite pas de composants ou dépendances supplémentaires. Cela signifie qu'il est facile à installer.

- Il prend en charge **1000 plugins** ou plus pour faciliter notre travail. Si un plugin n'existe pas, nous pouvons écrire le script correspondant et le partager avec la communauté.

- Il est construit en **Java** et est donc portable.

- Il est indépendant de la plate-forme et est disponible pour toutes les plates-formes et différents systèmes d'exploitation. Comme OS X, Windows ou Linux.

- Jenkins prend également en charge l'architecture basée sur le **cloud** afin que nous puissions déployer Jenkins sur des plates-formes basées sur le cloud.

### e.2 - Inconvénients de Jenkins

- Son interface est **obsolète** et peu conviviale par rapport aux tendances actuelles de l'interface utilisateur.

- Pas facile à maintenir car il tourne sur un serveur et nécessite quelques compétences en tant qu'administrateur de serveur pour **surveiller** son activité.

- CI se casse régulièrement en raison de quelques petits changements de **réglage**. CI sera mis en pause et nécessite donc l'attention de l'équipe de développeurs.

## **F - Architecture Jenkins**

Jenkins suit l'architecture maître-esclave pour gérer les builds distribués. Dans cette architecture, l'esclave et le maître communiquent via le protocole TCP/IP.

L'architecture Jenkins comporte deux composants :

- Jenkins Master
- Jenkins Worker

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/jenkins_architecture.png" style="width:45%">
</p>

### f.1 - Jenkins Master

Le serveur **principal** de Jenkins est le Jenkins **Master**. Il s'agit d'un tableau de bord Web alimenté par un fichier `war`.

Par défaut, celui-ci fonctionne sur le port **8080**. Avec l'aide du Dashboard, nous pouvons configurer les travaux ou/et projets mais la construction de ces travaux a lieu sur les Jenkins **Worker**. Par défaut, un nœud esclave est configuré et exécuté sur le serveur Jenkins. Nous pouvons ajouter plus de nœuds en utilisant l'adresse IP, le nom d'utilisateur et le mot de passe en utilisant les méthodes `ssh`, `jnlp` ou `webstart`.

Le travail du serveur ou le travail du Master consiste à gérer :

- Planification des travaux de **construction**.

- Envoi des **builds** aux nœuds/esclaves pour l'exécution.

- **Surveiller** les nœuds/esclaves (éventuellement en les mettant en ligne et hors ligne selon les besoins).

- Enregistrement et présentation des résultats de construction.

- Une instance **maître/serveur** de Jenkins peut également exécuter directement des tâches de build.

### f.2 - Jenkins Worker

Le Jenkins Worker est utilisé pour exécuter les tâches de **build** envoyées par le **Master**. Nous pouvons configurer un projet pour qu'il s'exécute toujours sur une machine esclave particulière, ou un type particulier de machine esclave, ou simplement laisser Jenkins choisir le prochain esclave (nœud) disponible.

Comme nous le savons, Jenkins est développé à l'aide de Java et est indépendant de la plate-forme utilisé. Ainsi, les Jenkins **Master** et **Worker** peuvent être configurés sur n'importe quel serveur, y compris Linux, Windows et Mac.

De cette introduction, vous remarquerez que l'usage de Jenkins n'est pas réservé aux Data Engineer, à l'instar d'un système de versioning, il s'agit d'un outil phare pour tout développeur.

#%%

# II - Installation de Jenkins

Nous allons, à présent, installer Jenkins via Docker avec son image officielle. Pour information, Docker est une plateforme open-source utilisée pour automatiser le déploiement d'applications dans des conteneurs. Ces conteneurs Docker permettent d'emballer une application et toutes ses dépendances dans une unité portable et légère, ce qui va faciliter son exécution et son déploiement sur différentes plateformes.
Quant à l'image Docker, il s'agit d'un paquet autonome et exécutable qui contient tout le nécessaire pour exécuter une application.

> Ouvrez une fenêtre de terminal et exécutons les commandes suivantes pour télécharger l'image Docker de Jenkins depuis le registre DockerHub et créer un réseau spécifique à l'outil :

```shell
docker pull jenkins/jenkins
docker pull docker:dind
docker network create jenkins
```

> Puis lancez le premier conteneur Docker avec la commande :

Cette commande va nous permettre d'avoir un conteneur Docker autonome (Docker-in-Docker) c'est à dire un environnement Docker fonctionnel à l'intérieur du conteneur Jenkins. Cela va nous permettre d'exécuter des constructions et des déploiements Docker à partir de Jenkins.


```shell
docker run \
  --name jenkins-docker \
  --rm \
  --detach \
  --privileged \
  --network jenkins \
  --network-alias docker \
  --env DOCKER_TLS_CERTDIR=/certs \
  --volume jenkins-docker-certs:/certs/client \
  --volume jenkins-data:/var/jenkins_home \
  --publish 2376:2376 \
  docker:dind \
  --storage-driver overlay2
```

> Dans un fichier que vous nommerez `Dockerfile`, recopiez les lignes suivantes qui vont permettre de créer une image personnalisée de Jenkins avec les plugins "blueocean" et "docker-workflow" pré-installés :

```dockerfile
FROM jenkins/jenkins:2.346.3-jdk11
USER root
RUN apt-get update && apt-get install -y lsb-release
RUN curl -fsSLo /usr/share/keyrings/docker-archive-keyring.asc \
  https://download.docker.com/linux/debian/gpg
RUN echo "deb [arch=$(dpkg --print-architecture) \
  signed-by=/usr/share/keyrings/docker-archive-keyring.asc] \
  https://download.docker.com/linux/debian \
  $(lsb_release -cs) stable" > /etc/apt/sources.list.d/docker.list
RUN apt-get update && apt-get install -y docker-ce-cli
USER jenkins
RUN jenkins-plugin-cli --plugins "blueocean:1.25.6 docker-workflow:1.29"
```

> Lancez la commande suivante pour construire notre image Docker :

```shell
docker build -t myjenkins-blueocean:2.346.3-1 .
```

> Enfin, démarrez Jenkins via ce nouveau conteneur Docker :

```shell
docker run \
  --name jenkins-blueocean \
  --restart=on-failure \
  --detach \
  --network jenkins \
  --env DOCKER_HOST=tcp://docker:2376 \
  --env DOCKER_CERT_PATH=/certs/client \
  --env DOCKER_TLS_VERIFY=1 \
  --publish 8080:8080 \
  --publish 50000:50000 \
  --volume jenkins-data:/var/jenkins_home \
  --volume jenkins-docker-certs:/certs/client:ro \
  myjenkins-blueocean:2.346.3-1
```

<div class="alert alert-info"><i class="icon circle info"></i>
Pour ne pas recopier ces longues commandes Docker, vous pouvez passer par des <code>alias</code>, pour les rendre permanent, vous pouvez apprendre en faire depuis ce <a href="https://www.linuxtricks.fr/wiki/personnaliser-son-shell-alias-couleurs-bashrc-cshrc">lien</a>.
</div>

> Après avoir lancer les conteneurs Docker, accédez à Jenkins en allant sur `localhost:8080` ou `adresse-ip-vm:8080` (si vous utilisez la machine virtuelle) sur notre navigateur internet. 

Nous arrivons alors sur la page ci-dessous:

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_fr/unlock.png" style="width:65%">
</p>

> Pour générer le mot de passe demandé, exécutez la commande suivante :

```shell
docker logs jenkins-blueocean
```

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_fr/find_admin_password.png" style="width:65%">
</p>

<div class="alert alert-info"><i class="icon circle info"></i>
Si vous avez besoin d'accéder au répertoire <code>/var/jenkins_home</code>, qui contient des informations relatives à Jenkins, lancez la commande <code>docker exec -it jenkins-blueocean bash</code>.
</div>

Une fois le mot de passe entré, nous arriverons sur la page suivante :

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_fr/custo.png" style="width:65%">
</p>

> Sélectionnez le bouton _Install suggested plugin_. Vous devriez tomber sur l'écran de configuration de la connexion administrateur. Remplissez alors le formulaire avec les informations requises.

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/jenkins-admin-user.png" style="width:65%">
</p>

<div class="alert alert-warning">
Attention à bien noter vos identifiants de connexion.
</div>

Nous devrions arriver sur le dashboard Jenkins :

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_fr/welcome.png" style="width:75%">
</p>

Nous avons réussi à installer et configurer Jenkins. À gauche se trouve le **menu principal** permettant d'accéder aux différentes fonctionnalités de Jenkins comme la création de projets, la consultation de l'historique, ou encore la configuration de Jenkins.

#%%

# III - Premiers pas sur Jenkins

<br>

## **A - Plugins**

Nous allons nous intéresser sur la paramétrisation de Jenkins, particulièrement aux **plugins de Jenkins**. Ce sont des composants essentiels qui étendent les fonctionnalités de base de Jenkins et permettent de personnaliser les flux de travail d'intégration continue selon les besoins spécifiques des projets.

Dans l'écran d'accueil de Jenkins (tableau de bord Jenkins), cliquons sur l'option **Administrer Jenkins** (*Manage Jenkins*) situé sur le côté gauche du dashboard.

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/manage_jenkins.png" style="width:60%">
</p>

À présent, focalisons nous sur la partie *System Configuration*, nous remarquons plusieurs onglets mais nous allons nous intéresser à l'onglet **Gestion des plugins** (*Manage plugins*). Il s'agit d'une fonctionnalité de Jenkins qui permet d'améliorer son usage.

Il y a plus de 1800 plugins pour Jenkins, parmi ceux-ci, on peut notamment citer les intégrations avec les différents **systèmes de contrôle de version** (Git, Mercurial, SVN), Kubernetes, Docker et même des services de **Cloud Computing** (AWS, Azure, GCP).

>  Cliquez sur l'option "Gestion des plugins"

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/manage_plugins.png" style="width:60%">
</p>

Sur la page *Plugin Manager*, nous pouvons voir que les plugins sont regroupés dans 4 onglets :

  - `Mises à jour/Updated ` qui liste les plugins installés pour lesquels des mises à jour sont disponibles.

  - `Disponibles/Available` qui permet de chercher et d'installer les plugins dont nous avons besoin.

  - `Installés/Installed` qui liste l'ensemble des plugins que nous avons installés.

  - `Avancé/Advanced` qui est une interface plus complexe pour installer des plugin manuellement.

  <div class="alert alert-info"><i class="icon circle info"></i>
  Jenkins fourni également un <a href="https://plugins.Jenkins.io/" target="_blank">site</a> qui liste les différents plugins existants, sur lequel nous pourrons trouver une documentation plus détaillée.
  </div>

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/available_plugins.png" style="width:60%">
</p>

L'onglet **Available** nous donne une liste des plugins disponibles au téléchargement. 

> Dans le champ de recherche de l'onglet **Diponibles**, entrez `github integration` et cochez sur la checkbox afin de sélectionner le plugin `github integration`:

**Github** est un référentiel de code basé sur le Web qui fournit une plate-forme commune à de nombreux développeurs travaillant sur le **même code** ou projet pour télécharger et récupérer le code mis à jour, facilitant ainsi l'**intégration continue**. Le plugin **plugin Git** va fournir à Jenkins plusieurs fonctionnalités pour améliorer le flux de travail de développement avec GitHub.

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/install_github_integration.png" style="width:60%">
</p>

> Cliquez sur "**install without restart**". 

<div class="alert alert-warning">
Le téléchargement du plug-in prendra un certain temps en fonction de notre connexion Internet et sera installé automatiquement.
</div>
	
<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/download_githubintegration_done.png" style="width:60%">
</p>

Une fois terminé, le plugin sera disponible en option lors de la configuration des jobs.

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/github-logo.webp" style="width:30%">
</p>


## **B - Intégration de Jenkins avec GitHub**

### b.1 - Création du dépôt Github

Nous parlerons à présent du processus d'intégration de GitHub à Jenkins. Nous commencerons par créer un nouveau dépôt sur notre compte Github, si vous n'en avez pas, vous pouvez en créer un à l'adresse de [GitHub](https://github.com/signup).

Nous allons donc créer un dépôt afin de pouvoir versionner notre code source et le connecter à Jenkins. Allons sur Github créer un nouveau dépôt appelé `Jenkins-datascientest`, avec une visibilité `public`:

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/repo_github.png" style="width:60%">
</p>

Nous pouvons à présent créer notre dépôt en cliquant sur le bouton `Create repository`. Une fois sur l'interface de dépôt, nous pouvons aller sur les réglages du dépôt en cliquant sur `settings`.

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/setting_github.png" style="width:100%">
</p>

### b.2 - Qu'est-ce qu'un webhook ?

**Les Webhooks sont des notifications déclenchées par des événements**. Dans la plupart des cas, ils sont utilisés pour la communication entre les systèmes. C'est le moyen le plus simple de recevoir une alerte lorsque un évènement (tentative de connexion, mise à jour...) se passe dans un autre système.

**Comment fonctionnent les Webhooks ?**

Lorsque nous effectuons un retrait à l'aide d'un guichet automatique, la machine vérifie notre solde et nous donne le montant que nous avons demandé. Une fois cette opération effectuée, notre solde est mis à jour et ce changement déclenche une **action**. Ensuite, un SMS est envoyé avec les détails du retrait.

C'est ainsi que fonctionnent les **Webhooks**. Une action sert de **déclencheur** à une autre action. Le reste est une architecture populaire utilisée pour communiquer entre les systèmes. Un cas d'utilisation populaire consiste à connecter des services Web tels que GitHub et Slack.

Un Webhook est une **requête HTTP** qui transfère des données lorsqu'elle est déclenchée par un **événement** et transporte un **message** vers une destination telle qu'un SMS ou une alerte d'appel téléphonique.

Les Webhooks sont utilisés pour les notifications en **temps réel**, afin que votre système puisse être mis à jour dès que l'événement a lieu et ainsi permettre d'avoir un suivi granulaire de vos systèmes.

En termes plus techniques, la plupart des Webhooks sont configurés en tant que points de **rappel HTTP** définis par l'utilisateur. Ils nous permettent d'enregistrer une URL `http://` ou `https://` où les données d'événements peuvent être stockées aux formats [JSON](https://en.wikipedia.org/wiki/JSON) ou [XML](https://en.wikipedia.org/wiki/XML).

Nous pourrons faire ce que nous voulons avec les données que nous récupérons et stockons à partir d'un certain événement.

La mécanique de base des Webhooks consiste à envoyer une requête **HTTP** à l'URL spécifiée par l'utilisateur, ensuite, un webhook effectue un **callback HTTP** vers une URL qui doit être configurée par le système qui **reçoit** les données.

Cette URL de webhook est appelée **point de terminaison** de webhook. Les points de terminaison Webhook doivent être publics pour être accessibles, et il est important que cette URL appartienne au système **récepteur**. Le rappel est déclenché chaque fois qu'il y a un événement dont vous souhaitez informer un autre système.

Nous allons donc le mettre en place sur Github afin d'alerter notre instance de Jenkins.

Nous pouvons à présent cliquer sur `webhooks`.

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/github_webhook.png" style="width:100%">
</p>

Nous pouvons cliquer sur `Add Webhook`.

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/add_webhook.png" style="width:100%">
</p>

Dans le formulaire, nous devons remplir le champ `Payload URL`. Nous allons donc remplir ce champ avec la combinaison suivante :

- Votre url jenkins : `http://votreadesseip:8080/`
- L'endpoint `github-webhook`

Le contenu complet sera donc `http://votreadesseip:8080/github-webhook/`. Vous devrez remplacer `votreadresseip` par l'adresse IP de votre serveur.
<div class="alert alert-warning">
	Si vous travaillez en local et non sur la VM fournie par DataScientest et que vous ne souhaitez pas indiquer votre adresse IP personnelle, veuillez vous référérer à la partie complément de ce chapitre. 
</div>
Pour le champ `Content type`, nous choisirons `application/json`.

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/payload_url.png" style="width:100%">
</p>
A présent nous devons configurer les évènements qui alerterons Jenkins et déclencherons nos jobs de constructions.

Sur la partie `Which events would you like to trigger this webhook?`, nous choisirons `Let me select individual events` afin de choisir nous même les évènement déclencheurs.

Nous cocherons les cases suivantes :

- `Branch or tag creation`

- `Branch or tag deletion`

- `Packages`

- `Pull request review comments`

- `Pull requests`

- `Pull request reviews`

- `Pushes`

- `Registry packages`

Une fois toutes ces cases cochées, nous pouvons enregistrer notre Webhook en cliquant sur le bouton `Add Webhook`.

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/kubernetes.png" style="width:60%">
</p>

### Complément

Cette partie s'adresse aux personnes ne faisant pas les excercices sur la VM fournie par DataScientest.

Nous ne pouvons pas donner une adresse locale comme `localhost`. Nous allons pour cela passer par un tunnel ssh `qui` va nous donner une adresse publique. Nous allons utiliser [ngrok](https://ngrok.com/), un logiciel permettant de créer des tunnels sécurisés entre un serveur local et Internet. Il agit en tant que passerelle inversée, permettant à des applications exécutées localement sur votre ordinateur de recevoir des requêtes externes. 

> Téléchargez puis décompressez le fichier.

> Lancez l'exécutable `ngrok` puis dans le terminal de l'application, lancez la commande suivante :

```shell
ngrok http port-associé-à-Jenkins
```

Votre terminal devrait afficher un message similaire à l'image ci-dessous :

```shell
ngrok by @inconshreveable                                                                                                                                                                            (Ctrl+C to quit)

Session Status                online
Session Expires               1 hour, 59 minutes
Version                       2.3.40
Region                        United States (us)
Web Interface                 http://127.0.0.1:4040
Forwarding                    http://d4b48cd1f88c.ngrok.io -> http://localhost:8080
Forwarding                    https://d4b48cd1f88c.ngrok.io -> http://localhost:8080

Connections                   ttl     opn     rt1     rt5     p50     p90
                              0       0       0.00    0.00    0.00    0.00
```

> Copiez l'adresse commençant par `https`, puis rajoutez à la fin `/github-webhook/`, par exemple dans l'exemple ci-dessus, nous devrions avoir `https://d4b48cd1f88c.ngrok.io/github-webhook/`. Ensuite dirigez-vous dans la section _Webhook_ et placez l'adresse dans l'encadré _Payload Url_. Vous pouvez maintenant retourner aux intructions.

## **C - Credentials**
Sur Jenkins, les credentials font référence aux informations d'identification nécessaires pour accéder à différents services, systèmes ou environnements lors de l'exécution de pipelines ou de jobs.

Allons, à présent, créer nos éléments de connexion sur Jenkins. 

> Cliquez sur le bouton `Dashboard` afin de revenir sur le tableau de bord puis sur le menu `Manage Jenkins` et une fois sur cette vue, cliquez sur le menu `Manage Credentials` :

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/manage_credentials.png" style="width:100%">
</p>

> Cliquez ensuite sur `system` :

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/system.png" style="width:100%">
</p>

> Cliquez sur `Global credentials (unrestricted)` .

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/global.png" style="width:100%">
</p>

> Sur la nouvelle vue, cliquez sur le bouton `add credentials` :

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/add_credentials.png" style="width:100%">
</p>

Nous pouvons maintenant choisir le type de credentials. Examinons les différents types de credentials Jenkins :

<style type="text/css">
.tg  {border-collapse:collapse;border-color:#93a1a1;border-spacing:0;}
.tg td{background-color:#fdf6e3;border-color:#93a1a1;border-style:solid;border-width:1px;color:#002b36;
  font-family:Arial, sans-serif;font-size:14px;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{background-color:#657b83;border-color:#93a1a1;border-style:solid;border-width:1px;color:#fdf6e3;
  font-family:Arial, sans-serif;font-size:14px;font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-lboi{border-color:inherit;text-align:left;vertical-align:middle}
.tg .tg-isc8{background-color:#eee8d5;border-color:inherit;text-align:left;vertical-align:middle}
.tg .tg-g7sd{border-color:inherit;font-weight:bold;text-align:left;vertical-align:middle}
</style>
<table class="tg" style="undefined;table-layout: fixed; width: 1066px">
<colgroup>
<col style="width: 201.333333px">
<col style="width: 864.333333px">
</colgroup>
<thead>
  <tr>
    <th class="tg-g7sd">Type de Credentials</th>
    <th class="tg-g7sd">Description</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-isc8">Nom d'utilisateur et mot de passe</td>
    <td class="tg-isc8">Il s'agit d'un nom d'utilisateur et d'un mot de passe associés ou token à un compte particulier. Ces informations peuvent être utilisées pour s'authentifier sur des serveurs, des services ou des applications.</td>
  </tr>
  <tr>
    <td class="tg-lboi">SSH Username with Private Key</td>
    <td class="tg-lboi">Ce type de credentials est utilisé pour l'authentification SSH. Il comprend un nom d'utilisateur et une clé privée correspondante pour établir une connexion sécurisée à un serveur distant.</td>
  </tr>
  <tr>
    <td class="tg-isc8">Secret File</td>
    <td class="tg-isc8">Il s'agit d'un fichier contenant des informations sensibles, telles que des clés d'API ou des certificats, qui peuvent être utilisées par les jobs Jenkins.</td>
  </tr>
  <tr>
    <td class="tg-lboi">Secret Text</td>
    <td class="tg-lboi">Vous devez fournir un nom descriptif et la valeur secrète. Jenkins stocke ensuite cette valeur de manière sécurisée, en la chiffrant avant de l'enregistrer dans son système de stockage.</td>
  </tr>
  <tr>
    <td class="tg-isc8">Certificate</td>
    <td class="tg-isc8">Ce type de credentials est utilisé pour stocker des certificats numériques, tels que des certificats SSL/TLS.</td>
  </tr>
</tbody>
</table>

> Créez une variable de type `secret text` afin d'y définir le mot de passe utilisé par Jenkins pour pousser nos images au sein de Dockerhub. Nous appellerons cette variable `DOCKER_HUB_PASS`:

<div class="alert alert-info"><i class="icon circle info"></i>
Dans <code>secret</code> il faudra renseigner le mot de passe de votre compte dockerHub
</div>

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/secret_test.png" style="width:100%">
</p>

Ceci sera la liste de nos informations secretes :

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/variables_list.png" style="width:100%">
</p>


<br>


#%%

# III Jobs et Build 

## A - Projet freestyle


Nous allons nous lancer enfin dans la pratique de Jenkins en affichant le classique Hello World.

> Cliquez sur "Nouveau Item" (_New Item_) qui est la première option du dashboard. 

Nous arriverons alors sur la page des jobs Jenkins qui sont un ensemble donné de tâches qui s'exécutent **séquentiellement** tel que défini par l'utilisateur. Toute automatisation est implémentée dans Jenkins est un `Job` Jenkins. Ces travaux constituent une partie importante du processus de construction de Jenkins. Nous pouvons créer et construire des Jobs Jenkins pour tester et déployer notre application ou notre projet.
Il existe différents types de Job Jenkins disponibles à des fins différentes. En fonction de la complexité et de la nature de notre projet, nous pouvons choisir celui qui correspond le mieux à nos besoins.

Examinons brièvement les différents types de job à Jenkins :

<style type="text/css">
.tg  {border-collapse:collapse;border-color:#93a1a1;border-spacing:0;}
.tg td{background-color:#fdf6e3;border-color:#93a1a1;border-style:solid;border-width:1px;color:#002b36;
  font-family:Arial, sans-serif;font-size:14px;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{background-color:#657b83;border-color:#93a1a1;border-style:solid;border-width:1px;color:#fdf6e3;
  font-family:Arial, sans-serif;font-size:14px;font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-lboi{border-color:inherit;text-align:left;vertical-align:middle}
.tg .tg-isc8{background-color:#eee8d5;border-color:inherit;text-align:left;vertical-align:middle}
.tg .tg-g7sd{border-color:inherit;font-weight:bold;text-align:left;vertical-align:middle}
</style>
<table class="tg" style="undefined;table-layout: fixed; width: 1066px">
<colgroup>
<col style="width: 201.333333px">
<col style="width: 864.333333px">
</colgroup>
<thead>
  <tr>
    <th class="tg-g7sd">Type de Jobs</th>
    <th class="tg-g7sd">Description</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-isc8">Projet Freestyle</td>
    <td class="tg-isc8">C'est la fonctionnalité centrale et la plus largement utilisée dans Jenkins. Il s'agit d'un travail de build Jenkins disponible offrant plusieurs opérations. Grâce à cette option, vous pouvez créer et exécuter des pipelines ou des scripts de manière transparente.</td>
  </tr>
  <tr>
    <td class="tg-lboi">Projet Maven</td>
    <td class="tg-lboi">Si votre travail consiste à gérer et à créer des projets contenant des fichiers POM, vous préférez utiliser Maven Project pour créer des travaux dans Jenkins. En choisissant cette  option, Jenkins, par défaut, sélectionnera les fichiers POM, effectuera des configurations et exécutera des build. Un fichier POM (Project Object Model) est un élément central de la configuration d'un projet Maven, décrivant son contenu, ses dépendances et les actions à effectuer lors de sa construction. Un fichier POM est un fichier XML utilisé par Maven pour définir la configuration, les dépendances et la structure d'un projet logiciel Java.</td>
  </tr>
  <tr>
    <td class="tg-isc8">Pipeline</td>
    <td class="tg-isc8">Un travail basé sur un Jenkinsfile, offrant une approche plus puissante et flexible pour la création de pipelines et de flux de travail d'intégration continue et de déploiement continu (CI/CD).</td>
  </tr>
  <tr>
    <td class="tg-lboi">Projet multi-configuration</td>
    <td class="tg-lboi">Si vous travaillez sur un projet nécessitant plusieurs configurations, vous devez utiliser l'option "Projet multi-configuration". Cette option permet de créer plusieurs configurations pour tester dans plusieurs environnements.</td>
  </tr>
  <tr>
    <td class="tg-isc8">Organisation GitHub</td>
    <td class="tg-isc8">Cette option analyse le compte GitHub de l'utilisateur pour tous les référentiels d'une organisation spécifique, correspondant aux marqueurs définis pour automatiser les opérations associées.</td>
  </tr>
</tbody>
</table>

> Donnez un nom à votre projet, puis sélectionnez l'option `Construire un projet free-style` (_Freestyle project_) et appuyez sur le bouton **OK**.

Vous devriez obtenir la page suivante :

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_fr/desc_projet.png" style="width:75%">
</p>

Vous disposez de plusieurs onglets, qui vous renvoient à la section associée et vous permettent de configurer votre projet Jenkins. Vous pouvez ajouter une simple description, l'associer avec un repo Git avec le _Source Code Management_ , automatiser les _build_ du projet et réaliser des actions selon si le build a été un succès ou un échec.

<div class="alert alert-info"><i class="icon circle info"></i>
Si vous observez bien, vous apercevez un point d'interrogation à la droite de chaque proposition, qui comme attendu fournit une explication, n'hésitez pas à les consulter.
</div>

Ici, nous voulons simplement afficher un _Hello World_ , pour cela nous allons sur la section _Build_, qui va retranscrire les actions que nous voulons faire. Nous choisissons l'action depuis le bouton _Add build step_. Nous avons plusieurs options, dans notre cas, nous prenons _Execute shell_.

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_fr/build_2.png" style="width:75%">
</p>

Comme nous le montre l'image, il suffit d'écrire ce que nous aurions écrit dans la console, il est aussi possible d'écrire d'autres commandes telles que `java -version` qui nous renseigne sur la version de java utilisée. Il est possible aussi de rajouter des blocs build supplémentaires à l'aide du bouton _Add build step_.

<div class="alert alert-info">
<i class="fa fa-info-circle"></i>
Des variables d'environnement sont aussi disponibles depuis la route /env-vars.html/, vous pouvez les utiliser pour vos scripts et les afficher via un <code>echo</code>.
</div>

Une fois cela fait, cliquez sur le bouton Save et cela vous renvoie à la page principale du projet.

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_fr/page_garde.png" style="width:65%">
</p>

Sur le Dashboard à votre gauche, cliquez sur le bouton "Lancer un Build" (_Build Now_), cela va exécuter les actions que vous avez définies dans le _Add Build Step_. En dessous du Dashboard se trouve une section _Build History_ qui est un historique des Build. Une fois, le job lancé, vous devrez pouvoir observer un #1 associé avec un tick vert entouré, si le build avait échoué, nous aurions eu une croix rouge entouré. En cliquant sur le #1, cela vous renvoie aux informations relatives au build.

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_fr/after_build1.png" style="width:65%">
</p>

Sur cette nouvelle page, le dashboard est différent et il y apparaît un onglet _Console Output_, où se trouve les sorties des actions demandées, nous obtenons un Hello World couplé avec la version de Java utilisée par Jenkins.

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_fr/resultat.png" style="width:65%">
</p>

Bravo, nous avons réalisé notre premier projet sur Jenkins!

<div class="alert alert-info"><i class="icon circle info"></i>
Jenkins n'est pas utilisable que depuis son interface web. Il y a aussi des lignes de commandes dont vous pouvez retrouver l'utilisation depuis la route <code>/cli</code>. Comme avec Git, il est parfois plus rapide de passer par ces lignes de commandes, mais moins facile d'accès que depuis l'interface web. Pour pouvoir utiliser ces lignes de commandes, vous devez installer le langage Java.
</div>



## **B - Pipeline Jenkins**

<br>

Précédemment, nous avons vu la fonctionnalité Freestyle Project nonobstant il ne s'agit pas de l'application classique de Jenkins. De même, nous avions mis le SCM (Source Code Management) à *None* bien que ce n'est rarement le cas. Une des fonctionnalités principales de Jenkins est le **Pipeline**. Dans ce module, nous utiliserons le logiciel de versioning Git.

## **A - Présentation**

Dans Jenkins, un pipeline est défini comme une **série d'événements** ou de tâches qui sont interconnectés et qui s’exécutent dans un ordre particulier. En d'autres termes, le pipeline Jenkins est un ensemble de **modules** ou de **plugins** qui permettent la mise en œuvre et l'**intégration** ou **livraison continue** au sein de Jenkins.

Le pipeline Jenkins dispose d'un système d'**automatisation** extensible pour créer des pipelines de distribution de "modèles" via le langage spécifique au domaine (DSL) utilisé dans le pipeline. 

Il existe quatre états de livraison continue dans le pipeline Jenkins :

> - Construire (build)
> - Déployer (dans un environnement de test)
> - Tester 
> - Déployer (dans un environnement de production)

## **B - Pourquoi utiliser Jenkins Pipeline ?**

Jenkins joue un rôle important dans la fourniture d'applications ou de produits de haute qualité. Nous savons maintenant que Jenkins s'est avéré être utile pour l'intégration continue, des tests continus et de la livraison continue.

Il utilise une fonctionnalité appelée **pipeline Jenkins** pour la livraison continue, qui est essentiellement la possibilité de publier des applications régulièrement à un intervalle. Ce processus garantit la **répétabilité** lors de l'intégration et que le logiciel est toujours prêt pour la **production**.

### Avantages du pipeline Jenkins

Le point culminant du pipeline Jenkins est qu'il offre la fonctionnalité permettant de définir la **configuration** et le code complets du flux de déploiement. Il indique que tous les travaux Jenkins standard peuvent être écrits manuellement sous la forme d'un **script** et peuvent être gérés avec un système de **contrôle de version**.

Il s'agit essentiellement de suivre la discipline du **"pipeline as code"**. Ainsi, au lieu de créer plusieurs tâches pour chaque processus, cela nous permet de coder l'ensemble du flux de travail et de le placer dans un **fichier** Jenkins.

Vous trouverez ci-dessous quelques-unes des raisons que l'on pourrait envisager avant d'utiliser le pipeline Jenkins pour l'automatisation des tests Jenkins (avec **Selenium** par exemple) :

- Le code est stocké sous la forme d'un fichier texte appelé **"Jenkinsfile"** qui peut être scanné dans **Source Code Management**.

- Il prend en charge les pipelines complexes en ajoutant des boucles **conditionnelles**, des fourches ou des opérations de **jointure** et en autorisant des tâches d'exécution parallèles.

- Il améliore l'expérience utilisateur en intégrant les **commentaires** des utilisateurs dans le pipeline.

- Il est résilient en termes de **redémarrage** non planifié principal de Jenkins.

- Il peut reprendre à partir des **points de contrôle** enregistrés.

- Il peut incorporer plusieurs **plugins** et compléments supplémentaires.

Jenkins Pipeline est une solution d'automatisation qui vous permet de créer des pipelines simples ou complexes (modèles) via le DSL utilisé dans chaque pipeline. Jenkins propose deux manières de développer un pipeline : scripté et déclaratif.Traditionnellement, les tâches Jenkins étaient créées à l'aide de l'interface utilisateur Jenkins, appelées tâches FreeStyle.

Avec Jenkins 2.0, Jenkins a introduit une nouvelle façon de créer des travaux en utilisant la technique appelée pipeline en tant que code (Pipeline as Code). Dans la technique **du pipeline en tant que code**, les tâches sont créées à l'aide d'un fichier de script contenant les étapes à exécuter par la tâche. Dans Jenkins, ce fichier scripté s'appelle **Jenkinsfile**.

## **C - Jenkinsfile**

### c.1 - Introduction

Il s'agit d'un fichier texte qui stocke l'ensemble du **processus sous forme de code** dans notre machine locale. Il peut être examiné dans une plate-forme de gestion de code source (SCM) telle que Git. Il est essentiel car il aide les développeurs à afficher, modifier et tester le code chaque fois que nécessaire.

Le fichier Jenkins est écrit à l'aide du langage spécifique au domaine Groovy et peut être généré à l'aide d'un éditeur de texte ou de l'onglet de configuration de l'instance Jenkins.

Il existe deux types différents dans lesquels le pipeline Jenkins peut être construit. Ce sont les syntaxes-

- Syntaxe de pipeline déclarative
- Syntaxe de pipeline scriptée

Les pipelines déclaratifs sont une fonctionnalité relativement nouvelle qui prend en charge le concept de pipeline de code. Il permet la lecture et l'écriture du code du pipeline. Ce code est écrit dans un fichier Jenkins, qui peut être testé dans un outil tel que Git pour le contrôle de source.

Le pipeline **scripté** est une méthode typique d'écriture de code. Le fichier Jenkins est écrit sur l'instance d'interface utilisateur Jenkins dans ce pipeline.

Bien que ces deux pipelines soient basés sur Groovy, le pipeline scripté utilise des syntaxes basées sur Groovy plus strictes. En effet, il s'agissait du premier pipeline de fondation groovy créé pour être utilisé. Comme ce script Groovy n'était généralement pas adapté à tous les utilisateurs, il a introduit le pipeline **déclaratif** pour fournir une syntaxe Groovy plus simple et plus flexible.

Le pipeline déclaratif est défini dans un bloc **`pipeline`**, tandis que le pipeline scripté est défini dans un bloc **`node`**.

### c.2 - Qu'est-ce que le pipeline scripté Jenkins ?

Les pipelines Jenkins sont traditionnellement écrits sous forme de pipelines scriptés. Idéalement, le pipeline scripté est stocké dans l'interface utilisateur Web Jenkins en tant que fichier Jenkins. Le script de pipeline scripté de bout en bout est écrit en Groovy :

- Il nécessite une connaissance de la programmation Groovy comme prérequis.

- Le Jenkinsfile commence par le mot **node**, rappelions que c'est un node worker qui execute la charge de travail.

- Il peut contenir des constructions de programmation standard comme le bloc **if-else**, le bloc **try-catch**, etc.

Un pipeline scripté simple pourrait ressembler à la syntaxe suivante :

```shell
node {
     	stage('Greeting')
     		{
     		echo 'hello Datascientest'
         	}
       }
```

<br>

### c.3 - Qu'est-ce que le pipeline déclaratif Jenkins ?

Le sous-système **déclaratif** de Pipeline dans Jenkins Pipeline est relativement nouveau et fournit une syntaxe simplifiée et opiniâtre en plus des sous-systèmes Pipeline.

- Le dernier ajout à la technique de création d'emplois de pipeline Jenkins.

- Le pipeline déclaratif Jenkins doit utiliser les constructions prédéfinies pour créer des pipelines. Par conséquent, il n'est pas flexible en tant que pipeline scripté.

- Jenkinsfile commence par le mot `pipeline`.

```shell
pipeline {
    stages {
     	stage('Greeting'){
     	    echo 'hello Datascientest'
 	}
    }
}
```

Le pipeline déclaratif Jenkins devrait être le moyen préféré de créer un Job Jenkins car il offre un riche ensemble de fonctionnalités, une courbe d'apprentissage réduite et aucun prérequis pour apprendre un langage de programmation comme Groovy juste pour écrire du code de pipeline.

Nous pouvons également valider la syntaxe du code de pipeline déclaratif avant d'exécuter le Job. Cela permet d'éviter de nombreux problèmes d'exécution avec le script de construction.

## **D - Création d'un pipeline**

Nous allons, dès à présent, créer un pipeline déclaratif qui va être composé de trois phases: *Building*, *Testing* et *Deploying*. Nous devons tout d'abord réaliser un nouveau projet.

> Dirigeons nous sur `New Item` qui est la première option du dashboard, comme lorsque nous avions fait le Freestyle Project en donnant le nom `datascientest-ci-cd` à notre projet.

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/new_item.png" style="width:60%">
</p>

Nous devons donner un nom à notre projet et ensuite choisir un type de projet.

Nous appellerons `datascientest-ci-cd` et nous choisirons le type `pipelines` car nous partirons de notre fichier `Jenkinsfile` afin de décrire les tâches à automatiser :

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/pipeline_projet.png" style="width:60%">
</p>

En cliquant sur le bouton `OK`, notre Job Jenkins sera prêt à être configuré. Nous pouvons créer autant de Jobs Jenkins selon nos besoins. La procédure de création de Job reste la même quelque soit le type de Job. Seuls les paramètres de configurations pourront varier en fonction du type de Jobs.

### **B - Configuration de la gestion du code source**

Nous commençons par remplir la section "Description" qui est un simple champ dans lequel nous remplissons la description sommaire de notre Job :

```shell
Ceci est notre projet Jenkins ci/cd chez Datascientest
```

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/description_job.png" style="width:60%">
</p>

Outre le champ Description, d'autres options sont disponibles dans la section **Général**, parlons de certains champs du formulaire qui sont des cases à cocher :

<style type="text/css">
.tg  {border-collapse:collapse;border-color:#93a1a1;border-spacing:0;}
.tg td{background-color:#fdf6e3;border-color:#93a1a1;border-style:solid;border-width:1px;color:#002b36;
  font-family:Arial, sans-serif;font-size:14px;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{background-color:#657b83;border-color:#93a1a1;border-style:solid;border-width:1px;color:#fdf6e3;
  font-family:Arial, sans-serif;font-size:14px;font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-cly1{text-align:left;vertical-align:middle}
.tg .tg-lboi{border-color:inherit;text-align:left;vertical-align:middle}
.tg .tg-isc8{background-color:#eee8d5;border-color:inherit;text-align:left;vertical-align:middle}
.tg .tg-g7sd{border-color:inherit;font-weight:bold;text-align:left;vertical-align:middle}
</style>
<table class="tg" style="undefined;table-layout: fixed; width: 1086px">
<colgroup>
<col style="width: 205.333333px">
<col style="width: 880.333333px">
</colgroup>
<thead>
  <tr>
    <th class="tg-g7sd">Choix</th>
    <th class="tg-g7sd">Description</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-isc8">Discard old builds</td>
    <td class="tg-isc8">Si nous préférons supprimer les anciennes versions lors du lancement d'une nouvelle version, utilisez cette option.</td>
  </tr>
  <tr>
    <td class="tg-lboi">Do not allow concurrent builds</td>
    <td class="tg-lboi">Si nous préférons interdire les constructions simultanées.</td>
  </tr>
  <tr>
    <td class="tg-isc8">Pipeline</td>
    <td class="tg-isc8">Freestyle Project n'est souvent pas une  bonne option pour créer des Jobs Jenkins. Par conséquent, Pipeline est la meilleure option. Utilisez l'option Pipeline pour créer des tâches Jenkins, en particulier lorsque vous travaillez sur des activités de longue durée.</td>
  </tr>
  <tr>
    <td class="tg-lboi">GitHub project</td>
    <td class="tg-lboi">Si nous avons du code source au sein d'un dépôt GitHub et que nous souhaitons l'utiliser dans notre job Jenkins, utilisons l'option Projet GitHub. Lors de la sélection de cet avis, assurons-nous de spécifier l'URL GitHub.</td>
  </tr>
  <tr>
    <td class="tg-isc8">This project is parameterized</td>
    <td class="tg-isc8">Cette option nous permet de créer des builds avec différents paramètres qui seraient transmis lors de l'exécution. Chaque paramètre aura un nom et une valeur spécifiques.</td>
  </tr>
  <tr>
    <td class="tg-cly1">Throttle builds</td>
    <td class="tg-cly1">Choisissez l'option Throttle Builds lorsque vous travaillez sur un projet avec un temps minimum requis entre les builds en fonction du taux maximum attendu.</td>
  </tr>
</tbody>
</table>

Une fois que nous avons ajouté la description, passons à la section suivante.

### **C - Projet Github**

Nous devons cocher la case `GitHub project` et remplir le formulaire qui apparaîtra en utilisant l'url de notre dépôt git:

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/github_project.png" style="width:60%">
</p>

Jenkins utilise Git comme outil de gestion de version de code source. Après avoir terminé la gestion du code source, nous allons ensuite vérifier l'option `Jenkins Build Triggers`.

### **D - Déclencheur Jenkins**

Avant l'étape de construction de Jenkins, le déclenchement du travail est essentiel. La création de déclencheurs dans Jenkins nous permet d'exécuter une tâche à **chaque occurrence**. En d'autres termes, chaque fois qu'il y a un changement dans le code source, Jenkins déclenche automatiquement une **construction** avec la mise à jour la plus récente.

Sur la partie `Build Triggers` du Job Jenkins, plusieurs options sont disponibles. Analysons chacunes en détail:

<style type="text/css">
.tg  {border-collapse:collapse;border-color:#93a1a1;border-spacing:0;}
.tg td{background-color:#fdf6e3;border-color:#93a1a1;border-style:solid;border-width:1px;color:#002b36;
  font-family:Arial, sans-serif;font-size:14px;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{background-color:#657b83;border-color:#93a1a1;border-style:solid;border-width:1px;color:#fdf6e3;
  font-family:Arial, sans-serif;font-size:14px;font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-cly1{text-align:left;vertical-align:middle}
.tg .tg-lboi{border-color:inherit;text-align:left;vertical-align:middle}
.tg .tg-isc8{background-color:#eee8d5;border-color:inherit;text-align:left;vertical-align:middle}
.tg .tg-g7sd{border-color:inherit;font-weight:bold;text-align:left;vertical-align:middle}
</style>
<table class="tg" style="undefined;table-layout: fixed; width: 1086px">
<colgroup>
<col style="width: 205.333333px">
<col style="width: 880.333333px">
</colgroup>
<thead>
  <tr>
    <th class="tg-g7sd">Choix</th>
    <th class="tg-g7sd">Description</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-isc8">Build after other projects are built</td>
    <td class="tg-isc8">Avec cette option, une nouvelle génération n'est déclenchée qu'après l'exécution réussie d'autres générations.</td>
  </tr>
  <tr>
    <td class="tg-lboi">Build periodically</td>
    <td class="tg-lboi">Si vous choisissez d'exécuter des builds périodiquement, choisissez cette option. Assurez-vous de spécifier l'heure à laquelle vous souhaitez que la génération démarre. Jenkins mettra en place une sorte de CRON afin de construire périodiquement notre Job</td>
  </tr>
  <tr>
    <td class="tg-isc8">GitHub Pull Requests</td>
    <td class="tg-isc8">L'utilisation de cette option de déclencheur de génération permet l'intégration avec les activités GitHub Pull Requests and Issues. De plus, il lance des exécutions en sortie.</td>
  </tr>
  <tr>
    <td class="tg-lboi">GitHub hook trigger for GITScm polling</td>
    <td class="tg-lboi">Utilisez cette option si vous devez exécuter vos builds à l'aide des webhooks GitHub.</td>
  </tr>
  <tr>
    <td class="tg-isc8">Poll SCM</td>
    <td class="tg-isc8">Semblable à l'option de déclencheur de génération périodique de Jenkins Build, nous devons spécifier une minuterie pour Poll SCM. Cependant, l'option SCM dans Jenkins exécute la génération uniquement lorsqu'il y a un changement de code pendant cette période.</td>
  </tr>
  <tr>
    <td class="tg-cly1">Trigger builds remotely</td>
    <td class="tg-cly1">Choisissez les builds déclenchés à distance si vous avez besoin de déclencher de nouveaux builds à l'aide d'une URL dédiée.</td>
  </tr>
</tbody>
</table>

Nous devons cocher la case `GitHub hook trigger for GITScm polling` pour que GitHub puisse envoyer des Webhooks qui déclencherons la construction de notre Job.

Ensuite, nous devons spécifier le chemin du fichier **Jenkinsfile** depuis notre dépôt. Jenkins essaiera par défaut de le récupérer à la racine de ce dernier. Nous devons donc lui renseigner l'URL `SSH`.

Jenkins essaiera immédiatement de vérifier s'il peut récupérer le fichier depuis notre dépôt avant de sauvegarder le projet. 

Pour le cours, nous créerons le fichier `Jenkinsfile` au sein de notre dépôt Github

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/webhook_pipeline.png" style="width:60%">
</p>

Nous devons ensuite spécifier le dépôt dans lequel se trouve le fichier `Jenkinsfile` ainsi que le chemin ou le trouver dans le dépôt. Jenkins essaiera par défaut de récupérer le Jenkinsfile à la racine de notre dépôt Github. Nous devons récupérer l'URL en SSH de notre dépôt et le passer à Jenkins.

Jenkins essaiera immédiatement de vérifier s'il peut bien récupérer le fichier dans le dit dépôt avant de sauvegarder le projet . Pour le cours, nous créerons le fichier `Jenkinsfile` depuis au sein de notre dépôt Github.

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/jenkinsfile_from_scm.png" style="width:60%">
</p>

Nous choisissons Git comme `SCM` et définissons le chemin de notre dépôt Github . Nous définissons également sur `None` le champ Credentials car notre dépôt est public et Jenkins pourra récupéré le fichier `Jenkinsfile` sans avoir besoin de s'authentifier.

Nous laisserons le reste des champs par défaut et nous définirons dans le champ `Script Path` la valeur Jenkinsfile puisse que le fichier `Jenkinsfile` se trouvera à la racine de notre projet. S'il avait été dans un répertoire appelé `pipeline`, nous aurions rempli à la place `pipeline/Jenkinsfile`.

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/jenkinsfile_path.png" style="width:60%">
</p>

Une fois terminé, nous pouvons sauvegarder notre travail en cliquant sur le bouton `Save`.


## **D - Syntaxe déclarative du pipeline Jenkins**

### d.1 - Stages et Stage

La section `stages` permet de générer différentes étapes sur le pipeline qui seront visualisées sous la forme de différents segments lors de l'exécution de la tâche.

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/jenkins-stages.jpg" style="width:60%">
</p>

Jenkins divise graphiquement l'exécution du pipeline en fonction des étapes définies et affiche leur durée et si elle a réussi ou non. La directive `stage` va dans la section `stages` et devrait contenir une directive [steps](https://docs.cloudbees.com/docs/admin-resources/latest/pipeline-syntax-reference-guide/declarative-pipeline#steps), une directive `agent` facultative ou d'autres directives spécifiques à une étape.

En pratique, tout le travail réel effectué par un Pipeline sera enveloppé dans une ou plusieurs directives `stage`.

```groovy
pipeline {
	agent any
	stages {
		stage ('build') {
			...
		}
		stage ('test: integration-&-quality') {
			...
		}
		stage ('test: functional') {
			...
		}
		stage ('test: load-&-security') {
			...
		}
		stage ('approval') {
			...
		}
        	stage ('deploy:dev') {
			...
		}
         stage ('deploy:staging') {
			...
		}
		stage ('deploy:prod') {
			...
		}
	}
}
```

> Créez votre premier pipeline avec trois stages nommés `Building`, `Testing` et `Deploying` 

%%SOLUTION%%
```groovy
pipeline {
    stages {
        stage('Building') {

        }
        stage('Testing') {

        }
	stage('Deploying') {

        }
    }
}
```
%%SOLUTION%%


<br>

### d.2 - Steps

Il s'agit d'une séquence d'une ou plusieurs directives d'étape, la section `stages` est l'endroit où se situera l'essentiel du job décrit par un Pipeline. Au minimum, il est recommandé de contenir au moins une directive `steps` pour chaque partie distincte du processus de livraison continue, telle que `Build`, `Test` et `Deploy`.

```groovy
pipeline {
    agent any
    stages {
        stage('Love') {
            steps {
                echo 'I love Datascientest'
            }
        }
    }
}
```

Pour Linux et MacOS, `sh` est pris en charge. Si nous voulons enchaîner plusieurs commandes, nous pouvons utiliser `sh'''` de la façon suivante :

```groovy
steps {
    sh 'echo "I love Datascientest"'
    sh '''
    echo "A multiline step"'
    cd /tests/results
    ls -lrt
    '''
}
```

Pour Windows, bat ou powershell peut être utilisé de la façon suivante :

```groovy
steps {
    bat "mvn clean test -Dsuite=SMOKE_TEST -Denvironment=QA"
    powershell ".\funcional_tests.ps1"
}
```

<br>

> En ajoutant une section `steps` dans chacune des trois stages, effectuez les commandes suivantes:
> Dans la phase Building, vous devez installer les librairies contenues dans le fichier requirements.txt
> Dans la phase Testing, vous devez lancer les tests unitaires

%%SOLUTION%%

```groovy
pipeline {
    stages {
        stage('Building') {
            steps {
	    	sh 'pip install -r requirements.txt'
            }
        }
        stage('Testing') {
            steps {
	    	sh 'python -m unittest'
            }
        }
	stage('Deploying') {
            steps{

            }
        }
    }
}
```
%%SOLUTION%%

</br>


### d.7 - script

L' étape `script` prend un bloc de pipeline scripté et l'exécute dans le pipeline déclaratif. Cette étape est utilisée pour ajouter des phrases de pipeline scripté dans une phrase déclarative, offrant ainsi encore plus de fonctionnalités. Cette étape doit être incluse au niveau `stage`.

Plusieurs fois, des blocs de scripts peuvent être utilisés sur différents projets. Ces blocs vous permettent d'étendre les fonctionnalités de Jenkins et peuvent être implémentés en tant que bibliothèques partagées. Plus d'informations à ce sujet peuvent être trouvées sur [les bibliothèques partagées Jenkins](https://jenkins.io/doc/book/pipeline/shared-libraries/).

De plus, les bibliothèques partagées peuvent être importées et utilisées dans le bloc **"script"**, étendant ainsi les fonctionnalités du pipeline.

```groovy
pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                echo 'Testing schools'
                script {
                    def schools = ['Datascientest', 'DevUniversity']
                    for (int i = 0; i < schools.size(); ++i) {
                        echo "Testing the ${schools[i]} school"
                    }
                }
            }
        }
    }
}
```

> Dans la phase Deploying, faites une section script dans lequel vous allez créer une image Docker à partir du Dockerfile et lancer le conteneur Docker

%%SOLUTION%%

```groovy
pipeline {
    stages {
        stage('Building') {
            steps {
	    	sh 'pip install -r requirements.txt'
            }
        }
        stage('Testing') {
            steps {
	    	sh 'python -m unittest'
            }
        }
	stage('Deploying') {
            steps{
	    	script {
		sh '''
		docker build -t shinbi/mlops_tp5:latest .
		docker run -d -p 8000:8000 shinbi/mlops_tp5:latest
		'''
		}
            }
        }
    }
}
```
%%SOLUTION%%

<br>

### d.1 - Agent

Jenkins offre la possibilité d'effectuer des builds distribués en les déléguant à des nœuds "agents". Cela vous permet d'exécuter plusieurs projets avec une seule instance du serveur Jenkins, tandis que la **charge de travail** est distribuée à ses **agents**. Les détails sur la configuration d'un mode maître/agent sortent du cadre de ce cours.

Veuillez vous référer aux [versions distribuées de Jenkins](https://wiki.jenkins.io/display/JENKINS/Distributed+builds#Distributedbuilds-Nodelabelsforagents) pour plus d'informations.

Les agents doivent être **étiquetés** afin qu'ils puissent être facilement identifiés les uns des autres. Par exemple, les nœuds peuvent être étiquetés par leur plate-forme (Linux, Windows, etc.), par leurs versions ou par leur emplacement.
La section **"agent"** configure sur quels nœuds le pipeline peut être exécuté. Spécifier **"agent any"** signifie que Jenkins exécutera le travail sur n'importe lequel des nœuds disponibles.

Ce mot clé peut être spécifiée au niveau d'un stage, d'une étape (**steps**) ou au niveau plus global dans tout le Pipeline et désigne les agents utilisés par Jenkins pour exécuter le Job en cours.

```groovy
pipeline {
    agent any // means any agent
    stages {
        stage('Greeting') {
            steps {
                echo 'Hello Datascientest'
            }
        }
    }
}
```

Afin de prendre en charge la grande variété de cas d'utilisation, la section `agent` prend en charge quelques types de paramètres différents. Ces paramètres peuvent être appliqués au niveau supérieur du bloc `pipeline` ou dans chaque directive `stage`.

- `any`: Exécutez le Pipeline, ou l'étape, sur n'importe quel agent disponible.

- `none`: Lorsqu'il est appliqué au niveau supérieur du bloc `pipeline`, aucun agent global ne sera alloué pour l'ensemble de l'exécution du Pipeline et chaque section `stage` devra contenir sa propre section `agent`.

- `label`: Exécute le pipeline, ou l'étape, sur un agent disponible dans l'environnement Jenkins avec l'**étiquette** fournie.

Exemple : `agent { label 'datascientest1' }`.

Il est également possible de définir plusieurs label et de faire un **"ou"** logique : `agent { label 'datascientest1 || datascientest2' }`.

Mais aussi un **"et"** : `agent { label 'datascientest1 || datascientest2' }` en fonction du besoin.

- `node`: désigne un noeud spécifique sur lequel nous voulons exécuter notre Job.

- `docker` : Exécute le pipeline, ou l'étape, avec le conteneur donné qui sera provisionné dynamiquement.

```shell
agent {
    docker {
        image 'gradle:6.9-alpine'
        label 'datascientest-gradle'
        args  '-v /tmp:/tmp'
    }
}
```

> Ajoutez un agent de type `Any` à votre pipeline

%%SOLUTION%%

```groovy
pipeline {
    agent any
    stages {
        stage('Building') {
            steps {
	    	sh 'pip install -r requirements.txt'
            }
        }
        stage('Testing') {
            steps {
	    	sh 'python -m unittest'
            }
        }
	stage('Deploying') {
            steps{
	    	script {
		sh '''
		docker build -t shinbi/mlops_tp5:latest .
		docker run -d -p 8000:8000 shinbi/mlops_tp5:latest
		'''
		}
            }
        }
    }
}
```
%%SOLUTION%%

<br>


### d.2 - Environment

La directive `environment` spécifie une séquence de paires clé-valeur qui seront définies comme des variables d'environnement pour toutes les étapes, ou des étapes spécifiques à une étape, selon l'emplacement de la directive `environment` dans le Pipeline. Cette directive peut être définie à la fois au niveau de l'étape ou du pipeline, ce qui déterminera la portée de ses définitions.

Lorsque **"environnement"** est utilisé au niveau **"pipeline"**, ses définitions seront valides pour toutes les étapes du pipeline. Si, au contraire, il est défini dans une **"étape"**, il ne sera valable que pour l'étape en question.

Cette directive prend en charge une méthode d'assistance spéciale `credentials()` qui peut être utilisée pour accéder aux informations d'identification prédéfinies par leur identifiant dans l'environnement Jenkins. Pour les informations d'identification de type `text secret`, la méthode `credentials()` garantira que la variable d'environnement spécifiée contient le contenu du texte secret.

Pour l'appel des variables dans le code du Jenkinsfile, nous devrons y ajouter le préfixe `$` juste avant le nom de la variable.

```groovy
// at the pipeline and stage level
pipeline {
    agent any
    environment {
         nom = 'datascientest'
    }
    stages {
        stage('Example') {
            environment {
                AN_ACCESS_KEY = credentials('datascientest-secret')  // variable secret
            }
            steps {
                sh 'print $nom' // variable call
            }
        }
    }
}
```

Au niveau `pipeline` uniquement :

```groovy
pipeline {
	agent any
	environment {
		OUTPUT_PATH = './outputs/'
	}
	stages {
		stage ('build') {
			...
		}
	...
	}
}
```

Ici, `environment` est utilisé à un niveau d'un `stage` uniquement :

```groovy
pipeline {
	agent any
	stages {
		stage ('build') {
	environment {
		OUTPUT_PATH = './outputs/'
	}
	...
		}
		...
	}
}
```

> Dans votre pipeline, créez une variable nommée `dockerhub` qui va prendre en valeur les identifiants dockerhub que nous avons créé précédemment dans les credentials. Ces informations peuvent être retrouver grâce à la fonction `credentials()` qui prend en entrée, l'id du credentials jenkins

%%SOLUTION%%

```groovy
pipeline {
    agent any
    environment {
    	dockerhub = credentials('docker_jenkins')
    }
    stages {
        stage('Building') {
            steps {
	    	sh 'pip install -r requirements.txt'
            }
        }
        stage('Testing') {
            steps {
	    	sh 'python -m unittest'
            }
        }
	stage('Deploying') {
            steps{
	    	script {
		sh '''
		docker build -t shinbi/mlops_tp5:latest .
		docker run -d -p 8000:8000 shinbi/mlops_tp5:latest
		'''
		}
            }
        }
    }
}
```
%%SOLUTION%%

<br>


### d.3 - triggers

La directive `triggers` définit les manières automatisées de relancer le Pipeline. Pour les pipelines qui sont intégrés à une source telle que **GitHub** ou **Bitbucket**, cette directive peut ne pas être nécessaire car l'intégration basée sur les webhooks sera probablement déjà présente.

Actuellement, les deux déclencheurs disponibles sont `cron` et `pollSCM`.

**cron**: Accepte une chaîne de style cron pour définir un intervalle régulier auquel le Pipeline doit être re-déclenché, par exemple :`triggers { cron('H 4/* 0 0 1-5') }`

```shell
pipeline {
    agent any
    triggers {
    ////Exécute les jours de la semaine toutes les quatre heures à partir de la minute 0
cron('0 */4 * * 1-5')
    }
    stages {
        stage('greeting Datascientest') {
            steps {
                echo 'Hello Datascientest'
            }
        }
    }
}
```

**pollSCM** : Accepte une chaîne de style cron pour définir un intervalle régulier auquel Jenkins doit vérifier les nouvelles **modifications** de source. Si de nouvelles modifications existent, le Pipeline sera réenclenché.

```groovy
pipeline {
agent any
triggers {
	//Query the source code repository on weekdays every four hours starting at minute 0
pollSCM('0 */4 * * 1-5')
}
stages {
...
}
}
```

**upstream** : exécute des jobs si des jobs précédents ont été exécutés avec succès.

```groovy
pipeline {
    agent any
        triggers {
            //Execute when either job7 or job10 are successful
        upstream(upstreamProjects: 'job7, job10', threshold: hudson.model.Result.SUCCESS)
        }
        stages {
       ...
        }
}
```

<br>

### d.4 - post

La section `post` définit les actions qui seront exécutées à la fin de l'exécution du pipeline. Un certain nombre de blocs de conditions de publication supplémentaires sont pris en charge dans la `post` section : `always`, `changed`, `failure`, `success` et `unstable`.

Ces blocs permettent l'exécution d'étapes à la fin de l'exécution du Pipeline et en fonction de l'**état** de cette Pipeline.

#### Conditions :

- `always` : Exécuter quel que soit le statut d'achèvement de l'exécution du Pipeline.

- `changed` : Exécuter uniquement si l'exécution actuelle du Pipeline a un statut différent de celui du Pipeline précédemment terminé.

- `failure` : Ne s'exécute que si le Pipeline actuel a un statut "en échec", généralement indiqué dans l'interface utilisateur Web par une indication rouge.

- `success` : Ne s'exécute que si le pipeline actuel a un statut "succès", généralement indiqué dans l'interface utilisateur Web par une indication bleue ou verte.

- `unstable` : Ne s'exécute que si le Pipeline actuel a un statut "instable", généralement causé par des échecs de test, des violations de code, etc. Généralement signalé dans l'interface utilisateur Web par une indication jaune.

```groovy
pipeline {
    agent any
    stages {
        stage('Greeting') {
            steps {
                echo 'Hello Datascientest'
            }
        }
    }
    post {
        always {
            echo 'I will always say Hello Datascientest!'
        }
    }
}
```

Les sections de publication peuvent être ajoutées au niveau du pipeline ou sur chaque bloc `stage` et les phases qui y sont incluses sont exécutées une fois le stage ou le pipeline terminé.

Étant donné que les phrases incluses dans un bloc de publication de pipeline seront exécutées à la fin du script, des tâches de nettoyage ou des notifications, entre autres, peuvent être effectuées ici :

```groovy
pipeline {
    agent any
    stages {
        stage('Greeting Datascientest') {
            steps {
                // Steps here
            }
        }
    }
    post {
        always {
            echo "Pipeline finished Greeting datascientest"
            sh "./datascientest-clean.sh"
        }
    }
}
```

<br>


### d.8 - Input

La directive `input` est définie au niveau du `stage` et fournit la fonctionnalité pour demander une entrée. L'étape sera mise en pause jusqu'à ce qu'un utilisateur la confirme manuellement.

Les options de configuration suivantes peuvent être utilisées pour cette directive :

- `message` : il s'agit d'une option obligatoire dans laquelle le message à afficher pour l'utilisateur est spécifié.

- `id` : identifiant facultatif de l'entrée. Par défaut, le nom "étape" est utilisé.

- `ok` : texte facultatif pour le bouton OK.

- `submitter`: liste facultative d'utilisateurs ou de noms de groupes externes autorisés à soumettre l'entrée. Par défaut, n'importe quel utilisateur est autorisé.

- `submitterParameter` : nom facultatif d'une variable d'environnement à définir avec le nom de l'émetteur, s'il est présent.

- `parameters `: liste facultative de paramètres à fournir par le demandeur.

```groovy
pipeline {
	agent any
	stages {
		stage ('build') {
            input{
                message "Press Ok to continue Datascientest"
                submitter "user1,user2"
                parameters {
                    string(name:'username', defaultValue: 'user', description: 'Username of the user  pressing Ok')
                }
	}
	steps {
		echo "User: ${username} said Ok."
	}
		}
	}
}
```

<br>

### d.9 - Parrallel

Les étapes du pipeline déclaratif Jenkins peuvent avoir d'autres étapes imbriquées à l'intérieur qui seront exécutées en parallèle. Cela se fait en ajoutant la directive `parallel` à votre script:

```groovy
pipeline {
    agent none
    stages {
        stage('Run Tests') {
            parallel {
                stage('Test On Windows') {
                    agent { label "windows" }
                    steps {
                        bat "run-tests.bat"
                      }
                  }
                  stage('Test On Linux') {
                        agent { label "linux" }
                        steps {
                            sh "run-tests.sh"
                    }
                }
            }
        }
    }
}
```

Nous obtiendrons ceci en terme de résultats:

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/parralel.webp" style="width:30%">
</p>

Les deux scripts exécuteront les tests sur différents nœuds car ils exécutent des tests de plate-forme spécifiques. Le parallélisme peut également être utilisé pour exécuter simultanément des étapes sur le même nœud en utilisant le multithreading, si votre serveur Jenkins dispose de suffisamment de CPU.

Certaines restrictions s'appliquent lors de l'utilisation d'étapes parallèles :

- Une directive `stage` peut avoir soit une directive parallèle, soit une directive d'étapes, mais pas les deux.

- Une directive `stage` à l'intérieur d'une directive `parallel` ne peut pas imbriquer une autre directive `parallel`, seules les directives `stage` sont autorisées.

- Les directives d'étape qui ont une directive parallèle à l'intérieur ne peuvent pas avoir de directives "agent" ou "outils" définies.

### d.10 - Parameters

Cette directive permet de définir une liste de paramètres à utiliser dans le script. Les paramètres doivent être fournis une fois le pipeline déclenché. Il doit être défini au niveau du « pipeline » et une seule directive est autorisée pour l'ensemble du pipeline.

`string` et `boolean ` sont les types de paramètres valides pouvant être utilisés.

```shell
pipeline {
    agent any
    parameters {
        string(name: 'user', defaultValue: 'John', description: 'A user that triggers the pipeline')
    }
    stages {
        stage('Trigger pipeline') {
            steps {
                echo "Pipeline triggered by ${params.user}"
            }
        }
    }
}
```

<br>

### d.11 - Tools

La directive `tools` peut être ajoutée soit au niveau du pipeline, soit à la première étape. Il vous permet de spécifier quelle version maven, jdk ou gradle utiliser sur votre script par exemple si vous vous trouver sur du code JAVA.

Chacun de ces outils, les trois pris en charge au moment de la rédaction, doit être configuré dans le menu Jenkins `Configuration globale de l'outil`.

De plus, Jenkins tentera d'installer l'outil répertorié (s'il n'est pas encore installé). En utilisant cette directive, vous pouvez vous assurer qu'une version spécifique requise pour votre projet est installée.

```groovy
pipeline {
    agent any
        tools {
            maven 'apache-maven-3.0.6'
        }
    stages {
    ...
    }
}
```

<br>

### d.12 - when

Les étapes du pipeline peuvent être exécutées en fonction des conditions définies dans une directive "quand". Si les conditions correspondent, les étapes définies dans l'étape correspondante seront exécutées. Il doit être défini au niveau de l'étape.

Pour une liste complète des conditions et leurs explications, reportez-vous à [la directive when du pipeline déclaratif de Jenkins.](https://jenkins.io/doc/book/pipeline/syntax/#when) Les pipelines permettent d'effectuer des tâches sur des projets comportant plusieurs branches.

C'est ce qu'on appelle les pipelines multibranches, où des actions spécifiques peuvent être entreprises en fonction du nom de la branche, comme `master`, `features`, `development`, entre autres. Nous pouvons écrire un exemple de pipeline qui exécutera les étapes pour la branche master :

```groovy
pipeline {
    agent any
    stages {
        stage ('Deploy stage') {
            when {
                branch 'master'
            }
            steps {
                echo 'Deploy master to stage'
                // Add steps for deployment
            }
        }
    }
}
```

Les erreurs de syntaxe des pipelines **déclaratifs** sont signalées dès le début de l'exécution. C'est une fonctionnalité intéressante car vous ne perdrez pas de temps jusqu'à ce qu'une étape ne réalise pas qu'il y a une faute de frappe ou une faute d'orthographe.

Comme déjà mentionné, les pipelines peuvent être écrits de manière **déclarative** ou **scriptée**. En effet, la méthode déclarative est construite au-dessus de la méthode scriptée, ce qui facilite son extension comme expliqué, en ajoutant des étapes de script.

Les pipelines Jenkins sont largement utilisés dans les **environnements CI/CD**. L'utilisation de pipelines déclaratifs ou scriptés présente plusieurs avantages. la méthode déclarative offre une syntaxe beaucoup plus conviviale sans aucune connaissance Groovy requise.


#%%

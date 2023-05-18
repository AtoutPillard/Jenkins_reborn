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

Jenkins offre un moyen simple de configurer un environnement d'intégration continue ou de **livraison continue** pour presque tous les langages et les référentiels de code source (comme GitHub, GitLab...) à l'aide de **pipelines**, ainsi que d'automatiser la plupart des tâches de développement.

Avec l'aide de Jenkins, les organisations peuvent accélérer le processus de développement logiciel grâce à l'automatisation. Jenkins ajoute des **processus** de cycle de vie de développement de toutes sortes, y compris la construction, la documentation, le test, le package, la mise en scène, le déploiement d'analyses statiques et bien plus encore.

Jenkins réalise la phase d'intégration continue (**CI**) à l'aide de plugins. Les plugins sont utilisés pour permettre l'intégration de différentes étapes DevOps. Si nous souhaitons intégrer un outil particulier, nous devons installer les plugins dédiés pour cet outil. Par exemple : `Maven 2 Project`, `Git`, `HTML Publisher`, `Amazon EC2`, etc.

Si une organisation développe un projet, **Jenkins** testera en permanence les **versions** de notre projet et mettra en lumière les erreurs dans les premières étapes de notre développement.

Les étapes possibles exécutées par Jenkins sont par exemple :

- Effectuer une construction de logiciel à l'aide d'un système de construction comme **Gradle** ou **Maven Apache**

- Exécuter un **script** shell

- Archiver un résultat de génération

- Exécution de tests logiciels

## **B - Histoire de Jenkins**

En 2011 Oracle qui possédait la société Sun Microsystems a eu un différend avec la communauté open source d'Hudson. Hudson avait une vision bien différente d'Oracle en terme d'engineering et a décidé de bifurquer le projet et d'inaugurer **Jenkins**.

Hudson et Jenkins ont continué à fonctionner de manière indépendante. Mais en peu de temps, Jenkins a acquis beaucoup de contributeurs et de projets tandis qu'Hudson n'a conservé que 32 projets. Puis avec le temps, Jenkins est devenu plus populaire, et Hudson n'est depuis plus maintenu.

<div class="alert alert-info">Jenkins est l'un des outils DevOps <b>CI/CD</b> open source les plus utilisés. Il permet aux développeurs d'implémenter des pipelines CI/CD dans l'environnement de développement de manière complète.</div>

## **C - Intégration continue - Livraison continue - Déploiement continu**

Le **CI/CD** (intégration continue/livraison continue) est un processus DevOps holistique (qui s'intéresse à son objet dans sa globalité) et se concentre sur la création d'un mélange compatible entre le **cycle de développement** et le **processus d'exploitation**.

Cela se fait en automatisant les **flux de travail** et en déployant des mises à jour **automatiques** pour améliorer le retour sur investissement. La mise en œuvre du pipeline CI/CD est l'épine dorsale de l'ensemble des principes DevOps et facilite le processus d'introduction du produit sur le marché plus rapidement que jamais.

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

**e.2 - Inconvénients de Jenkins**

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

#%%

# II - Installation et configuration de Jenkins

Nous allons installer Jenkins via Docker avec l'image officielle.
Ouvrons une fenêtre de terminal et exécutons les commandes suivantes pour télécharger l'image Docker de Jenkins depuis le registre DockerHub et créer un réseau spécifique à l'outil :

```shell
docker pull jenkins/jenkins
docker pull docker:dind
docker network create jenkins
```

Puis lançons le premier conteneur Docker avec la commande :
> Cela va permettre d'avoir un conteneur Docker autonome (Docker-in-Docker) c'est à dire un environnement Docker fonctionnel à l'intérieur du conteneur Jenkins. Cela va permettre en autre d'exécuter des constructions et des déploiements Docker à partir de Jenkins.

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

Dans un fichier que nous nommerons `Dockerfile`, nous allons recopier les lignes suivantes :
> Ce script va permettre de créer une image personnalisée de Jenkins avec les plugins "blueocean" et "docker-workflow" pré-installés.

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

Lançons la commande suivante pour construire notre image Docker :

```shell
docker build -t myjenkins-blueocean:2.346.3-1 .
```

Enfin, démarrons Jenkins via ce nouveau conteneur Docker :

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

Après avoir lancer les conteneurs Docker, nous poivons accéder à Jenkins en allant sur `localhost:8080` ou `adresse-ip-vm:8080` (si vous utilisez la machine virtuelle) sur notre navigateur internet.

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_fr/unlock.png" style="width:65%">
</p>

Pour retrouver le mot de passe créé, exécutons la commande suivante :

```shell
docker logs jenkins-blueocean
```

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_fr/find_admin_password.png" style="width:65%">
</p>

<div class="alert alert-info"><i class="icon circle info"></i>
Si vous avez besoin d'accéder au répertoire <code>/var/jenkins_home</code>, qui contient des informations relatives à Jenkins, lancez la commande <code>docker exec -it jenkins-blueocean bash</code>.
</div>

Une fois que vous avez recopié le mot de passe généré, vous arriverez sur la page suivante :

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_fr/custo.png" style="width:65%">
</p>

> Sélectionnez le bouton _Install suggested plugin_, puis remplissez le formulaire avec les informations requises.

<div class="alert alert-warning">
Attention à bien noter les identifiants de connexion.
</div>

Vous devriez arriver sur le dashboard Jenkins :

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_fr/welcome.png" style="width:75%">
</p>

À gauche se trouve le menu principal permettant d'accéder aux différentes fonctionnalités de Jenkins comme la création de projets, la consultation de l'historique, ou encore la configuration de Jenkins.

#%%


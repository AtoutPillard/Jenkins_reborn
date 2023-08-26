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

- Si la construction échoue, le résultat des builds sera affiché. Il est possible de configurer l'alerting afin que l'équipe concernée soit informée.

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

- Il prend en charge **1800 plugins** ou plus pour faciliter notre travail. Si un plugin n'existe pas, nous pouvons écrire le script correspondant et le partager avec la communauté.

- Il est construit en **Java** et est donc portable.

- Il est indépendant de la plate-forme et est disponible pour toutes les plates-formes et différents systèmes d'exploitation. Comme OS X, Windows ou Linux.

- Jenkins prend également en charge l'architecture basée sur le **cloud** afin que nous puissions déployer Jenkins sur des plates-formes basées sur le cloud.

### e.2 - Inconvénients de Jenkins

- Son interface est **obsolète** et peu conviviale par rapport aux tendances actuelles de l'interface utilisateur.

- Pas facile à maintenir car il tourne sur un serveur et nécessite quelques compétences en tant qu'administrateur de serveur pour **surveiller** son activité.

- CI se casse régulièrement en raison de quelques petits changements de **réglage**. CI sera mis en pause et nécessite donc l'attention de l'équipe de développeurs.

- Le large éventail de plugins disponibles pour Jenkins augmente les risques d'infection et de vulnérabilité.

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

# II - Installation et configuration de Jenkins

<br>

## **A - Installation de Jenkins**

Jenkins est disponible à partir des référentiels **Ubuntu** et peut être installé directement à l'aide du gestionnaire de packages APT. Nous avons vu que Jenkins est développé en JAVA. 

> Pour vérifier que Java est installé sur notre système, exécutez la commande :

```shell
java --version
```

> Vérifiez que Jenkins est bien installé sur notre système et que le service est actif :

```shell
sudo systemctl status jenkins
```

<div class="alert alert-info">Vous devriez constater que Jenkins est bien en mode "running". Toutefois si ce n'est pas le cas, nous vous avons préparé les prochaines étapes pour reproduire l'installation sur votre machine.</div>

### a.1 - Jenkins Master

Puisque Jenkins est basé sur Java, nous devons installer **OpenJDK**. 

> Pour cela, exécutez la commande :

```shell
sudo apt install openjdk-11-jdk-headless -y
```

Mettre à jour notre machine. Il est recommandé de toujours mettre à jour les packages système.

> Exécutez donc les commandes :

```shell
sudo apt update -y

sudo apt upgrade -y
```

Installons à présent Jenkins. 

> Ajoutez la clé du référentiel Jenkins à notre système :

```shell
curl -fsSL https://pkg.jenkins.io/debian/jenkins.io.key | sudo tee /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] https://pkg.jenkins.io/debian binary/ | sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins -y
```

Jenkins est démarré lors de l'installation sur notre serveur. Nous pourrons confirmer qu'il est en cours d'exécution en exécutant la commande :

```shell
sudo systemctl status jenkins
```

À partir de la sortie, nous pouvons voir que Jenkins est opérationnel.

> Si Jenkins n'est pas démarré, exécutez la commande ci-dessous pour qu'il soit opérationnel :

```shell
sudo systemctl start jenkins
```

Pour activer Jenkins au démarrage, vous pouvez exécuter la commande :

```shell
sudo systemctl enable --now jenkins
```

Jenkins démarrera désormais chaque fois que nous redémarrons ou allumons notre serveur.

## **B - Configuration de Jenkins**

> Connectez-vous au serveur Jenkins à l'aide de votre navigateur à l'adresse: `http://adresseip:8080/`.

<div class="alert alert-info">L'interface Web Jenkins utilise la langue configurée par défaut sur le navigateur du client. Vous pouvez changer ce paramètre à tout moment. Pour simplifier la gestion de nos exercices, nous avons choisit de paramétrer notre navigateur en Anglais.</div>

Nous obtiendrons la première page qui est l'écran "**Déverrouiller Jenkins**". Afin de configurer Jenkins en toute sécurité, nous devrons coller le mot de passe de l'administrateur.

> Exécuterons la commande suivante afin de révéler le mot de passe:

```shell
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

Affichage en sortie:

```shell
943eb6a8472b4e929945a5cb65745f24
```

Copions et collons le mot de passe dans le champ de texte « **Administrator Password** », comme indiqué. Une fois collé, cliquons sur le bouton « **Continuer** »:

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_fr/unlock.png" style="width:65%">
</p>

Une fois que nous avons recopié le mot de passe généré, nous arriverons sur la page suivante :

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_fr/custo.png" style="width:65%">
</p>

> Sélectionnez le bouton « **Install suggested plugin** »,

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/install_jenkins.png" style="width:65%">
</p>

Puis remplissons le formulaire avec les informations requises.

L'écran suivant configure la connexion administrateur, remplissons les informations souhaitées :

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/jenkins-admin-user.png" style="width:65%">
</p>

Vient ensuite la configuration de l'instance de votre URL Jenkins. Nous pouvons laisser la configuration par défaut.

Cliquons sur commencer à utiliser Jenkins. Nous serons alors redirigé vers l'interface Jenkins :

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_fr/welcome.png" style="width:90%">
</p>

Nous avons réussi à installer et configurer Jenkins. À gauche se trouve le **menu principal** permettant d'accéder aux différentes fonctionnalités de Jenkins comme la création de projets, la consultation de l'historique, ou encore la configuration de Jenkins.

#%%

# III - Mise en place des outils 

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

## B - Création du dépôt Github

Nous parlerons à présent du processus d'intégration de GitHub à Jenkins. Pour rappel, GitHub est une plateforme en ligne utilisée pour la gestion de versions et la collaboration dans le développement de logiciels. 

Nous commencerons par créer un nouveau dépôt sur notre compte Github, si vous n'en avez pas, vous pouvez en créer un à l'adresse de [GitHub](https://github.com/signup).

Nous allons donc créer un dépôt afin de pouvoir versionner notre code source et le connecter à Jenkins. Allons sur Github créer un nouveau dépôt appelé `Jenkins-datascientest`, avec une visibilité `public`:

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/repo_github.png" style="width:60%">
</p>

Nous pouvons à présent créer notre dépôt en cliquant sur le bouton `Create repository`.


## **C - Installation de Docker**

Docker est une plate-forme parfaitement adaptée à l'écosystème DevOps. C'est une solution appropriée pour les éditeurs de logiciels qui ne peuvent pas suivre le rythme de l'évolution de la technologie, des activités et des besoins des clients. Cela fait de Docker un choix évident pour développer et accélérer les opérations dans une entreprise.

La raison du succès de Docker est sa capacité à conteneuriser les applications. Cela réduit le temps de développement et de publication d'une solution pour une société de développement de logiciels.

Il permet à une application de s'exécuter sur n'importe quelle application, quelles que soient les configurations d'hôte. Cela permet à toutes les équipes de collaborer tout en travaillant efficacement.

[Docker](http://docker.com/) nous permet de rationaliser et de contrôler les modifications tout au long du cycle de développement. Nous pouvons l'utiliser tout au long des étapes de développement, de production et de publication. Si nous souhaitons revenir à une version précédente, vous pouvez le faire en utilisant Docker.

Nous pouvons également nous assurer qu'une fonctionnalité fonctionne dans l'environnement de production selon qu'elle est opérationnelle ou non dans l'environnement de développement.

> Docker est déjà installé sur les machines virtuelles fournies, afin que Jenkins puisse piloter le `Docker` engine, nous devons ajouter l'utilisateur Jenkins au groupe Docker avec la commande suivante:

```shell
sudo usermod -aG docker jenkins
```

<div class="alert alert-info"><i class="icon circle info"></i>
La section suivante sert pour ceux qui utilisent leurs ordinateurs personnelles. Vous pouvez le vérifier avec la commande <code>docker -v</code>
</div>

Nous allons installer Docker à fin que Jenkins puisse être utilisé pour manipuler nos différentes images Docker. Nous installerons Docker en nous servant des commandes suivantes :

```shell
sudo apt-get install ca-certificates curl gnupg lsb-release -y
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update -y
sudo apt-get install docker-ce docker-ce-cli containerd.io -y
sudo systemctl enable --now docker
```

Nous devons ensuite ajouter l'utilisateur Jenkins au groupe Docker afin que Jenkins puisse piloter le `Docker engine`.

Nous le ferons de la façon suivante :

```shell
sudo usermod -aG docker jenkins
```

<br>

## **D - Docker Hub**

Docker Hub est un registre Docker, une version **hébergée** dans le cloud, une application côté serveur open-source, évolutive et sans état.

Il peut gérer le partage et le stockage des images Docker. À l'aide de Docker, les développeurs peuvent y accéder en tant que public et créer leur propre espace de référentiels privés et **automatiser** les fonctions personnalisées de création d'applications, les groupes de travail et les **webhooks**.

Un développeur formé aux pratiques DevOps peut télécharger l'image officielle du conteneur du système de base de données orienté document MongoDB depuis Docker Hub pour s'entraîner sur une application déployée dans les conteneurs par exemple.

### Fonctionnalités du hub Docker

- Référentiels : il contient le processus Push et Pull pour les images de conteneurs.

- Équipes et organisations : il permet au développeur/utilisateur d'accéder à des référentiels privés d'images de conteneurs.

- Images officielles de **Docker** : il extrait et utilise des images de conteneurs de haute qualité rendues par Docker.

- Images d'éditeur vérifiées par **Docker** : il extrait et utilise des images de conteneurs de haute qualité rendues par des fournisseurs externes.

- **Builds** : il fournit les mécanismes qui formulent automatiquement des images de conteneur à partir de **Bitbucket** et **GitHub** et les poussent vers Docker Hub.

- **Webhooks** : il déclenche certaines actions après une poussée réussie vers un conteneur pour combiner Docker Hub avec des services supplémentaires.

- **Docker** implémente un outil Docker Hub CLI qui est actuellement expérimental et une API (Micro-service) qui nous permet de communiquer avec Docker Hub. Nous pouvons parcourir la documentation [de l'API Docker Hub](https://docs.docker.com/docker-hub/api/latest/) pour rechercher les points de terminaison entre accolades.

Vous pouvez créer un compte Dockerhub à l'adresse suivante : https://hub.docker.com/signup. Nous nous en servirons dans la suite de notre cours.

<br>


## **E - Credentials**
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

> Créez une variable de type `Nom d'utilisateur et mot de passe` afin d'y définir le mot de passe utilisé par Jenkins pour pousser nos images au sein de Dockerhub. Nous mettrons dans ID: `DOCKER_HUB_PASS`

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



#%%

# IV Jobs et Build


## **A - Les différents types de Jobs**

Nous allons nous lancer enfin dans la pratique de Jenkins en construisant notre premier projet!

> Cliquez sur "Nouveau Item" (_New Item_) qui est la première option du dashboard. 

Nous arriverons alors sur la page des jobs Jenkins qui sont un ensemble donné de tâches qui s'exécutent **séquentiellement** tel que défini par l'utilisateur. Toute automatisation est implémentée dans Jenkins est un `Job` Jenkins. Ces travaux constituent une partie importante du processus de construction de Jenkins. Nous pouvons créer et construire des Jobs  pour tester et déployer notre application ou notre projet.

Lorsque nous travaillons avec Jenkins, les termes Jenkins Job et Jenkins Project sont synonymes. Avec un Job Jenkins, nous pouvons cloner le code source à partir d'un gestionnaire de version comme Git, compiler le code et exécuter des tests unitaires en fonction de nos besoins.

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

## **B - Projet Freestyle**

Nous allons nous lancer enfin dans la pratique de Jenkins en affichant le classique `Hello World`.

Pour cela, cliquez sur "Nouveau Item" (_New Item_) qui est la première option du dashboard. Donnez un nom à votre projet, puis sélectionnez l'option "Construire un projet free-style" (_Freestyle project_) et appuyez sur le bouton OK.

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

<div class="alert alert-info"><i class="icon circle info"></i>
Jenkins n'est pas utilisable que depuis son interface web. Il y a aussi des lignes de commandes dont vous pouvez retrouver l'utilisation depuis la route <code>/cli</code>. Comme avec Git, il est parfois plus rapide de passer par ces lignes de commandes, mais moins facile d'accès que depuis l'interface web. Pour pouvoir utiliser ces lignes de commandes, vous devez installer le langage Java.
</div>

#%%

## **V - Pipeline Jenkins**

<br>
Précédemment, nous avons vu la fonctionnalité *Freestyle Project* nonobstant il ne s'agit pas de l'application classique de Jenkins. De même, nous avions mis le SCM (Source Code Management) à None bien que ce n'est rarement le cas. Une des fonctionnalités principales de Jenkins est le Pipeline.

Nous avions explicité l'intérêt d'utiliser Jenkins par la possibilité d'automatiser certaines étapes dans la mise en production d'un logiciel. L'ensemble des étapes de cette mise en production constitue le pipeline de notre projet. Le pipeline dépend de vos projets les étapes peuvent être différentes.

Afin de pouvoir utiliser les fonctionnalités de Jenkins, nous allons reprendre le dépot GitHub crée précédemment. Nous allons ajouter les fichiers suivant pour simuler le déploiement d'une API puis grâce à Jenkins, faire un pipeline qui va automatiser chaque étapes de ce déploiement. 

Les fichiers suivants sont à mettre sur votre repository github.

> Dans un fichier nommé `app.py`, nous allons coller le code ci-dessous qui va créer une API Flask avec plusieurs routes.

```python
##########################################################################
## Imports
##########################################################################

import os

from flask import Flask
from flask import request
from flask import render_template
from flask import url_for
from flask.json import jsonify

##########################################################################
## Application Setup
##########################################################################

app = Flask(__name__)

##########################################################################
## Routes
##########################################################################

@app.route("/api/hello")
def hello():
    """
    Return a hello message
    """
    return jsonify({"hello": "world"})

@app.route("/api/hello/<name>")
def hello_name(name):
    """
    Return a hello message with name
    """
    return jsonify({"hello": name})

@app.route("/api/whoami")
def whoami():
    """
    Return a JSON object with the name, ip, and user agent
    """
    return jsonify(
        name=request.remote_addr,
        ip=request.remote_addr,
        useragent=request.user_agent.string
    )

@app.route("/api/whoami/<name>")
def whoami_name(name):
    """
    Return a JSON object with the name, ip, and user agent
    """
    return jsonify(
        name=name,
        ip=request.remote_addr,
        useragent=request.user_agent.string
    )

##########################################################################
## Main
##########################################################################

if __name__ == '__main__':
    app.run()
```

> Créez un fichier `test_main.py` qui va contenir les tests unitaires de notre API:

```python
import unittest
from app import app

class FlaskTestCase(unittest.TestCase):

    def setUp(self):
        self.app = app.test_client()

    def test_hello(self):
        response = self.app.get('/api/hello')
        self.assertEqual(response.status_code, 200)
        self.assertEqual(response.json, {'hello': 'world'})

    def test_hello_name(self):
        response = self.app.get('/api/hello/ben')
        self.assertEqual(response.status_code, 200)
        self.assertEqual(response.json, {'hello': 'ben'})

if __name__ == '__main__':
    unittest.main()
```

> Dans un fichier nommé `requirements.txt`, ajoutez les librairies nécessaires pour le fonctionnement de l'API ainsi que des tests unitaires: 

```txt
flask
unittest
```

> Enfin nous allons contenairiser notre API avec Docker avec le `Dockerfile` ci-dessous:

```shell
# Dockerfile to build a flask app

FROM python:3.8-slim-buster

WORKDIR /usr/ 

COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt

COPY . .

CMD ["python", "-m" , "flask", "run"]
```

Nous allons retrouver dans ce dépôt notre API, un fichier de tests unitaires, un fichier listant les librairies à installer et un fichier DockerFile. Maintenant que notre API est prête, nous allons pouvoir faire un pipeline composée de plusieurs phases qui va contruire l'API, la tester et la déployer.

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

Nous devons donner un nom à notre projet et ensuite choisir un type de projet.

> Donnez le nom `datascientest_ci_cd` à votre projet et sélectionner le type de projet `Pipeline` car nous partirons de notre fichier Jenkinsfile afin de décrire les tâches à automatiser :


<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/pipeline_projet.png" style="width:60%">
</p>

En cliquant sur le bouton `OK`, notre Job Jenkins sera prêt à être configuré. Nous pouvons créer autant de Jobs Jenkins selon nos besoins. La procédure de création de Job reste la même quelque soit le type de Job. Seuls les paramètres de configurations pourront varier en fonction du type de Jobs.

### **d.1 - Configuration de la gestion du code source**

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

### **d.2 - Projet Github**

> Nous devons cocher la case `GitHub project` et remplir le formulaire qui apparaîtra en utilisant l'url de notre dépôt git:

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/github_project.png" style="width:60%">
</p>

Jenkins utilise Git comme outil de gestion de version de code source. Après avoir terminé la gestion du code source, nous allons ensuite vérifier l'option `Jenkins Build Triggers`.

### **d.3 - Déclencheur Jenkins**

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

> Nous devons cocher la case `GitHub hook trigger for GITScm polling` pour que GitHub puisse envoyer des Webhooks qui déclencherons la construction de notre Job.

Ensuite, nous devons spécifier le chemin du fichier **Jenkinsfile** depuis notre dépôt. Jenkins essaiera par défaut de le récupérer à la racine de ce dernier. Nous devons donc lui renseigner l'URL `SSH`.

Jenkins essaiera immédiatement de vérifier s'il peut récupérer le fichier depuis notre dépôt avant de sauvegarder le projet. 

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/webhook_pipeline.png" style="width:60%">
</p>

> Jenkins essaiera immédiatement de vérifier s'il peut bien récupérer le fichier dans le dit dépôt avant de sauvegarder le projet . Pour le cours, nous créerons le fichier `Jenkinsfile` depuis au sein de notre dépôt Github.

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/jenkinsfile_from_scm.png" style="width:60%">
</p>

> Nous choisissons Git comme `SCM` et définissons le chemin de notre dépôt Github . Nous définissons également sur `None` le champ Credentials car notre dépôt est public et Jenkins pourra récupéré le fichier `Jenkinsfile` sans avoir besoin de s'authentifier.

> Nous laisserons le reste des champs par défaut et nous définirons dans le champ `Script Path` la valeur Jenkinsfile puisse que le fichier `Jenkinsfile` se trouvera à la racine de notre projet. S'il avait été dans un répertoire appelé `pipeline`, nous aurions rempli à la place `pipeline/Jenkinsfile`.

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/jenkinsfile_path.png" style="width:60%">
</p>

> Une fois terminé, nous pouvons sauvegarder notre travail en cliquant sur le bouton `Save`.


## **E - Syntaxe déclarative du pipeline Jenkins**

Nous allons contruire ensemble un pipeline Jenkins qui va automatiser les étapes des notre API, de sa construction à son déploiement. Les instructions seront à faire dans un fichier nommé `Jenkinsfile`.

Le premier bloc d'un pipeline commence toujours par `pipeline`. Si vous écrivez hors de ce bloc, cela générera une erreur. Ensuite, 2 éléments interviennent. Le premier est `agent`, qui va préciser où Jenkins va exécuter les différentes étapes du pipeline. 




### e.1 - Agent

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

Voici un exemple d'agent:
```shell
agent {
  docker {
    image 'gradle:6.9-alpine'
    label 'datascientest-gradle'
    args  '-v /tmp:/tmp'
  }
}
```

> Nous allons maintenant mettre en place notre pipeline pour automatiser tout le déploiement de notre projet. Créez dans votre fichier `Jenkinsfile` une section `pipeline` puis ajoutez un `agent` de type `any` dans votre pipeline

%%SOLUTION%%

```groovy
pipeline {
    agent any

}
```
%%SOLUTION%%

<br>


### e.2 - Environment

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

La déclaration des variables d'environnement peuvent se faire sur l'entièreté du `pipeline` ou au niveau d'un stage :

```groovy
pipeline {
	agent any
  // au niveau de la pipeline
	environment {
		OUTPUT_PATH = './outputs/'
	}
	stages {
		stage ('build') {
      // au niveau d'un stage
      environment {
		    OUTPUT_PATH = './outputs/'
	    }
			...
		}
	...
	}
}
```

<br>

### **e.3 - Variables d'environnement**

Dans le monde de la programmation, les variables sont très utilisés afin de rendre dynamique le code source. Ce système est très utilisé quand nous voulons avoir un pipeline que nous pourrons réutiliser dans des contextes différents.

Une liste de variable est disponible au sein de Jenkins en ouvrant l'url du serveur master sur un navigateur et en y ajoutant `env-vars.html`. L'url finale est donc sous ce format :

```shell
http://ip_de_votre_masterjenkins:8080/env-vars.html
```

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/variables_jenkins.png" style="width:60%">
</p>

Nous les utiliserons dans le fichier `Jenkinsfile` . Une variable d'environnement Jenkins est une variable globale exposée via la variable `env` et utilisée n'importe où dans le fichier `Jenkinsfile`.

Toute valeur stockée dans la variable `env` est stockée en tant que type `String`. Les variables d'environnement peuvent être définies au niveau supérieur du pipeline, au niveau de l'étape spécifique ou à l'intérieur du bloc `script`.

Nous pouvons lister toutes les variables d'environnement en exécutant la commande shell `printenv` de la façon suivante dans un pipeline :

```groovy
pipeline {
    agent any

    stages {
        stage("Datascientest Variables") {
            steps {
                sh "printenv"
            }
        }
    }
}
```

Nous pourrons accéder aux variables d'environnement dans les étapes du pipeline via l'objet `env`. Un exemple simple serait d'utiliser `env.BUILD_ID` qui renverra l'ID de build actuel.

Nous pouvons également utiliser une version abrégée `BUILD_ID` dans un fichier de pipeline de la façon suivante :

```groovy
pipeline {
    agent any

    stages {
        stage("Datascientest Env Variables") {
            steps {
                echo "The build id is ${env.BUILD_ID} or $BUILD_ID or ${BUILD_ID} "
            }
        }
    }
}
```

Les variables d'environnement peuvent être définies de manière déclarative à l'aide du bloc `environment { }`, à l'aide de `env.VARIABLE_NAME`, ou du bloc `withEnv(["VARIABLE_NAME=value"]) {}`

```groovy
pipeline {
    agent any

    environment {
        SHOOL = "datascientest"
    }

    stages {
        stage("Env Variables") {
            environment {
                NAME = "Datascientest"
            }

            steps {
                echo "SHOOL = ${env.SHOOL}"
                echo "NAME = ${env.NAME}"

                script {
                    env.TEST_VARIABLE = "some test value"
                }

                echo "TEST_VARIABLE = ${env.TEST_VARIABLE}"

                withEnv(["ANOTHER_ENV_VAR=here is some value"]) {
                    echo "ANOTHER_ENV_VAR = ${env.ANOTHER_ENV_VAR}"
                }
            }
        }
    }
}
```

Le fichier Jenkinsfile prend en charge le remplacement des variables d'environnement. Il y a quelques règles à connaître.

- Le bloc `withEnv(["env=value]) { }` peut remplacer n'importe quelle variable d'environnement.

- Les variables définies à l'aide de bloc `environment {}` ne peuvent pas être remplacées à l'aide d' une affectation impérative `env.VAR = "value"`.

- L'affectation impérative `env.VAR = "value"` ne peut remplacer que les variables d'environnement créées à l'aide de l'affectation impérative.

Nous pouvons mettre en avant les trois cas dans le pipeline suivant :

```groovy
pipeline {
    agent any

    environment {
        SHOOL = "datascientest"
        NAME = "Anthony"
    }

    stages {
        stage("Env Variables") {
            environment {
                NAME = "lewis" // overrides pipeline level NAME env variable
                BUILD_ID = "2" // overrides the default BUILD_ID
            }

            steps {
                echo "SHOOL = ${env.SHOOL}" // prints "SHOOL = bar"
                echo "NAME = ${env.NAME}" // prints "NAME = lewis"
                echo "BUILD_ID =  ${env.BUILD_ID}" // prints "BUILD_ID = 2"

                script {
                    env.SOMETHING = "1" // creates env.SOMETHING variable
                }
            }
        }

        stage("Override Variables") {
            steps {
                script {
                    env.SHOOL = "I LOVE DATASCIENTEST!" // it can't override env.SHOOL declared at the pipeline (or stage) level
                    env.SOMETHING = "2" // it can override env variable created imperatively
                }

                echo "SHOOL = ${env.SHOOL}" // prints "SHOOL = bar"
                echo "SOMETHING = ${env.SOMETHING}" // prints "SOMETHING = 2"

                withEnv(["SHOOL=DEV UNIVERSITY"]) { // it can override any env variable
                    echo "SHOOL = ${env.SHOOL}" // prints "SHOOL = DEV UNIVERSITY"
                }

                withEnv(["BUILD_ID=1"]) {
                    echo "BUILD_ID = ${env.BUILD_ID}" // prints "BUILD_ID = 1"
                }
            }
        }
    }
}
```
> À nouveau dans votre fichier `Jenkinsfile`, ajoutez dans une section `environment`, les variables d'environnement suivantes que nous utiliserons plus tard:
> - `DOCKER_ID` qui va contenir le pseudonyme de votre compte Dockerhub que nous avons créée dans la partie `Credentials`
> - `DOCKER_IMAGE` qui va contenir le nom de l'image docker que vous nommerez `datascientestapi`
> - `DOCKER_TAG` qui va prendre comme valeur `v.${BUILD_ID}.0` permettant d'incrémenter la valeur de 1 à chaque nouvelle construction

%%SOLUTION%%

```groovy
pipeline {
  agent any
  environment { 
    DOCKER_ID = "dstdockerhub"
    DOCKER_IMAGE = "datascientestapi"
    DOCKER_TAG = "v.${BUILD_ID}.0" 
  }
}
```
%%SOLUTION%%

<br>

### e.4 - Stages et Stage

La section `stages` permet de générer différentes étapes sur le pipeline qui seront visualisées sous la forme de différents segments lors de l'exécution de la tâche.

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/jenkins-stages.jpg" style="width:60%">
</p>

Jenkins divise graphiquement l'exécution du pipeline en fonction des étapes définies et affiche leur durée et si elle a réussi ou non. La directive `stage` va dans la section `stages` et devrait contenir une directive [steps](https://docs.cloudbees.com/docs/admin-resources/latest/pipeline-syntax-reference-guide/declarative-pipeline#steps), une directive `agent` facultative ou d'autres directives spécifiques à une étape.

En pratique, tout le travail réel effectué par un Pipeline sera enveloppé dans une ou plusieurs directives `stage`.

Voici un exemple d'architecture d'un pipeline avec des stages:
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

> Ajoutez à votre pipeline une section nommée `stages` qui va contenir trois `stage` nommés `Building`, `Testing` et `Deploying`.  

%%SOLUTION%%
```groovy
pipeline {
    agent any
    environment { 
	DOCKER_ID = "dstdockerhub"
	DOCKER_IMAGE = "datascientestapi"
	DOCKER_TAG = "v.${BUILD_ID}.0" 
    }
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

### e.5 - Steps

Il s'agit d'une séquence d'une ou plusieurs directives d'étape, la section `stages` est l'endroit où se situera l'essentiel du job décrit par un Pipeline. Au minimum, il est recommandé de contenir au moins une directive `steps` pour chaque partie distincte du processus de livraison continue, telle que `Build`, `Test` et `Deploy`.

Voici un exemple de `steps` dans un pipeline Jenkins

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

> En ajoutant une directive `steps` dans chacune des trois stages, effectuez les commandes suivantes:
> - Dans la phase `Building`, vous devez installer les librairies contenues dans le fichier `requirements.txt`
```shell
pip install -r requirements.txt
```
> - Dans la phase `Testing`, vous devez lancer les tests unitaires
```shell
python -m unittest
```

%%SOLUTION%%

```groovy
pipeline {
    agent any
    environment { 
	DOCKER_ID = "dstdockerhub"
	DOCKER_IMAGE = "datascientestapi"
	DOCKER_TAG = "v.${BUILD_ID}.0" 
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

            }
        }
    }
}
```
%%SOLUTION%%

</br>

### e.6 - script

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

> * Dans la phase `Deploying`, faites une section `script` dans lequel vous allez créer une image Docker à partir du Dockerfile. Vous allez devoir utiliser les variables implémentées un peu plus tôt et suivre cette nomenclature: pseudo_dockerhub/nom_image:version_api.
```shell
docker build -t $DOCKER_ID/$DOCKER_IMAGE:$DOCKER_TAG .
```
> * Lancez le conteneur Docker avec le nom `jenkins` sur le port `8000`. Faites attention à ce que le port soit libre.
```shell
docker run -d -p 8000:8000 --name jenkins $DOCKER_ID/$DOCKER_IMAGE:$DOCKER_TAG
```
> * Pour éviter tous conflits de port avec les conteneurs Docker lorsque le pipeline se relance, ajoutez la commande suivante avant la création de l'image.
```shell
docker rm -f jenkins
```

%%SOLUTION%%

```groovy
pipeline {
    agent any
    environment { 
      DOCKER_ID = "dstdockerhub"
      DOCKER_IMAGE = "datascientestapi"
      DOCKER_TAG = "v.${BUILD_ID}.0" 
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
              docker rm -f jenkins
              docker build -t $DOCKER_ID/$DOCKER_IMAGE:$DOCKER_TAG .
              docker run -d -p 8000:8000 --name jenkins $DOCKER_ID/$DOCKER_IMAGE:$DOCKER_TAG
              '''
		        }
          }
        }
    }
}
```
%%SOLUTION%%

<br>


### e.7 - triggers

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


### e.8 - Input

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

> Ajoutez dans votre jenkinsfile, un nouvel stage nommé `User acceptance` qui va demander à l'utilisateur s'il veut déployer le code sur la branche `main`

%%SOLUTION%%

```groovy
pipeline {
    agent any
    environment { 
      DOCKER_ID = "dstdockerhub"
      DOCKER_IMAGE = "datascientestapi"
      DOCKER_TAG = "v.${BUILD_ID}.0" 
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
              docker rm -f jenkins
              docker build -t $DOCKER_ID/$DOCKER_IMAGE:$DOCKER_TAG .
              docker run -d -p 8000:8000 --name jenkins $DOCKER_ID/$DOCKER_IMAGE:$DOCKER_TAG
              '''
            }
          }
        }
        stage('User Acceptance') {
          steps{
            input {
              message "Proceed to push to main"
              ok "Yes"
            }    
          }
        }
    }
}
```
%%SOLUTION%%

<br>


### e.9 - Parrallel

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


> Créez un nouveau stage `Pushing and Merging` regroupant les deux stages suivantes qui seront exécutés en parallèle:
> * Un stage `Pushing` qui va push l'image Docker sur votre compte dockerhub
> * * Créez une section `environment` propre à ce stage qui va contenir une variable nommée `DOCKERHUB_CREDENTIALS`. Elle va prendre en valeur les identifiants dockerhub que nous avons créé précédemment dans les credentials. Ces informations peuvent être retrouver grâce à la fonction credentials() qui prend en entrée, l'id du credentials jenkins.
> * * Vous devez vous connecter à dockerhub à partir de Jenkins grâce à la commande suivante: `echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin`
> * Un stage `Merging` dans lequel nous allons mettre un simple `echo 'Merging done'`. Modifier des branches directement sur le dépot Github nécessite plus de manipulation que nous verrons dans la partie `Compléments`. 

%%SOLUTION%%

```groovy
pipeline {
    agent any
    environment { 
      DOCKER_ID = "dstdockerhub"
      DOCKER_IMAGE = "datascientestapi"
      DOCKER_TAG = "v.${BUILD_ID}.0" 
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
              docker rm -f jenkins
              docker build -t $DOCKER_ID/$DOCKER_IMAGE:$DOCKER_TAG .
              docker run -d -p 8000:8000 --name jenkins $DOCKER_ID/$DOCKER_IMAGE:$DOCKER_TAG
              '''
            }
          }
        }
	      stage('User Acceptance') {
	        steps{
		        input {
              message "Proceed to push to main"
              ok "Yes"
            }    
	        }
	      }
	      stage('Pushing and Merging'){
	        parallel {
		        stage('Pushing Image') {
		          environment {
			          DOCKERHUB_CREDENTIALS = credentials('docker_jenkins')
		          }
		          steps {
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
			          sh 'docker push $DOCKER_ID/$DOCKER_IMAGE:$DOCKER_TAG'
		          }
		        }
            stage('Merging') {
              steps {
                echo 'Merging done'
              }
            }
	      }
	    }
    }
}
```
%%SOLUTION%%

### e.10 - Post

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

> Créez une section post qui va permettre de se déconnecter de dockerhub à la fin de chaque workflow. Nous allons donc utiliser la condition `always`.

%%SOLUTION%%

```groovy
pipeline {
    agent any
    environment { 
      DOCKER_ID = "dstdockerhub"
      DOCKER_IMAGE = "datascientestapi"
      DOCKER_TAG = "v.${BUILD_ID}.0" 
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
              docker rm -f jenkins
              docker build -t $DOCKER_ID/$DOCKER_IMAGE:$DOCKER_TAG .
              docker run -d -p 8000:8000 --name jenkins $DOCKER_ID/$DOCKER_IMAGE:$DOCKER_TAG
              '''
            }
          }
        }
	      stage('User Acceptance') {
	        steps{
		        input {
              message "Proceed to push to main"
              ok "Yes"
            }    
	        }
	      }
	      stage('Pushing and Merging'){
	        parallel {
		        stage('Pushing Image') {
		          environment {
			          DOCKERHUB_CREDENTIALS = credentials('docker_jenkins')
		          }
		          steps {
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
			          sh 'docker push $DOCKER_ID/$DOCKER_IMAGE:$DOCKER_TAG'
		          }
		        }
            stage('Merging') {
              steps {
                echo 'Merging done'
              }
            }
	      }
	    }
    }
    post {
      always {
        sh 'docker logout'
      }
    }
}
```
%%SOLUTION%%

<br>

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

Nous avons maintenant fini notre pipeline!

Vous pouvez cliquez ensuite sur le bouton `Build Now` sur le dashboard de gauche, vous obtenez l'image suivante.

#TODO: Ajouter l'image

Vous pouvez observer le succès ou l'échec des différentes étapes depuis la `Stage View` et le temps imparti pour réaliser l'étape. La couleur verte indique bien sûr que c'est un succès, et le rouge un echec. 

Nous pouvons voir aussi le déroulé des actions de notre étape en allant sur le *Build#1* comme avec un Freestyle Project, l'option `Console Output` apparaîtra sur le dashboard. 

Il est possible aussi de voir les résultats depuis le Stage View en cliquant sur le rectangle vert, une option pour voir les logs apparaîtra ou sinon en allant dans la page de garde du *Build#1* accessible en cliquant sur le `#1`. 

Nous allons maintenant voir comment gérer les erreurs. Pour cela nous allons simuler une faute de frappe en changeant la step du stage `Merging` par: 
```shell
echoo 'Merging done'
```

En cliquant à nouveau sur le bouton `Build Now`, nous obtenons cela :

#TODO: Ajouter l'image

Comme prévu, nous obtenons une erreur. En affichant les logs, nous voyons quelle partie de l'étape Merging n'a pas fonctionné. En se concentrant sur la première erreur, nous observons que `echoo` n'existe pas, en effet nous avons mal écrit la commande. Vous pouvez, dès à présent, corriger l'erreur.

Les erreurs de syntaxe des pipelines **déclaratifs** sont signalées dès le début de l'exécution. C'est une fonctionnalité intéressante car vous ne perdrez pas de temps jusqu'à ce qu'une étape ne réalise pas qu'il y a une faute de frappe ou une faute d'orthographe.

Comme déjà mentionné, les pipelines peuvent être écrits de manière **déclarative** ou **scriptée**. En effet, la méthode déclarative est construite au-dessus de la méthode scriptée, ce qui facilite son extension comme expliqué, en ajoutant des étapes de script.

Les pipelines Jenkins sont largement utilisés dans les **environnements CI/CD**. L'utilisation de pipelines déclaratifs ou scriptés présente plusieurs avantages. la méthode déclarative offre une syntaxe beaucoup plus conviviale sans aucune connaissance Groovy requise.


#%%

# VI - Jenkins Blue Ocean

<br>

## **A - Introduction**

Blue Ocean est un **plugin** de Jenkins qui simplifie le développement des pipelines de logiciels en permettant aux développeurs de créer des pipelines avec **éditeur visuel**, puis visualiser le **flux de processus** de manière intuitive, de sorte que toute l'organisation et pas seulement les développeurs puisse le comprendre.

Pour cela, la nouvelle expérience utilisateur apportée par **Blue Ocean** est basée sur un design personnalisé et moderne et est créé sur la base de l'expérience utilisateur de Jenkins. Il est principalement conçu pour le processus de pipeline et permet de réduire le désordre causés par des multiples pipelines Jenkins et augmente également la clarté pour chaque membre de l'équipe.

## **B - Principales caractéristiques de Blue Ocean**

- **Personnalisation :** Blue Ocean fonctionne de manière personnalisée. Chaque membre de l'équipe peut facilement visualiser l'exécution et les modifications apportées aux builds.

- **Précision précise :** chaque fois qu'un problème survient ou qu'une interférence est nécessaire dans le processus de pipeline, Blue Ocean indique l'emplacement exact où le bogue est apparu et où vous pouvez faire attention dans le pipeline.

- **Éditeur de pipeline :** Blue Ocean facilite la création d'un pipeline en donnant des conseils à l'utilisateur via des **instructions** et une **représentation** visuelle.
- Open source : L'océan bleu est open source ; vous êtes en mesure d'apporter des modifications selon vos besoins.

- **Gratuit :** L'océan bleu est totalement gratuit. Il s'agit d'un **plugin** dans Jenkins et vous pouvez le télécharger à partir de la section Gérer Jenkins.

## **C - Installation de Blue Ocean**

Pour installer le Blue Ocean dans le Jenkins, nous devons utiliser la version Jenkins 2.7.x ou ultérieure.

- Dans l'écran d'accueil de Jenkins (tableau de bord Jenkins), cliquons sur l' option **Manage Jenkins** sur le côté gauche de l'écran.

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/manage_jenkins.png" style="width:100%">
</p>

- Maintenant, cliquons sur **Manage plugins**.

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/manage_plugins.png" style="width:100%">
</p>

- Dans la page suivante, cliquons sur l'onglet **Available**.

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/available_plugins.png" style="width:100%">
</p>

- Dans le champ de recherche, entrons `Blue Ocean ` et cochons sur la checkbox afin de sélectionner le plugin `Blue Ocean` et cliquons sur le bouton `install without restart`:

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/blueocean_install.png" style="width:100%">
</p>

Une fois l'installation terminée, nous pouvons revenir sur le tableau de bord Jenkins. Nous retrouvons un menu `open blue ocean` sur le menu de gauche de Jenkins.

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/blueocean_menu.png" style="width:100%">
</p>

Nous arrivons sur l'interface de Blue Ocean.

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/blue0.png" style="width:100%">
</p>

Nous cliquons sur notre projet `datascientest-ci-cd`.

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/blue1.png" style="width:100%">
</p>

Nous pouvons à présent cliquer sur le bouton `run` afin de voir Blue Ocean en action.

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/blue2.png" style="width:100%">
</p>

Une fois terminé, nous avons une interface qui nous montre que tout est Ok.

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/blue3.png" style="width:100%">
</p>

#%%

# VII - Compléments

## **A - Les Webhooks Github**

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

Sur votre dépot github, nous pouvons aller sur les réglages du dépôt en cliquant sur `settings`.

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/setting_github.png" style="width:100%">
</p>


Nous pouvons à présent cliquer sur `webhooks`.

<p align="center">
  <img src="https://dst-de.s3.eu-west-3.amazonaws.com/jenkins_devops_fr/github_webhook.png" style="width:100%">
</p>

Nous cliquerons sur `Add Webhook`.

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




# VII - Conclusion

Nous avons vu différentes façons d'utiliser Jenkins, notamment comment il s'intègre en **CI/CD**. Son installation est simple via l'utilisation du conteneur Docker officiel et elle comporte l'ensemble des capacité de Jenkins.

Dans un premier temps, nous avons observé les premières fonctionnalités de Jenkins avec le _Freestyle Project_ dont notamment la simulation d'un terminal mais aussi des outils en _Software Engineering_ comme `Ant`, `Gradle` et `Maven`.

Puis, nous sommes rentrés plus dans le sujet de l'intégration continue avec l'objet _Pipeline_, qui réalise une suite de tâches, comme la création de l'exécutable, la phase de test et le déploiement du produit. Pour réaliser cet ensemble d'action, nous manipulons un fichier nommé `Jenkinsfile` écrit en `Apache Groovy`. Nous découvrons le succès ou l'échec de notre application depuis l'interface graphique. Soit celle par défaut, soit en utilisant _Blue Ocean_ qui est plus esthétique.

Par ailleurs, il est possible d'employer Jenkins pour des projets où vous travaillez sur plusieurs branches grâce au _Multibranch Pipeline_. Ainsi, vous pouvez observer l'avancement de votre projet sur les différentes branches.

Enfin, dans la continuité du processus CI/CD, nous avons constaté que Jenkins permettait d'automatiser l'exécution des _Pipeline_, selon un emploi du temps ou même à la suite d'une modification de vos fichiers.
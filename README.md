# Projet-Time-Series-E5

## URL Database: 

"https://public.opendatasoft.com/explore/dataset/donnees-synop-essentielles-omm/download/?format=csv&q=date:%5B2018-12-31T23:00:00Z+TO+2022-10-01T21:59:59Z%5D&timezone=Europe/Berlin&lang=fr&use_labels_for_header=true&csv_separator=%3B
"

# Prédiction de température en utilisant des méthodes time series

Nous avons trouvé une base de données sur opendatasoft :

Données d'observations issues des messages internationaux d’observation en surface (SYNOP) circulant sur le système mondial de télécommunication (SMT) de l’Organisation Météorologique Mondiale (OMM). Paramètres atmosphériques mesurés (température, humidité, direction et force du vent, pression atmosphérique, hauteur de précipitations) ou observés (temps sensible, description des nuages, visibilité) depuis la surface terrestre. Selon instrumentation et spécificités locales, d'autres paramètres peuvent être disponibles (hauteur de neige, état du sol, etc.)

Elle est actualisé chaque jour.

Notre but avec cette base de données est de faire du forcasting des températures pour prédire d'éventuelle sécheresse par exemple.

Pour réaliser cela on va utiliser différentes méthodes vues en cours tel que : 
- exponential smoothing
- les differends modèles SARIMAX
- du deep learning avec un model RNN

Certains modèles utiliseront les features présentes dans la base de données et d'autre uniquement les valeurs des températures 

# Conclusion

La température dépend de beaucoup de choses. La distance au soleil, l'épaisseur de l'atomshère que le rayon doit traverser... si la température ne dependait que de ça, ça serait facile de la prédire car on connait très bien la distance au soleil à chaque instant et l'épaisseur de l'atmosphère on en a une bonne estimation tout autour de la terre (exemple en Austalie elle est plus fine). Cependant il y a d'autre facteur qui la font évoluer tel que le vent, les nuages ... ces phénomènes ne sont pas aléatoire cependant ils dépendent de tellement de paramètres que il est tres difficile de les prédire. On appel cela l'effet papillon.

Avec cette base de données on ne peut prédire correctement des données futur car nos features sont des observations, il faudrait alors anticiper ces features. On peut essayer de prédire ces features mais on sait que les données météo sont soumises à l'effet papillon et donc très aléatoire. Cependant à cours terme il est possible d'avoir quelques estimations sur ces features et donc prédire la température de manière imprécise car se ne sont que des estimations et nous sommes limités à un proche futur. Il y a certain cas où on pourrait prédire plus loin. Par exemple lorsqu'une région va être sous un anti cyclone (phénomène que on prédit plutôt bien ), on sera au courant qu'il n'y aura pas de vent, pas de pluie, pression constante, etc... on pourra donc prédire un plus grand horizon les températures.

D'autre part on observe que nos features sont très utile pour la prédiction de la température car les modèles utilisant les features sont beaucoup plus précis que les autres (cf ARMA vs SARIMAX).

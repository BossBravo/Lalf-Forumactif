## Lalf
  
  Logiciel d'Aide à la Libération de Forumactif  
  Copyright ©2011 Roromis  
  http://www.le-lalf.fr.nf  
  
## BossBravo
  Version Modifiée par mes soins pour une adaptation personelle.

## Note importante

Ce programme est un logiciel libre ; vous pouvez le redistribuer et/ou 
le modifier au titre des clauses de la Licence Publique Générale GNU, 
telle que publiée par la Free Software Foundation ; soit la version 3 
de la Licence.

## Disclaimer

Ce programme est distribué dans l'espoir qu'il sera utile, mais SANS 
AUCUNE GARANTIE ; sans même une garantie implicite de COMMERCIABILITE 
ou DE CONFORMITE A UNE UTILISATION PARTICULIERE. Voir la Licence 
Publique Générale GNU pour plus de détails. Vous devriez avoir reçu 
un exemplaire de la Licence Publique Générale GNU avec ce programme.
Les auteurs déclinent toutes responsabilités quant à l'utilisation 
qui pourrait en être faite.

## Documentation

### Prérequis

 * Vous devez être administrateur du forum que vous souhaitez exporter.
 
 * Le forum doit être hébergé par forumactif, et doit utiliser le 
   template (style) phpbb2.
   
 * Le format des dates de votre forum doit-être "jour J mois AAAA - 
   HH:MM" (par exemple: Lun 1 Jan 2009 - 00:01), vous devez modifier 
   cela dans le profil de l'administrateur.

### Installation

Dans un premier temps, installez, si ce n'est pas déjà fait, Python 
2.* (le script ne fonctionnera PAS avec Python 3).

 * Sous Linux, Python est certainement installé par défaut. Vérifiez 
   que vous avez bien la version 2. Sinon, installez la avec votre 
   gestionnaire de paquets ou compilez la.
   
 * Sous Windows, téléchargez Python 2.* sur cette page: 
   http://www.python.org/download/ 
   
 * Sous Mac, Python devrait être installé par défaut.

Installez ensuite la bibliothèque lxml.

 * Sous Linux, installez le paquet correspondant.
 
 * Sous Windows, téléchargez et installez la dernière version stable 
   sur cette page: http://pypi.python.org/pypi/lxml/

Modifiez ensuite la configuration dans le fichier config.py.

### Utilisation

 * Lancez le script (en double cliquant sur launcher.py ou depuis un 
   terminal).
   Il est très probable que vous ayez des erreurs de connection 
   pendant l'exécution du script (HTTP Error 502: Bad Gateway, 
   SocketError...). Ces erreurs sont normales (à mon avis, elles 
   viennent des serveurs de forumactif et non de mon script), essayez 
   de relancez le script.

 * Installez un forum PhpBB3 en suivant la procédure habituelle.
 
 * Importez ensuite le fichier phpbb.sql généré par le script dans 
   votre base de donnée.

### Resynchronisation

 * Connectez vous au panneau d'administration en utilisant les 
   identifiants de l'administrateur de votre ancien forum (seul le mot 
   de passe indiqué dans le fichier config.py est conservé, les autres 
   sont générés aléatoirement) et resynchronisez les statistiques, 
   les compteurs de messages et les sujets pointés (Onglet Général).
   
 * Resynchronisez tous les forums/sous-forums (Onglet Forums, Bouton 
   orange "Resynchroniser" à droite de chaque forum).
   
 * Créez les index de recherche (Onglet Maintenance -> Base de donnée 
   -> Index de recherche, cliquez sur les deux boutons "Supprimer 
   l'index de recherche" (s'ils sont présent) puis sur les boutons 
   "Créer l'index de recherche").
   
 * Téléchargez le Support Toolkit (et éventuellement la traduction 
   française) sur http://www.phpbb.com/support/stk/ et extrayez le 
   dossier stk/stk à la racine de votre forum. Ouvrez ce dossier dans 
   votre navigateur (http://lien vers phpbb/stk) et réanalysez les 
   BBCodes (onglet Outils pour les administrateurs, cochez "Réanalyser 
   tous les BBCodes" et cliquez sur Envoyer).
   
 * Modifiez les permissions de vos forums (par défaut, ils sont 
   visibles par tous les utilisateurs et les invités), ajoutez les 
   modérateurs, co-administrateurs manuellement.

## Crédits

Programmé en python en utilisant:

 * [PyQuery](https://bitbucket.org/olauzanne/pyquery/)
 * [python-progressbar](http://code.google.com/p/python-progressbar/)
 * [cssselect](http://pythonhosted.org/cssselect/)
 * [chardet](https://github.com/erikrose/chardet)

En s'inspirant des [Crawler Converters](http://www.phpbb.com/community/viewtopic.php?f=65&t=1761395)
de nneonneo 

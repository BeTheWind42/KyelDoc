.. KyelDoc documentation master file, created by
   sphinx-quickstart on Thu May 14 18:28:19 2020.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

KyelDoc
===================================

Attributs Basiques
==================

Id:
	``<Card id='test' />``
	 - Ici 'test' est l'id de la carte.
	 - *id* est un attribut obligatoire.
	 - Les mujuscule compte dans l'id.

Type:
	``<Card type='INFORMATIVE' />``
	 - Il existe 4 types differents: 
		 - **INFORMATIVE**
		 - **YOUR_KINGDOM**
		 - **ENNEMY**
		 - **OTHERS_KINGDOMS**
	 - *type* est un attribut obligatoire.
	 - le *type* doit être écrit en majuscule et sans faute de frappe.

Text Id:
	``<Card id='this' idText='otherid' />``
	 - Cet attribut permet de donné un id différent pour la traduction que *id*.

Sprite Id:
	``<Card id='this' idSprite='otherid' />``
	 - Cet attribut permet aussi de donné un id différent mais pour l'image.

Next Card:
	``<Card nextCard='idOfNextCard' />``
	 - Cet attribut permet de désigné la prochaine carte quand on swipe la carte à Gauche ou à Droite

Left Card:
	``<Card leftCard='idOfCardOnLeft' />``
	 - Cet attribut permet de désigné la prochaine carte quand on swipe à Gauge.
	 - Cet attribut n'est pas compatible avec *nextCard*

Right Card:
	``<Card rightCard='idOfCardOnRight' />``
	 - Cet attribut permet de désigné la prochaine carte quand on swipe à Droite.
	 - Cet attribut n'est pas compatible avec *nextCard*

Text Left:
	``<Card textLeft='traductionIdOfTextOnLeft' />``
	 - Cet attribut permet de choisir l'id de la traduction quand on tourne la carte vers la Gauche.

Text Right:
	``<Card textLeft='traductionIdOfTextOnRight' />``
	 - Cet attribut permet de choisir l'id de la traduction quand on tourne la carte vers la Droite.
	 
Weight:
	``<Card weight='10' />``
	 - Le poids est de base à 0.
	 - Cet attribut permet de changé par un valeur net le poids de la carte et donc la chance d'être pioché.
	

Les Sous-attributs
==================

Les sous-attribut sont à crée de cette maniere:

.. code-block:: xml
	
	<Card attribut1='...' attribut2='...' ...>
		<Nom_du_sous-attribut attribut1_du_sous-attribut='' ... />
	</Card>


Les sous-attributs basiques
---------------------------

Gauge:
	.. code-block:: xml
		
		<Card>
			<Gauge army='+10' food='-10' money='0' population='0' life_bar='-30' type='left' />
		</Card>
	..
	 - Cet attribut permet de modifié les ressources du joueur lorsque qu'il swipe
	 - Si l'attribut *type* a la valeur *left* il ne modifira les ressources que si on swipe à Gauche, et inversement si l'attribut a la valeur *right*.
	 - Si l'attribut *type* n'est pas utilisé alors la gauge s'appliquera sur les deux coté.
	 - Les attributs *army*, *food*, *money*, *population*, et *life_bar* sont obligatoire.

.. toctree::
   :maxdepth: 2
   :caption: Contents:


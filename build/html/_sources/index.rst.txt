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
..



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
	 - Les attributs *army*, *food*, *money*, *population*, et *life_bar* ont comme valeur par default 0.
	 - Aucun attribut est obligatoire.

EndGame:
	.. code-block:: xml
		
		<Card>
			<EndGame />
		</Card>
	..
	
	 - Finit le jeu lorsque la carte est swipé

AddDelayedCard:
	.. code-block:: xml
		
		<Card>
			<AddDelayedCard player='ennemy' turn='2' cardId='isCard' side='left' />
		</Card>
	..
	
	 - Ajout une carte retardé de tour *turn* et d'id *cardId*.
	 - Seuls les attribut *turn* et *cardId* sont obligatoire.
	 - Si l'attribut *player* est a la valeur **ennemy** alors la carte retardé sera donné à l'adversaire.
	 - Si l'attribut *side* est à **left** alors la carte sera donné si on wipe a gauche, l'inverse si *side* est à **right**.


Tag Attributs
-------------

AddTag:
	.. code-block:: xml
	
		<Card>
			<AddTag name='loan' side='left' />
		</Card>
	..
	
	 - Ajout le tag du nom de la valeur de *name*.
	 - Seul l'attribut *name* est obligatoire.
	 - Si l'attribut *side* est à **left** alors la carte sera donné si on wipe a gauche, l'inverse si *side* est à **right**.

DelTag:
	.. code-block:: xml
	
		<Card>
			<DelTag name='loan' side='right' />
		</Card>
	..
	
	 - Supprime le tag de valeur *loan* si il y est.
	 - Seul l'attribut *name* est obligatoire.
	 - Si l'attribut *side* est à **left** alors la carte sera donné si on wipe a gauche, l'inverse si *side* est à **right**.


Weight Attributs
----------------

Les attribut de poids modifie le poids d'une carte.

.. important:: Les sous-attributs de poids sont cumulable mais ecrase l'attribut poids.

TagWeight:
	.. code-block:: xml
		
		<Card>
			<TagWeight name="loan" value="100" notValue="1" />
		<Card>
	..
	
	 - *TagWeight* permet de modifier le poids de la carte si le joueur a le tag de valeur *name*.
	 - Si le joueur a le tag alors le poids vaut *value* sinon il vaut *notValue*.
	 - Seul l'attribut *name* est obligatoire.
	 - Si l'attribut *value* n'est pas spécifié alors sa valeur est à 100.
	 - Si l'attribut *notValue* n'est pas spécifié alors sa valeur est à 0.

GaugeWeight:
	.. code-block:: xml
		
		<Card>
			<GaugeWeight army="50" poidsArmy="1" population="20" poidsPopulation="1" maxPoids="100" />
		</Card>
	..
	
	 - *GaugeWeight* augement le poids de la carte si le joueur ce raproche des valeur.
	 - Le poids permet de faire varié l'importance du ressouce, exemple: *poidsArmy* est à 2 et *poidsPopulation* à 1 alors l'armée importe plus.
	 - De base tous les poids sont à 0.
	 - List des attributs : *army*, *sharpArmy*, *rangeArmy*, *poidsArmy*, *food*, *sharpFood*, *rangeFood*, *poidsFood*, *money*, *sharpMoney*, *rangeMoney*, *poidsMoney*, *population*, *sharpPopulation*, *rangePopulation*, *poidsPopulation*, *maxPoids*.
	 - Aucun attribut est obligatoire.
	 - La valeur de base de *sharp...* est **1**
	 - La valeur de base de *range...* est **1.5**
	 - La valeur de base de *maxPoids* est **100**
	 - Le *maxPoids* est la valeur qu'aura le poids si il correspond exactement à la gauge du joueur.


Random Attributs
----------------

RandomNextCard:
	.. code-block:: xml
		
		<Card>
			<RandomNextCard prob="0.7" idCard1="Card1" idCard2="Card2" side="left" />
		<Card>
	..
	
	 - Cette attribut permet de choisir aléatoirement entre 2 cartes.
	 - Dans l'exemple ci-dessus la carte définie par l'attribut *idCard1* de valeur *Card1* a **0.7**(70%) de chance et donc **0.3**(30%) de chance d'avoir *idCard2*.

AddRandomDelayedCard:
	.. code-block:: xml
		<Card>
			<AddRandomDelayedCard prob="0.7" idCard1="Card1" idCard2="Card2" turn="1" side="left" />
		<Card>
	..
	
	 - Cette attribut permet de choisir aléatoirement entre 2 cartes et d'ajouter la carte choisi dnas un certain nombre de tour.
	 - *prob* correspond à la probabilité que ce soit *idCard1* qui soit choisie. Ainsi *idCard2* à 30% de chance d'être choisie.
	 - *idCard1* et *idCard2* sont les identifiants des deux cartes.
	 - *turn* correspond au nombre de tour séparant le tour actuel du moment où le joueur a une chance de piocher la carte choisie aléatoirement.
	 - *side* permet de définir si l'action doit être éxécuté lorsque le joueur swipe à droit (*right*) ou à gauche (*left*).


.. toctree::
   :maxdepth: 2
   :caption: Contents:


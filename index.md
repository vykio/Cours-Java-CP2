
# Java - Cours1

[Cours Suivant (#2)](https://vykio.github.io/Cours-Java-CP2/2.md "Cours Java n°2")

# Les tableaux:

   Les tableaux sont des objets.
    **syntaxe**: 
`type [] nomDuTableau;`
    
   *exemple*: 
    
	    int [] tableau;
	    tableau = new int[50];
	    int [] tab2 = tableau; /* tab2 est le meme tableau que "tableau" */

   Java vérifie dynamiquement que la valeur de l'élément existe sinon : "Erreur OutOfBoundsExecption"

    Taille du tableau: tableau.length;
    Indice max du tableau: tableau.length-1;


# Classes et Objets:

   Orienté Objet (O.O.):
   - Une boite noire
   - Un objet sans classe n'a pas de Classes
   - Héritage
   - UML

  Idée centrale:
            Placer les entités, objets ou acteurs du problème à la base de la conception
            On met en avant les données.

   ► La Classe:
	   • Données **[Attributs]**
	   • Procédures et fonctions **[Méthodes]**

  Elle a: Une **structure** et un **comportement**.

Les objets sont des représentations, on parle **d'instances** du modèle défini dans les Classes
Une classe permet d'instancer (créer) plusieurs modèles

     statique : partagée à toutes les Classes
	 dynamique: propre à chaque Classe

   # Instanciation:
	   new constructeur (<liste de paramètres>)
	 
Les constructeurs ont le même nom que la classe.
Sans paramètre: 

    Etudiant e1;
    e1 = new Etudiant();
    Etudiant e2, e3;
    e2 = new Etudiant();
    e3 = e2; //Exactement le même

# Déclaration des méthodes
1. Constructeurs: Créer des objets
2. Accesseurs: Accéder aux données de nos objets
3. Méthodes de classe

###  Constructeurs
Ils sont appelés qu'une seule fois lors de la création de l'instance.
Il n'est pas obligatoire.
### Accesseurs
Accéder aux attributs d'une classe, éventuellement de les modifier.
### Méthodes de classe
permet de travailler directement sur les instances de classe
Gestion, édition, affichage, calcul sur les objets.

*exemple:*
- toUpper() (mise en majuscule)
- subString() (récupération d'une sous-chaîne

## Méthodes
Déclaration d'une méthode

    <typeRetour> nomMethode( <liste de paramètres> ) {
		<corps de la méthode>
	}

# Gestion de la mémoire
L'instanciation provoque une allocation dynamique de la mémoire.

> En Java, pas de soucis de mémoire.

Si un objet n'est plus référence, la mémoire allouée est libérée automatiquement. Ce processus de libération de la mémoire est appelé **Garbage Collector** ou **Ramasse-miettes**.

# Un constructeur plus élaboré

	public class Etudiant {
		
		String nom;
		String prenom;
		int anneeNaissance;
		int nbNotes;
		int [] notes;
		
		public Etudiant() { //Meme nom que la classe => C'est un constructeur
			nom = "Inconnu";
			prenom = "Inconnu";
			nbNotes = 0;
			notes = new int[20];
		}

		/* Deuxième constructeur */
		public Etudiant(String n, String p, int a) {
			nom = n;
			prenom = p;
			anneeNaissance = a;
			nbNotes = 0;
			notes = new int[20];
		}
	}

> 

	Premier constructeur: Création d'un étudiant
	Deuxième constructeur: Création de l'étudiant Jean Dupont

> Le constructeur sera choisi selon ses paramètres

# L'objet "This"

Mot clé désignant l'objet courant. 

	public Etudiant(String n, String p, int a) {
		this.nom = n;
		this.prenom = p;
		this.anneeNaissance = a;
		this.nbNotes = 0;
		this.notes = new int[20];
	}

# Accès aux attributs d'un objet
On utilise la notation :

    nomObjet.nomAttribut

On utilisera le principe d'**encapsulation**

# Encapsulation

Trois types:
- **private**
- **public**
- protected

# Exercice
> Créer une classe Voiture
> - Année (millésime)
> - Marque
> - Couleur
> - Neuve (Boolean)

    public class Voiture {
	
		private int annee;
		private String marque;
		private String couleur;
		private boolean neuve;

		public Voiture (String marque, String couleur, int annee, boolean neuve) {
			this.annee = annee;
			this.marque = marque;
			this.couleur = couleur;
			this.neuve = neuve;
			System.out.println("Voiture créée: "+ this.marque + " " + this.couleur+ " de " + this.annee);
		}

	}

---------------
> Créer classe équation pour résoudre les équations du second degré
> - eq.discriminant()
> - eq.resolution()

    public class Equation {
		
		private double a;
		private double b;
		private double c;
		
		public Equation(double a, double b, double c) {
			this.a = a;
			this.b = b;
			this.c = c;
		}

		public double discriminant() {
			return (this.b*this.b-4*this.a*this.c);
		}

		public void resolution() {
			double d = discriminant();
			if (d>0.0) {
				/* Afficher les racines... */
			}
		}

	}

# 📘 Cours complet — UC D41.2
## Développement et bases de données — Fondamentaux
### Avec un cours Java intégré (départ niveau zéro)

> Objectif : t'amener de **« je n'ai jamais fait de Java »** à **« je sais répondre à toutes les questions du sujet »** en 2h de lecture.
> Format : on construit chaque notion, exemple par exemple, puis on l'applique au sujet de janvier 2025.

---

## 🗺️ Plan du cours

1. **Partie I — Java de A à Z** (variables, classes, objets, héritage, collections)
2. **Partie II — Java Swing** (interfaces graphiques)
3. **Partie III — Java Servlets** (Java côté serveur web)
4. **Partie IV — PHP & cURL** (l'essentiel pour le sujet)
5. **Partie V — Oracle SQL** (CREATE TABLE, séquence, trigger, requêtes)
6. **Partie VI — MongoDB** (NoSQL, mongosh)
7. **Partie VII — Application complète au sujet de janvier 2025**
8. **Partie VIII — Fiche mémo finale**

---

# 🌱 PARTIE I — JAVA DE A À Z

## 1.1 Qu'est-ce que Java ?

Java est un **langage de programmation orienté objet**, créé en 1995, conçu pour être :
- **Portable** : « write once, run anywhere » → ton code tourne sur n'importe quel OS (Windows, Linux, Mac) grâce à la JVM (Java Virtual Machine).
- **Fortement typé** : chaque variable a un **type fixe**, déclaré à l'avance.
- **Orienté objet** : tout (ou presque) est un **objet**.

### Cycle de vie du code Java

```
Code source (.java)  →  [Compilation javac]  →  Bytecode (.class)  →  [Exécution JVM]  →  Programme
```

---

## 1.2 Le squelette d'un programme Java

Tout programme Java commence par une **classe** qui contient une méthode `main` :

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

**À retenir :**
- `public class HelloWorld` : déclaration d'une classe nommée HelloWorld (le fichier **doit** s'appeler `HelloWorld.java`).
- `public static void main(String[] args)` : c'est **toujours** la signature du point d'entrée du programme.
- `System.out.println(...)` : affiche du texte dans la console.
- Chaque instruction se termine par un `;`.
- Les blocs de code sont délimités par `{ }`.

---

## 1.3 Les variables et les types

Une variable a un **type**, un **nom** et une **valeur**.

```java
int age = 25;
double prix = 19.99;
String nom = "Alice";
boolean estConnecte = true;
char initiale = 'A';
```

### Les types primitifs essentiels

| Type | Description | Exemple |
|---|---|---|
| `int` | Entier (4 octets) | `int x = 42;` |
| `long` | Grand entier (8 octets) | `long pop = 8000000000L;` |
| `float` | Décimal (4 octets) | `float p = 19.99f;` |
| `double` | Décimal précis (8 octets) | `double pi = 3.14159;` |
| `boolean` | Vrai ou faux | `boolean ok = true;` |
| `char` | Un seul caractère | `char c = 'A';` |
| `String` | Chaîne de caractères (objet) | `String s = "Hello";` |

> ⚠️ `String` commence par une **majuscule** : ce n'est pas un type primitif, c'est une **classe**.

---

## 1.4 Les opérateurs

### Arithmétiques
`+`, `-`, `*`, `/`, `%` (modulo)

```java
int somme = 5 + 3;        // 8
int reste = 10 % 3;       // 1
```

### Comparaison
`==`, `!=`, `<`, `>`, `<=`, `>=`

```java
if (age >= 18) { ... }
```

### Logiques
- `&&` : ET
- `||` : OU
- `!` : NON

```java
if (age >= 18 && estConnecte) { ... }
```

---

## 1.5 Structures de contrôle

### `if / else`
```java
if (age >= 18) {
    System.out.println("Majeur");
} else {
    System.out.println("Mineur");
}
```

### `for`
```java
for (int i = 0; i < 5; i++) {
    System.out.println(i);   // affiche 0, 1, 2, 3, 4
}
```

### `while`
```java
int n = 0;
while (n < 5) {
    System.out.println(n);
    n++;
}
```

### `for-each` (pour parcourir une collection)
```java
for (String mot : maListe) {
    System.out.println(mot);
}
```

---

## 1.6 Les tableaux

```java
int[] notes = {12, 15, 18, 9};
notes[0] = 14;             // accès par index (commence à 0)
int taille = notes.length; // 4
```

Mais en pratique, on utilise plus souvent les **collections** (voir 1.13).

---

## 1.7 Les méthodes

Une méthode = un bloc de code réutilisable.

```java
public int addition(int a, int b) {
    return a + b;
}
```

- `public` : visible partout
- `int` : type de retour
- `addition` : nom
- `(int a, int b)` : paramètres
- `return` : valeur renvoyée

Si la méthode ne renvoie rien : `void`.

```java
public void direBonjour() {
    System.out.println("Bonjour !");
}
```

---

## 1.8 🎯 LE CŒUR DU JAVA : les classes et les objets

**C'est LA notion à maîtriser absolument** pour ton exam.

### Qu'est-ce qu'une classe ?

Une **classe** est un **plan** qui décrit ce qu'est un objet.
Un **objet** est une **instance** (un exemplaire concret) de cette classe.

**Analogie :** la classe c'est le **plan d'une voiture** ; les objets ce sont les **voitures construites** à partir de ce plan.

### Exemple minimal

```java
public class Voiture {
    // Attributs (caractéristiques)
    String marque;
    int annee;
    
    // Constructeur (appelé à la création de l'objet)
    public Voiture(String marque, int annee) {
        this.marque = marque;
        this.annee = annee;
    }
    
    // Méthode (action que l'objet sait faire)
    public void demarrer() {
        System.out.println(this.marque + " démarre !");
    }
}
```

**Utilisation :**
```java
Voiture v1 = new Voiture("Renault", 2020);
v1.demarrer();   // Affiche : "Renault démarre !"
```

### Décortiquons :

- **Attribut** : une variable qui appartient à la classe (`marque`, `annee`).
- **Constructeur** : méthode spéciale qui **a le même nom que la classe** et qui sert à **initialiser un nouvel objet**. Pas de type de retour.
- **`this`** : référence à **l'objet courant** (utile pour distinguer un attribut d'un paramètre du même nom).
- **`new`** : mot-clé qui **crée un nouvel objet** (appelle le constructeur).
- **`v1.demarrer()`** : on appelle une méthode **sur** un objet.

---

## 1.9 L'encapsulation : getters et setters

**Principe :** on protège les attributs de la classe en les rendant **privés**, et on fournit des méthodes publiques pour y accéder.

```java
public class Voiture {
    private String marque;   // privé : inaccessible de l'extérieur
    private int annee;
    
    public Voiture(String marque, int annee) {
        this.marque = marque;
        this.annee = annee;
    }
    
    // Getter (lire)
    public String getMarque() {
        return marque;
    }
    
    // Setter (écrire)
    public void setMarque(String marque) {
        this.marque = marque;
    }
    
    public int getAnnee() { return annee; }
    public void setAnnee(int annee) { this.annee = annee; }
}
```

> 🧠 **Convention :** pour un attribut `xxx`, le getter est `getXxx()` et le setter est `setXxx(...)`.
> Pour un `boolean`, le getter peut être `isXxx()`.

---

## 1.10 Niveaux de visibilité

| Modificateur | Accessible depuis... |
|---|---|
| `public` | Partout |
| `private` | Seulement dans la même classe |
| `protected` | La classe + ses sous-classes + même package |
| (rien) | Même package uniquement |

> ✅ **Bonne pratique** : attributs `private`, méthodes utiles `public`.

---

## 1.11 L'héritage

Une classe peut **hériter** d'une autre avec `extends`.

```java
public class Animal {
    protected String nom;
    
    public Animal(String nom) {
        this.nom = nom;
    }
    
    public void dormir() {
        System.out.println(nom + " dort.");
    }
}

public class Chien extends Animal {
    public Chien(String nom) {
        super(nom);    // appelle le constructeur parent
    }
    
    public void aboyer() {
        System.out.println(nom + " : Ouaf !");
    }
}
```

**Utilisation :**
```java
Chien c = new Chien("Rex");
c.aboyer();   // méthode propre à Chien
c.dormir();   // méthode héritée d'Animal
```

> 🔑 `super` = "le parent". Sert à appeler le constructeur ou les méthodes de la classe parente.

---

## 1.12 La surcharge (`@Override`)

Une sous-classe peut **redéfinir** une méthode du parent :

```java
public class Chat extends Animal {
    public Chat(String nom) { super(nom); }
    
    @Override
    public void dormir() {
        System.out.println(nom + " ronronne en dormant.");
    }
}
```

`@Override` est une **annotation** : elle indique au compilateur que tu surcharges une méthode existante. Si tu te trompes de signature, le compilateur t'avertira.

---

## 1.13 Les collections : `List` et `ArrayList`

Pour stocker une liste d'objets, on utilise une **collection**. La plus courante : `ArrayList`.

```java
import java.util.ArrayList;
import java.util.List;

List<String> noms = new ArrayList<>();
noms.add("Alice");
noms.add("Bob");
noms.add("Charlie");

System.out.println(noms.size());     // 3
System.out.println(noms.get(0));     // "Alice"
noms.remove("Bob");

for (String n : noms) {
    System.out.println(n);
}
```

> 🔑 `List<String>` : c'est une **liste de String**. Les chevrons `< >` indiquent le **type des éléments** (génériques). On peut aussi avoir `List<Item>`, `List<Integer>`, etc.

### Méthodes essentielles
| Méthode | Effet |
|---|---|
| `add(e)` | Ajoute un élément |
| `remove(e)` | Supprime un élément |
| `get(i)` | Récupère l'élément à l'index i |
| `size()` | Nombre d'éléments |
| `contains(e)` | True si l'élément est présent |
| `isEmpty()` | True si la liste est vide |

---

## 1.14 🎯 Application : passer d'un diagramme UML à du code Java

Le diagramme UML représente une classe avec :
- Le nom de la classe en haut
- Les **attributs** (avec `-` privé, `+` public, `#` protégé, `o` package)
- Les **méthodes** en bas

### Exemple : la classe `User` du sujet

UML :
```
┌─────────────────┐
│      User       │
├─────────────────┤
│ o name : String │
│ o email: String │
├─────────────────┤
│ • login()       │
│ • logout()      │
└─────────────────┘
```

Traduction Java :

```java
public class User {
    private String name;
    private String email;
    
    // Constructeur
    public User(String name, String email) {
        this.name = name;
        this.email = email;
    }
    
    // Getters / Setters
    public String getName() { return name; }
    public void setName(String name) { this.name = name; }
    
    public String getEmail() { return email; }
    public void setEmail(String email) { this.email = email; }
    
    // Méthodes métier
    public void login() {
        System.out.println(name + " s'est connecté.");
    }
    
    public void logout() {
        System.out.println(name + " s'est déconnecté.");
    }
}
```

### Méthode systématique pour traduire un UML :
1. Crée la classe `public class NomClasse { ... }`
2. Pour chaque attribut UML : ajoute `private TypeAttribut nomAttribut;`
3. Ajoute un **constructeur** avec tous les attributs en paramètres
4. Ajoute les **getters/setters** pour chaque attribut
5. Pour chaque méthode UML : ajoute la méthode avec sa signature

---

## 1.15 Les relations entre classes (UML → Java)

### Association "1 vers plusieurs" : agrégation par liste

UML : `ShoppingCart` contient **plusieurs** `Item` (`List<Item> items`)

```java
import java.util.ArrayList;
import java.util.List;

public class ShoppingCart {
    private List<Item> items;
    
    public ShoppingCart() {
        this.items = new ArrayList<>();
    }
    
    public void addItem(Item item) {
        items.add(item);
    }
    
    public void removeItem(Item item) {
        items.remove(item);
    }
    
    public float calculateTotal() {
        float total = 0;
        for (Item item : items) {
            total += item.getPrice();
        }
        return total;
    }
    
    public List<Item> getItems() { return items; }
}
```

> 🧠 Ici, on **initialise la liste dans le constructeur** : sinon `items` serait `null` et on aurait une `NullPointerException` au premier `add`.

---

# 🖼️ PARTIE II — JAVA SWING (interfaces graphiques)

## 2.1 Concept

**Swing** est la bibliothèque historique de Java pour créer des fenêtres et des interfaces graphiques (boutons, champs, etc).

Une appli Swing minimale :
```java
import javax.swing.*;

public class MaFenetre {
    public static void main(String[] args) {
        JFrame frame = new JFrame("Ma fenêtre");
        frame.setSize(400, 300);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setVisible(true);
    }
}
```

## 2.2 Les composants essentiels

| Composant | Rôle |
|---|---|
| `JFrame` | La fenêtre principale |
| `JLabel` | Un texte ou une image à afficher |
| `JButton` | Un bouton cliquable |
| `JTextField` | Un champ de saisie texte |
| `JPanel` | Un conteneur (groupe d'éléments) |

## 2.3 Méthodes courantes

```java
component.setBounds(x, y, largeur, hauteur);   // positionnement absolu
component.setText("Salut !");
frame.add(component);                          // ajoute le composant à la fenêtre
frame.setVisible(true);
frame.setLayout(null);                         // désactive le layout auto
```

## 2.4 Les listeners (réagir à un événement)

Pour qu'un clic provoque une action :

```java
JButton bouton = new JButton("Clique-moi");
bouton.addActionListener(e -> {
    System.out.println("Bouton cliqué !");
});
```

> 🔑 La flèche `e -> { ... }` est une **lambda expression** : un code anonyme qui sera exécuté quand l'événement se produit. `e` est l'événement.

### Les autres listeners
- `addMouseListener` : clics souris
- `addMouseMotionListener` : mouvement souris (utilisé dans le sujet)
- `addKeyListener` : clavier

## 2.5 🎯 Analyse du code `Sample2` (Question 3 du sujet)

Reprenons le code du sujet ligne par ligne :

```java
JFrame frame = new JFrame("Confirm");
frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
frame.setSize(600, 400);
frame.setLayout(null);
```
→ Crée une fenêtre de 600×400 pixels qui se ferme proprement à la croix.

```java
JLabel message = new JLabel("Formatting hard drive...");
```
→ Affiche un message **inquiétant** : « Formatage du disque dur en cours ».

```java
JButton button = new JButton("Cancel");
```
→ Crée un bouton « Annuler » (apparemment, pour stopper le formatage).

```java
button.addMouseMotionListener(new MouseAdapter() {
    @Override
    public void mouseMoved(MouseEvent e) {
        // calcule la distance entre la souris et le bouton
        double distance = Math.sqrt(...);
        if (distance < 100) {
            // déplace le bouton à un endroit aléatoire
            int newX = random.nextInt(...);
            int newY = random.nextInt(...);
            button.setLocation(newX, newY);
        }
    }
});
```
→ **Quand la souris s'approche à moins de 100 pixels du bouton**, il **se déplace aléatoirement** dans la fenêtre.

### 💡 Conclusion à donner dans la réponse :

> Ce code crée une **application de farce** (canular). Elle affiche un message angoissant ("Formatting hard drive...") avec un bouton "Cancel" qui **fuit la souris** dès qu'on s'en approche : il devient donc **impossible de cliquer sur "Cancel"**.
>
> On en déduit que :
> - Cette application **n'a aucune utilité fonctionnelle réelle** ; c'est une blague / un piège visuel.
> - Elle **ne formate rien du tout** : c'est un simple JFrame avec un JLabel et un JButton.
> - Elle illustre l'utilisation des **listeners** Swing (`MouseMotionListener`) et du **positionnement absolu** (`setLayout(null)` + `setBounds` + `setLocation`).

---

# 🌐 PARTIE III — JAVA SERVLETS

## 3.1 C'est quoi un Servlet ?

Un **Servlet** est un programme Java qui tourne sur un **serveur web** (Tomcat, Jetty…) et qui répond aux requêtes HTTP des navigateurs.

```
Navigateur  ──── requête HTTP (GET/POST) ────►  Servlet  ──── réponse HTML ────►  Navigateur
```

## 3.2 Squelette d'un Servlet

Tout Servlet HTTP **hérite de `HttpServlet`** :

```java
import java.io.IOException;
import java.io.PrintWriter;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

public class MonServlet extends HttpServlet {
    
    @Override
    protected void doGet(HttpServletRequest request, 
                         HttpServletResponse response) throws IOException {
        response.setContentType("text/html");
        PrintWriter out = response.getWriter();
        out.println("<h1>Bonjour !</h1>");
    }
}
```

### Les méthodes clés :

| Méthode | Quand est-elle appelée ? |
|---|---|
| `doGet(req, resp)` | Quand le navigateur fait une requête GET |
| `doPost(req, resp)` | Quand le navigateur fait une requête POST (souvent un formulaire) |

### Récupérer un paramètre du formulaire :

```java
String nom = request.getParameter("name");
```

### Écrire la réponse :

```java
PrintWriter out = response.getWriter();
out.println("<p>Bonjour " + nom + "</p>");
```

## 3.3 🎯 Réponse à la Question 4 du sujet

Code à compléter :
```java
public class FormServlet extends ________ {
    @Override
    protected void doPost(HttpServletRequest request, 
                          HttpServletResponse response) {
        response.setContentType("text/html");
        String name = ______.getParameter("name");
        PrintWriter out = _____.getWriter();
        // ...
    }
}
```

**Réponses, dans l'ordre :**

| Blanc n° | Réponse |
|---|---|
| 1 | `HttpServlet` |
| 2 | `request` |
| 3 | `response` |

---

# 🐘 PARTIE IV — PHP & cURL

## 4.1 PHP en 30 secondes

PHP est un langage de script **côté serveur** très utilisé pour les sites web.

```php
<?php
$nom = "Alice";          // les variables commencent par $
$age = 25;
echo "Bonjour " . $nom;  // . concatène les chaînes
?>
```

Particularités :
- Les variables commencent par `$`.
- Pas besoin de déclarer un type (typage dynamique).
- `echo` affiche du texte.
- `.` concatène les chaînes (pas `+` !).

## 4.2 cURL : appeler une API depuis PHP

**cURL** = bibliothèque pour faire des **requêtes HTTP** depuis PHP (appeler une API, télécharger une page…).

### Squelette d'un appel cURL

```php
$url = "https://api.example.com/data";

// 1. Initialiser
$ch = curl_init($url);

// 2. Configurer les options
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);

// 3. Exécuter
$response = curl_exec($ch);

// 4. Gérer les erreurs
if (curl_errno($ch)) {
    echo "Erreur : " . curl_error($ch);
} else {
    echo $response;
}

// 5. Fermer
curl_close($ch);
```

### Les 4 fonctions clés à connaître

| Fonction | Rôle |
|---|---|
| `curl_init($url)` | Crée et initialise une session cURL vers l'URL |
| `curl_setopt($ch, OPT, val)` | Configure une option (ex: récupérer la réponse en variable) |
| `curl_exec($ch)` | **Exécute** la requête, renvoie la réponse |
| `curl_close($ch)` | Libère la session |

### `CURLOPT_RETURNTRANSFER = true`
→ La réponse est **renvoyée par `curl_exec`** au lieu d'être affichée directement. **À mettre quasiment toujours.**

## 4.3 🎯 Réponse à la Question 5 du sujet

Code à compléter :
```php
$url = "https://api.sample.com/posts/1";
$ch = ________($url);
curl_set_____($ch, CURLOPT_RETURNTRANSFER, true);
$response = _____($ch);
```

**Réponses, dans l'ordre :**

| Blanc n° | Réponse |
|---|---|
| 1 | `curl_init` |
| 2 | `opt` (donc `curl_setopt`) |
| 3 | `curl_exec` |

---

# 🗄️ PARTIE V — ORACLE SQL

## 5.1 Rappel SQL

SQL = **Structured Query Language**. Permet de manipuler des bases de données relationnelles.

On distingue :
- **DDL** (Data Definition Language) : `CREATE`, `ALTER`, `DROP` — structurer la base.
- **DML** (Data Manipulation Language) : `SELECT`, `INSERT`, `UPDATE`, `DELETE` — manipuler les données.

## 5.2 Créer une table avec contraintes

```sql
CREATE TABLE NomTable (
    colonne1 TYPE [contrainte],
    colonne2 TYPE [contrainte],
    ...
);
```

### Les contraintes essentielles

| Contrainte | Effet |
|---|---|
| `PRIMARY KEY` | Clé primaire (unique + non null) |
| `NOT NULL` | La colonne ne peut pas être vide |
| `UNIQUE` | Toutes les valeurs doivent être différentes |
| `FOREIGN KEY ... REFERENCES` | Clé étrangère vers une autre table |
| `DEFAULT valeur` | Valeur par défaut |
| `CHECK (condition)` | Validation |

### Exemple type

```sql
CREATE TABLE Etudiant (
    id INT PRIMARY KEY,
    nom VARCHAR(50) NOT NULL,
    email VARCHAR(100) UNIQUE,
    classe_id INT,
    CONSTRAINT fk_classe FOREIGN KEY (classe_id) REFERENCES Classe(id)
);
```

## 5.3 🎯 Question 1 D2 : créer la table `ShoppingCart`

D'après l'annexe 2, `ShoppingCart` a :
- `id` (INT, clé primaire)
- `user_id` (INT, clé étrangère vers `User.id`)

```sql
CREATE TABLE ShoppingCart (
    id INT PRIMARY KEY,
    user_id INT NOT NULL,
    CONSTRAINT fk_shoppingcart_user 
        FOREIGN KEY (user_id) REFERENCES "User"(id)
);
```

> ⚠️ Astuce Oracle : `USER` est un **mot réservé** en Oracle (renvoie le nom de l'utilisateur courant). Si la table s'appelle vraiment `User`, on la met entre `"guillemets doubles"` ou on la renomme (`AppUser`, `Users`, etc). Pour l'exam, écris-le entre guillemets pour montrer que tu connais le piège, ou précise-le en commentaire.

---

## 5.4 Séquences et triggers Oracle (auto-incrémentation)

**Problème :** dans Oracle 11, **il n'existe pas** la clause `AUTO_INCREMENT` (contrairement à MySQL) ni `GENERATED AS IDENTITY` (apparue en Oracle 12).

**Solution :** on crée :
1. une **séquence** (générateur de nombres incrémentés)
2. un **trigger** qui s'exécute avant chaque `INSERT` pour remplir la colonne `id` à partir de la séquence

### Créer une séquence

```sql
CREATE SEQUENCE shoppingcart_seq
    START WITH 1
    INCREMENT BY 1
    NOCACHE
    NOCYCLE;
```

- `START WITH 1` : démarre à 1
- `INCREMENT BY 1` : +1 à chaque fois
- `NOCACHE` : pas de cache (évite les trous)
- `NOCYCLE` : ne reboucle pas

### Créer un trigger BEFORE INSERT

```sql
CREATE OR REPLACE TRIGGER shoppingcart_bi
BEFORE INSERT ON ShoppingCart
FOR EACH ROW
BEGIN
    IF :NEW.id IS NULL THEN
        SELECT shoppingcart_seq.NEXTVAL 
        INTO :NEW.id 
        FROM DUAL;
    END IF;
END;
/
```

### Décortiquons :

- `CREATE OR REPLACE TRIGGER nom` : crée ou remplace le trigger
- `BEFORE INSERT ON ShoppingCart` : déclenché **avant** chaque insertion
- `FOR EACH ROW` : pour **chaque ligne** insérée (pas en bloc)
- `:NEW.id` : référence à la nouvelle valeur de la colonne id
- `shoppingcart_seq.NEXTVAL` : prend la prochaine valeur de la séquence
- `FROM DUAL` : table technique d'Oracle pour les SELECT sans table réelle
- `/` : termine le bloc PL/SQL

> 🧠 **Logique :** « Avant d'insérer une ligne dans ShoppingCart, si l'id n'est pas fourni, prends la prochaine valeur de la séquence et mets-la dans l'id. »

---

## 5.5 Les requêtes SELECT

### Syntaxe générale
```sql
SELECT colonnes
FROM table
[JOIN autre_table ON condition]
[WHERE conditions]
[GROUP BY ...]
[HAVING ...]
[ORDER BY ...];
```

### Jointures

```sql
SELECT u.username, sc.id
FROM "User" u
JOIN ShoppingCart sc ON u.id = sc.user_id;
```

### Fonctions d'agrégation

| Fonction | Effet |
|---|---|
| `COUNT(*)` | Compte les lignes |
| `SUM(colonne)` | Somme |
| `AVG(colonne)` | Moyenne |
| `MIN`/`MAX` | Min / Max |

### GROUP BY

```sql
SELECT user_id, COUNT(*) AS nb_paniers
FROM ShoppingCart
GROUP BY user_id;
```

→ « Pour chaque user_id, compte combien de paniers il a. »

### ORDER BY

```sql
ORDER BY total DESC   -- du plus grand au plus petit
ORDER BY nom ASC      -- ordre alphabétique
```

---

## 5.6 🎯 Question 3 D2 : prix total du ShoppingCart n°10

Logique :
- `ShoppingCartItem` contient `cart_id`, `item_id`, `quantity`
- `Item` contient `price`
- **Total** = somme de `quantity × price` pour tous les items du panier 10

```sql
SELECT SUM(sci.quantity * i.price) AS prix_total
FROM ShoppingCartItem sci
JOIN Item i ON sci.item_id = i.id
WHERE sci.cart_id = 10;
```

## 5.7 🎯 Question 4 D2 : utilisateurs avec les paniers les plus chers

```sql
SELECT u.username, 
       SUM(sci.quantity * i.price) AS total_panier
FROM "User" u
JOIN ShoppingCart sc ON u.id = sc.user_id
JOIN ShoppingCartItem sci ON sc.id = sci.cart_id
JOIN Item i ON sci.item_id = i.id
GROUP BY u.username
ORDER BY total_panier DESC;
```

**Variante pour avoir seulement le top (Oracle 12+ ou avec ROWNUM en Oracle 11) :**

```sql
SELECT * FROM (
    SELECT u.username, SUM(sci.quantity * i.price) AS total_panier
    FROM "User" u
    JOIN ShoppingCart sc ON u.id = sc.user_id
    JOIN ShoppingCartItem sci ON sc.id = sci.cart_id
    JOIN Item i ON sci.item_id = i.id
    GROUP BY u.username
    ORDER BY total_panier DESC
)
WHERE ROWNUM <= 5;   -- top 5
```

---

# 🍃 PARTIE VI — MONGODB

## 6.1 Concepts de base

MongoDB est une base de données **NoSQL orientée documents**.

### Vocabulaire

| Relationnel (SQL) | MongoDB |
|---|---|
| Base de données | Database |
| Table | **Collection** |
| Ligne | **Document** (JSON / BSON) |
| Colonne | **Champ** |

### Un document MongoDB ressemble à un objet JSON :

```javascript
{
    "_id": ObjectId("64f5a8d5a1d2f1a8d4c8f26b"),
    "title": "Harry Potter",
    "author": "J.K. Rowling",
    "price": 19.99,
    "tags": ["fantasy", "magic"]
}
```

- `_id` : **identifiant unique automatique** (de type ObjectId)
- Les champs sont **clé : valeur**
- Pas de schéma fixe : chaque document peut avoir des champs différents

### `mongosh` = le shell MongoDB (JavaScript)

Les commandes sont écrites en JavaScript.

---

## 6.2 Les opérations CRUD

### CREATE (insérer)

```javascript
// Insérer un document
db.maCollection.insertOne({ nom: "Alice", age: 30 });

// Insérer plusieurs
db.maCollection.insertMany([
    { nom: "Bob", age: 25 },
    { nom: "Carla", age: 28 }
]);
```

### READ (lire)

```javascript
// Tous les documents
db.maCollection.find();

// Avec filtre
db.maCollection.find({ age: 30 });

// Un seul document
db.maCollection.findOne({ nom: "Alice" });
```

### Opérateurs de comparaison
| Opérateur | Effet |
|---|---|
| `$eq` | égal |
| `$ne` | différent |
| `$gt`, `$gte` | > , >= |
| `$lt`, `$lte` | <, <= |
| `$in` | dans une liste |

Exemple :
```javascript
db.maCollection.find({ age: { $gt: 25 } });
```

### UPDATE (modifier)

```javascript
db.maCollection.updateOne(
    { nom: "Alice" },                  // filtre
    { $set: { age: 31 } }              // modification
);
```

Pour mettre à jour plusieurs documents : `updateMany`.

### DELETE (supprimer)

```javascript
db.maCollection.deleteOne({ nom: "Alice" });
db.maCollection.deleteMany({ age: { $lt: 18 } });
```

---

## 6.3 Créer une collection

Deux façons :

```javascript
// 1. Explicite
db.createCollection("orders");

// 2. Implicite (la collection est créée automatiquement à l'insertion)
db.orders.insertOne({ ... });
```

---

## 6.4 🎯 Réponses aux questions D3 du sujet

### Q1 : créer `orders` et insérer le document

```javascript
db.createCollection("orders");

db.orders.insertOne({
    customer_id: ObjectId("64f5a8d5a1d2f1a8d4c8f28d"),
    order_date: ISODate("2024-01-15T00:00:00Z"),
    items: [
        {
            book_id: ObjectId("64f5a8d5a1d2f1a8d4c8f26b"),
            quantity: 1
        },
        {
            book_id: ObjectId("64f5a8d5a1d2f1a8d4c8f27c"),
            quantity: 2
        }
    ],
    total_amount: 59.97
});
```

### Q2 : afficher tous les livres écrits par J.K. Rowling

```javascript
db.books.find({ author: "J.K. Rowling" });
```

### Q3 : rechercher un utilisateur par son email

```javascript
db.customers.findOne({ email: "emily.watson@example.com" });
```

> 💡 `findOne` renvoie **un seul** document (le premier qui correspond). Comme un email est unique, c'est la bonne méthode ici.

### Q4 : retrouver une commande à partir d'un utilisateur

```javascript
db.orders.find({ 
    customer_id: ObjectId("64f5a8d5a1d2f1a8d4c8f28d") 
});
```

### Q5 : fixer le stock à 200 pour un livre via son id

```javascript
db.books.updateOne(
    { _id: ObjectId("64f5a8d5a1d2f1a8d4c8f26b") },
    { $set: { stock_quantity: 200 } }
);
```

---

# 🎯 PARTIE VII — Récapitulatif complet des réponses au sujet

## Dossier 1 — Langages de développement

| Q | Sujet | Réponse |
|---|---|---|
| 1 | Code Java de la classe User | Voir section 1.14 |
| 2 | Implémentation ShoppingCart | Voir section 1.15 |
| 3 | Que fait Sample2 ? | App farce : bouton "Cancel" qui fuit la souris (voir 2.5) |
| 4 | Compléter FormServlet | 1: `HttpServlet`, 2: `request`, 3: `response` |
| 5 | Compléter PHP cURL | 1: `curl_init`, 2: `opt` (curl_setopt), 3: `curl_exec` |

## Dossier 2 — SQL Oracle

| Q | Sujet | Réponse |
|---|---|---|
| 1 | CREATE TABLE ShoppingCart | Voir section 5.3 |
| 2 | Séquence + trigger | Voir section 5.4 |
| 3 | Prix total cart #10 | Voir section 5.6 |
| 4 | Utilisateurs paniers les plus chers | Voir section 5.7 |

## Dossier 3 — MongoDB

| Q | Sujet | Réponse |
|---|---|---|
| 1 | Créer orders et insérer | Voir section 6.4 |
| 2 | Livres J.K. Rowling | `db.books.find({author: "J.K. Rowling"})` |
| 3 | User par email | `db.customers.findOne({email: "..."})` |
| 4 | Commande par user | `db.orders.find({customer_id: ObjectId("...")})` |
| 5 | Stock livre = 200 | `db.books.updateOne({_id:ObjectId("...")},{$set:{stock_quantity:200}})` |

---

# 📌 PARTIE VIII — Fiche mémo de dernière minute

## Java en 10 points

1. Tout vit dans une **classe**. Le `main` est le point d'entrée.
2. Attribut **privé** (`private`) + getter/setter publics = **encapsulation**.
3. `new MaClasse(...)` crée un **objet** en appelant le **constructeur**.
4. `this.x` = l'attribut `x` de l'objet courant.
5. `extends` = héritage. `super()` appelle le constructeur parent.
6. `@Override` pour redéfinir une méthode héritée.
7. `List<Type>` + `ArrayList<>()` pour les listes. `.add`, `.remove`, `.get`, `.size`.
8. **Swing** : `JFrame`, `JButton`, `addActionListener(e -> {...})`.
9. **Servlet** : étend `HttpServlet`, override `doGet`/`doPost`, `request.getParameter`, `response.getWriter`.
10. `String s = "...";` (majuscule) ≠ `char c = '...';` (minuscule + apostrophes simples).

## PHP cURL en 4 lignes

```php
$ch = curl_init($url);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
$response = curl_exec($ch);
curl_close($ch);
```

## SQL Oracle — les 5 patterns à connaître

1. **Création de table avec FK** :
```sql
CREATE TABLE T (
    id INT PRIMARY KEY,
    autre_id INT,
    CONSTRAINT fk FOREIGN KEY (autre_id) REFERENCES Autre(id)
);
```

2. **Séquence** :
```sql
CREATE SEQUENCE nom_seq START WITH 1 INCREMENT BY 1;
```

3. **Trigger d'auto-incrément** :
```sql
CREATE OR REPLACE TRIGGER t_bi
BEFORE INSERT ON T FOR EACH ROW
BEGIN
    IF :NEW.id IS NULL THEN
        SELECT nom_seq.NEXTVAL INTO :NEW.id FROM DUAL;
    END IF;
END;
/
```

4. **Jointure + agrégation** :
```sql
SELECT t1.col, SUM(t2.valeur)
FROM t1 JOIN t2 ON t1.id = t2.t1_id
GROUP BY t1.col
ORDER BY SUM(t2.valeur) DESC;
```

5. **Total avec quantité × prix** :
```sql
SELECT SUM(quantity * price) FROM ... WHERE ...;
```

## MongoDB — les 5 commandes à mémoriser

```javascript
// Insérer
db.coll.insertOne({ ... });

// Lire tous / un seul
db.coll.find({ champ: valeur });
db.coll.findOne({ champ: valeur });

// Mettre à jour
db.coll.updateOne({ filtre }, { $set: { champ: valeur } });

// Supprimer
db.coll.deleteOne({ filtre });

// Créer une collection
db.createCollection("nom");
```

---

## 🚀 Conseils de méthode pour le jour J (2h, 3 dossiers)

1. **Lis tout le sujet d'abord**, repère ce qui te paraît le plus simple.
2. **Commence par les questions à code court** : MongoDB Q2-Q5, PHP, complétion Servlet → vite gagnées.
3. **Java UML → code** : prends le réflexe attributs privés + constructeur + getters/setters. C'est de la cuisine, fais-le systématiquement.
4. **Le trigger Oracle** est le plus dense : **apprends-le par cœur** comme un pattern.
5. **SQL avec JOIN + GROUP BY** : si tu doutes, dessine d'abord ce que tu veux récupérer sur papier.
6. **Sois précis sur la syntaxe** : `;` à la fin des instructions Java/SQL, parenthèses bien fermées.
7. **Si tu bloques sur une question, passe à la suivante**. Ne reste pas figé.

Bonne révision Baron, tu vas y arriver ! 💪

> Si tu veux qu'on approfondisse une partie (un quiz Java, des exos SQL supplémentaires, plus de pratique MongoDB), demande-moi.

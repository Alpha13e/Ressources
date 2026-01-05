Ce langage est compilé il nécessite donc un compilateur. Celui-ci dépend du langage et du système.
## Comment configurer l'interface avec Vscodium
> C'est similaire mais bien plus facile avec VsCode, et les extensions propriétaires (**C/C++ Extension Pack** de Microsoft).

<u>Extensions:</u>

- **C/C++ Extension Pack (9)**; on remplace C/C++ runner par **Code runner**;
- **changd** : code completion mais flag les fonctions input/output: Pas grave, ça marche.
  
- **Pour utiliser la fonction input:** Activer *Code-runner: Run In Terminal* dans les paramètres *(ctrl + ,)*.

**Pour utiliser `math.h` il fait que le prompt appelant le compilateur (gcc) ait `-lm` avant le `-o`  Voir `code-runner.executorMap` dans les paramètres de VsCode.

# C

<u>**Fonctions utiles:**</u>

- `perror("errorname")` renvoie une erreur
- Pour ouvrir un ficher :
```C
FILE *f; // initie type var
f=fopen("filepath","r+"); //ouvre: r read, w write
if (f == NULL){ // Vérifie que ca marche
    perror("Error: Could not open file\n");
    return 1;
}
else printf("Ex3 is working...\n");
```
  voir cours pr fonctions.
- `while ((c=fgetc(f))!='\n' && c != EOF) i++;` On peut tt faire en 1 ligne
- `strtok`: split. 1er appel `char *n=strtok(l,",\n")` appels suivants `n=strtok(NULL,",\n")`. Coupe à `,` **OU** `\n`.

- Possible méthode utile:
```C
if (c=='\n'){
    fseek(f,-1,SEEK_CUR);// moves back the cursor
    fputc(' ',f); // remplace le caractère
    fflush(f);// force la syncro du buffer, cas spécial en C (changements entre read & write modes)
}
```

> La section **C++** n'indique que les différences, les bases sont ici.

Il y a différentes parties dans un programme, toutes **séparées par des acollades** *(on peut en ajouter sans argument pour avoir des variables locales)*:
- La discussion avec le compilateur avec le `#`. Généralement l'import de bibliothèques, peut aussi devenir des instructions complexes (*if*... Voir Internet pour plus de précisions, ébauche TP1 2025):

```C
#include <stdio.h>      // Manipulation des flux de caractères (dont console).
#include <math.h>       // Maths. Attention au -lm !
#include <stdlib.h>     // Différentes fonctions dont malloc pour la mémoire.
#include <string.h>     // Gestion des chaines de caractères

#define pi 3.143        // Définit un alias. Le compilateur remplacera le premier par le deuxième au début du process.
```
- La déclaration de variables et fonctions globales:

```C
int nom1(char *c, int n) 
void stuff()
```

- Le coeur du programme, appelant les fonctions (début du curseur):
```C
int main(void){
    ...
    return 0; // Succès
}
```
- La définition des fonctions. **Oui c'est pénible mais nécessaire !!**
```C
void stuff(){
    printf('Youpi !');
    ...
}
```
Toute ligne ne s'ouvrant pas sur des acollades se ferme par un point virgule !!!
---

Les commentaires inline sont avec `//`, bloc de texte avec les bornes `/*...*/`. Le premier est originaire de C++, le deuxième de C, les deux sont aujourd'hui compatibles.

## Communication: printf et scanf

```C
printf("%i entier, %c caractère...\n",12,'x');
```

|  Type  | Symbole | Rendu                           |
| :----: | :-----: | ------------------------------- |
|  int   | %d, %i  | Entier relatif                  |
|  int   |   %c    | Caractère                       |
| char*  |   %s    | Chaîne de caractères            |
| double |   %f    | Rationnel notation décimale     |
| double |   %e    | Rationnel notation scientifique |
|  int   |   %u    | unsigned, entier naturel        |
|  int   |   %o    | entier en octal                 |
|  int   |   %x    | entier en hexadécimal           |

```C
scanf("%lf",&var);
```
Même chose, mais le type est un pointeur et on ajoute `%le` ou `%lf` la version double des rationnels décimal/scientifique. %f et %e sont des floats (tjrs pointeurs). On utilise donc `&`.

On evite `getchar()`.

Il existe `strcpy(destination, source)`, fonction permettant de copier une chaîne.

## Variables

Ce langage est bas niveau, très proche de la mémoire, il faut donc y faire attention: **Il alloque la RAM de maniere ABSOLUE !** elle est alors gelée, il faut alors la libérer (voir malloc).

```C
int x=3;
float a,b,c;
a=3.14;
```
<u>Types de variables:</u>

| mot-clé     | description          | domaine              |
| ----------- | -------------------- | -------------------- |
| **char**    | **Caractère unique** | $\pm 128$            |
| **int**     | **entier**           | $\pm 2147483648$     |
| short       | entier court         | $\pm 32768$          |
| long        | entier long ?        | $\pm 2147483648$     |
| **double**  | **flottant moyen**   | $1.7 .10^{\pm 308}$  |
| float       | flottant             | $3.4 .10^{\pm 38}$   |
| long double | grand flottant       | $3.4 .10^{\pm 4932}$ |

On peut forcer un changement de type de deux manières. **C'est nécessaire pour les divisions !**

```C
y= (double)a / (double)b ;
x= a/1.; // Mettre un point ici met 1.0
```

### Booléens
C'est un int qui vaut $0$ si False ; 1 si True (ou tout autre int non nul).

- ET: `&&`
- OU: `||`
- NON: `!`
- Le reste est logique: `==`, `!=`, `>`, `>=`, ...

## Boucles

```C
for (i=1;i<n;i++){ // début, condition d'incrément, incrément
    ...;
}
while (i!=5) // booléen, la boucle ne duraunt qu'une ligne, les accolades sont omises.
    ...;

```
On peut omettre les acollades si la boucle tient en une ligne.

## Pointeurs

- `*` devant élément: pointeur (adresse) de l'élément.
- `&` devant élément: inverse type: 
  - pr pointeur donne valeur;
  - pr valeur donne pointeur ?

- Fonction renvoyant un pointeur : **Elle utilise `malloc`**
- chaine de caracteres: Pointeur du 1er élément, la chaine s'arrete a `\0`. On privilégie.

<u>**Malloc:**</u>

**Exemple:** Initie le pointeur du premier élément d'un tableau `tab[]` avec malloc

```C
int *tab=malloc(nb_element*sizeof(int));
```

## Pseudoclasses

```C
typedef struct{ // Définition de structure
    int numéro1;
    int numéro2;
}Nom_Classe; // Attention, ; ici !

Nom_Classe add(Nom_Classe a, Nom_Classe b); // Annonce fonctions de classe (méthode)
int sqrt(Nom_Classe a);

int main(){
    ...
}

Nom_Classe add(Nom_Classe a, Nom_Classe b){
    ...
    return c
}

int sqrt(Nom_Classe a){
    return a**0.5
}
```

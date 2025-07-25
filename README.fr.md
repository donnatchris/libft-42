##### [🇫🇷 Version française](README.fr.md) / [🇬🇧 English version](README.md)

# PROJET LIBFT POUR 42
Par chdonnat (Christophe Donnat de 42 Perpignan, France)

## BUT DU PROJET :
Vous allez créer votre propre bibliothèque de fonctions, que vous utiliserez tout au long de votre cursus.

### BONUS
Vous devez coder des fonctions de listes chaînées.

## QUELQUES COMMANDES QUE VOUS POUVEZ UTILISER :

compiler la librairie libft pour obtenir le fichier libft.a :

	make

compiler la librairie avec les fonctions de listes chaînées :

	make bonus

supprimer tous les fichiers .o :

	make clean

supprimer tous les fichiers .o et les fichiers exécutables générés par la commande make :

	make fclean

supprimer tous les fichiers .o et les fichiers exécutables générés par la commande make, et recompiler la librairie :

	make re

# LA LIBRAIRIE

## FONCTIONS D'AFFICHAGE ET D'ÉCRITURE

### ft_putchar

`void ft_putchar_fd(char c, int fd);`

> Écrit le caractère c sur le descripteur de fichier fd.

### ft_putstr

`void ft_putstr_fd(char *s, int fd);`

> Écrit la chaîne de caractères s sur le descripteur de fichier fd.

### ft_putendl

`void ft_putendl_fd(char *s, int fd);`

> Écrit la chaîne de caractères s suivie de '\n' sur le descripteur de fichier fd.

### ft_putnbr

`void ft_putnbr_fd(int n, int fd);`

> Écrit l'entier n sur le descripteur de fichier fd.

---

## FONCTIONS DE MANIPULATION DE CARACTÈRES

### ft_isalpha

`int ft_isalpha(int c);`

> Teste si `c` est une lettre (la valeur de l'argument doit être représentable comme un unsigned char ou la valeur de EOF), ce qui correspond à tout caractère entre 65 et 90 ou 97 et 122.
> -> Retourne zéro si le caractère est faux et retourne une valeur non nulle si le caractère est vrai.

### ft_isdigit

`int ft_isdigit(int c);`

> Teste si c'est un chiffre décimal (la valeur de l'argument doit être représentable comme un unsigned char ou la valeur de EOF), ce qui correspond à tout caractère entre 48 et 57.
> -> Retourne 0 si le caractère est faux, ou 1 si le caractère est vrai.

### ft_isalnum

`int ft_isalnum(int c);`

> Teste pour tout caractère pour lequel `ft_isalpha()` ou `ft_isdigit()` est vrai (la valeur de l'argument doit être représentable comme un unsigned char ou la valeur de EOF), ce qui correspond à tout caractère entre 65 et 90, 97 et 122, 48 et 57.
> -> Retourne 0 si le caractère est faux, ou 1 si le caractère est vrai.

### ft_isascii

`int ft_isascii(int c);`

> Teste si c'est un caractère ASCII, ce qui correspond à tout caractère entre 0 et 127.
> -> Retourne 0 si le caractère est faux, ou 1 si le caractère est vrai.

### ft_isprint

`int ft_isprint(int c);`

> Teste pour tout caractère imprimable, y compris l'espace (' ') (la valeur de l'argument doit être représentable comme un unsigned char ou la valeur de EOF), ce qui correspond à tout caractère entre 32 et 126.
> -> Retourne 0 si le caractère est faux ou 1 si le caractère est vrai.

### ft_toupper

`int ft_toupper(int c);`

> Convertit une lettre minuscule en la lettre majuscule correspondante (l'argument doit être représentable comme un unsigned char ou la valeur de EOF).
> -> Si l'argument est une lettre minuscule, la fonction retourne la lettre majuscule correspondante s'il y en a une, sinon, l'argument est retourné inchangé.

### ft_tolower

`int ft_tolower(int c);`

> Convertit une lettre majuscule en la lettre minuscule correspondante (l'argument doit être représentable comme un unsigned char ou la valeur de EOF).
> -> Si l'argument est une lettre majuscule, la fonction retourne la lettre minuscule correspondante s'il y en a une ; sinon, l'argument est retourné inchangé.

---

## FONCTIONS DE MANIPULATION DE CHAÎNES DE CARACTÈRES

### ft_strlen

`size_t ft_strlen(const char *s);`

> Calcule la longueur de la chaîne de caractères s.
> -> Retourne le nombre de caractères qui précèdent le caractère NULL de fin.

### ft_strncmp

`int ft_strncmp(const char *s1, const char *s2, size_t n);`

> Comme `ft_strcmp()` mais `ft_strncmp()` ne compare pas plus de n caractères.
> -> Retourne un entier supérieur, égal ou inférieur à 0, selon que la chaîne s1 est supérieure, égale ou inférieure à la chaîne s2.

### ft_atoi

`int ft_atoi(const char *nptr);`

> Convertit la partie initiale de la chaîne de caractères pointée par nptr en une représentation entière, en ignorant les espaces de début et en arrêtant la conversion au premier caractère non numérique.
> -> Retourne l'entier représenté par les premiers caractères numériques de la chaîne nptr.

### ft_strlcat

`size_t ft_strlcat(char *dst, const char *src, size_t size);`

> Ajoute la chaîne `src` à la fin de la chaîne `dst` (elle ajoutera au plus size - strlen(dst) - 1 caractères), puis elle terminera par un caractère nul, à moins que size soit 0 ou que la chaîne `dst` originale soit plus longue que dstsize.
> -> Retourne la longueur totale de la chaîne qu'elle a essayé de créer (c'est-à-dire la longueur initiale de `dst` plus la longueur de `src`).
> !! Si la valeur de retour est >= `dstsize`, la chaîne de sortie a été tronquée.

### ft_strlcpy

`size_t ft_strlcpy(char *dst, const char *src, size_t size);`

> Copie jusqu'à size - 1 caractères de la chaîne `src` terminée par NUL vers `dst`, en terminant le résultat par NUL.
> -> Retourne la longueur de `src` (ce qui facilite la détection de la troncature).

### ft_strnstr

`char *ft_strnstr(const char *big, const char *little, size_t len);`

> Localise la première occurrence de la chaîne terminée par un nul `little` dans la chaîne `big`, où pas plus de `len` caractères sont recherchés (les caractères qui apparaissent après un caractère '\0' ne sont pas recherchés).
> -> Si `little` est une chaîne vide, `big` est retourné ; si `little` n'apparaît nulle part dans `big`, NULL est retourné ; sinon, un pointeur vers le premier caractère de la première occurrence de `little` est retourné.

---

## FONCTIONS DE MANIPULATION DE LA MÉMOIRE

### ft_bzero

`void ft_bzero(void *s, size_t n);`

> Écrit n octets à zéro dans la chaîne `s`. Si n est nul, `ft_bzero()` ne fait rien.

### ft_calloc

`void *ft_calloc(size_t nmemb, size_t size);`

> Alloue de la mémoire pour un tableau de nmemb éléments de taille size octets chacun. La mémoire est mise à zéro.
> -> Retourne un pointeur vers la mémoire allouée. Si nmemb ou size est nul, retourne une valeur de pointeur unique qui peut être passée à `free()`. Si la multiplication de `nmemb * size` entraînait un débordement d'entier, `calloc()` retourne NULL.

### ft_memset

`void *ft_memset(void *s, int c, size_t n);`

> Écrit n octets de la valeur c (convertie en un unsigned char) dans la chaîne `s`.
> -> Retourne son premier argument.

---

## FONCTIONS DE RAPPEL (CALLBACK)

### ft_striteri

`void ft_striteri(char *s, void (*f)(unsigned int, char *));`

> Applique la fonction f à chaque caractère de la chaîne `s`, en spécifiant son index comme premier argument.

### ft_strmapi

`char *ft_strmapi(char const *s, char (*f)(unsigned int, char));`

> Applique la fonction f à chaque caractère de la chaîne `s`, en spécifiant l'index du caractère, pour créer une nouvelle chaîne allouée avec `malloc()` résultant des applications successives de f.
> -> Retourne la nouvelle chaîne de caractères créée.

---

## FONCTIONS DE MANIPULATION DE LISTES

### ft_lstnew

` t_list *ft_lstnew(void *content);`

> Alloue (avec malloc()) et retourne un nouveau maillon. Le champ content du nouveau maillon est initialisé avec la valeur du paramètre content. Le champ next est initialisé à NULL.
> **Retourne**: Le maillon "frais", ou NULL si l'allocation échoue.

### ft_lstdelone

`void ft_lstdelone(t_list *lst, void (*del)(void *));`

> Libère la mémoire de l'élément passé en paramètre en utilisant la fonction `del`, puis avec `free()`.
> **Note**: La mémoire du champ next n'est pas libérée.

### ft_lstadd_front

`void ft_lstadd_front(t_list **lst, t_list *new);`

> Ajoute l'élément `new` au début de la liste.
> **Paramètres**:
> - `lst` est l'adresse du pointeur vers le premier élément de la liste.
> - `new` est l'adresse du pointeur vers l'élément à ajouter.

### ft_lstsize

`int ft_lstsize(t_list *lst);`

> Compte le nombre d'éléments dans la liste.
> **Paramètres**:
> - `lst` est le début de la liste.
> **Retourne**: Le nombre d'éléments dans la liste.

### ft_lstlast

`t_list *ft_lstlast(t_list *lst);`

> Trouve le dernier élément de la liste.
> **Paramètres**:
> - `lst` est le premier élément de la liste.
> **Retourne**: Le dernier élément de la liste.

### ft_lstadd_back

`void ft_lstadd_back(t_list **lst, t_list *new);`

> Ajoute l'élément `new` à la fin de la liste.
> **Paramètres**:
> - `lst` est l'adresse du pointeur vers le premier élément de la liste.
> - `new` est l'adresse du pointeur vers l'élément à ajouter.

### ft_lstclear

`void ft_lstclear(t_list **lst, void (*del)(void *));`

> Supprime et libère la mémoire de l'élément passé en paramètre et de tous les éléments suivants, en utilisant la fonction `del()` et `free()`. Met le pointeur initial à NULL.
> **Paramètres**:
> - `lst` est l'adresse du pointeur vers un élément.
> - `del` est l'adresse de la fonction qui peut supprimer le contenu d'un élément.

### ft_lstiter

`void ft_lstiter(t_list *lst, void (*f)(void *));`

> Itère sur la liste `lst` et applique la fonction `f()` au contenu de chaque élément.
> **Paramètres**:
> - `lst` est l'adresse du pointeur vers un élément.
> - `f` est l'adresse de la fonction à appliquer.

### ft_lstmap

`t_list *ft_lstmap(t_list *lst, void *(*f)(void *), void (*del)(void *));`

> Itère sur la liste `lst` et applique la fonction `f()` au contenu de chaque élément. Crée une nouvelle liste résultant des applications successives de `f()`. La fonction `del()` est là pour détruire le contenu d'un élément si nécessaire.
> **Retourne**: La nouvelle liste ou NULL si l'allocation échoue.

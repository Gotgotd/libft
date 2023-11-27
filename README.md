# libft

## Partie Obligatoire
**Nom du programme :** libft.a  
**Fichiers de rendu :** Makefile, libft.h, ft_*.c  
**Makefile :** NAME, all, clean, fclean, re  
**Fonctions externes autorisées :** Détails ci-dessous  
**Description :** Créez votre propre bibliothèque contenant des fonctions utiles pour la suite de votre cursus.  

### Considerations techniques
• Interdiction d’utiliser des variables globales.  
• Si vous avez besoin de fonctions auxiliaires pour réaliser une fonction complexe, vous devez définir ces dernières en static dans le respect de la Norme. Ainsi, leur portée sera limitée au fichier concerné.  
• Vous devez rendre tous vos fichiers à la racine de votre dépôt.  
• Il est interdit de rendre des fichiers non utilisés.  
• Chaque fichier .c doit être compilé avec les flags -Wall -Wextra -Werror.  
• Vous devez utiliser la commande ar pour créer votre bibliothèque. L’utilisation de la commande libtool est interdite.  
• Votre libft.a doit être créé à la racine de votre dépôt.  

### Partie 1 - Fonctions de la libc  

Dans cette première partie, vous devez recoder un ensemble de fonctions de la libc telles que décrites dans leur man respectif sur votre système. Vos fonctions devront avoir exactement le même prototype et le même comportement que les originales. Seule différence, leur nom devra être préfixé par ’ft_’. Ainsi, strlen devient ft_strlen.  
  
Vous devez recoder les fonctions suivantes. Elles ne nécessitent aucune fonction externe :  
• isalpha  
• isdigit  
• isalnum  
• isascii  
• isprint  
• strlen  
• memset  
• bzero  
• memcpy  
• memmove  
• strlcpy  
• strlcat  
• toupper  
• tolower  
• strchr  
• strrchr  
• strncmp  
• memchr  
• memcmp  
• strnstr  
• atoi  
  
Pour les deux fonctions suivantes, vous pourrez faire appel à la fonction malloc() :  
  
• calloc  
• strdup  

### Partie 2 - Fonctions supplémentaires  
Dans cette seconde partie, vous devrez implémenter un certain nombre de fonctions absentes de la libc, ou qui y sont mais sous une forme différente  

**Function name :** ft_substr  
**Prototype char :** *ft_substr(char const *s, unsigned int start, size_t len);  
**Fichiers de rendu :** -  
**Paramètres :** s: La chaîne de laquelle extraire la nouvelle chaîne. start: L’index de début de la nouvelle chaîne dans la chaîne ’s’. len: La taille maximale de la nouvelle chaîne.  
**Valeur de retour :** La nouvelle chaîne de caractères. NULL si l’allocation échoue.  
**Fonctions externes autorisées :** malloc  
**Description :** Alloue (avec malloc(3)) et retourne une chaîne de caractères issue de la chaîne ’s’. Cette nouvelle chaîne commence à l’index ’start’ et a pour taille maximale ’len’.  
____________________  
**Function name :** ft_strjoin    
**Prototype char :** *ft_strjoin(char const *s1, char const *s2);    
**Fichiers de rendu :** -  
**Paramètres :** s1: La chaîne de caractères préfixe. s2: La chaîne de caractères suffixe.  
**Valeur de retour :** La nouvelle chaîne de caractères. NULL si l’allocation échoue.  
**Fonctions externes autorisées :** malloc  
**Description :** Alloue (avec malloc(3)) et retourne une nouvelle chaîne, résultat de la concaténation de s1 et s2.  
 ____________________  
**Function name :** ft_strtrim    
**Prototype char :** ft_strtrim(char const *s1, char const *set);    
**Fichiers de rendu :** -  
**Paramètres :** s1: La chaîne de caractères à trimmer. set: Le set de référence de caractères à trimmer.  
**Valeur de retour :** La chaîne de caractères trimmée. NULL si l’allocation échoue.  
**Fonctions externes autorisées :** malloc  
**Description :** Alloue (avec malloc(3)) et retourne une copie de la chaîne ’s1’, sans les caractères spécifiés dans ’set’ au début et à la fin de la chaîne de caractères.  
____________________  
**Function name :** ft_split  
**Prototype char :** **ft_split(char const *s, char c);   
**Fichiers de rendu :** -  
**Paramètres :** s: La chaîne de caractères à découper. c: Le caractère délimiteur.  
**Valeur de retour :** Le tableau de nouvelles chaînes de caractères résultant du découpage.  
**Fonctions externes autorisées :** malloc, free,  
**Description :** Alloue (avec malloc(3)) et retourne un tableau de chaînes de caractères obtenu en séparant ’s’ à l’aide du caractère ’c’, utilisé comme délimiteur. Le tableau doit être terminé par NULL.  
____________________  
**Function name :** ft_itoa  
**Prototype char :** *ft_itoa(int n);   
**Fichiers de rendu :** -  
**Paramètres :** n: L’entier à convertir.  
**Valeur de retour :** La chaîne de caractères représentant l’entier. NULL si l’allocation échoue.  
**Fonctions externes autorisées :** malloc,    
**Description :** Alloue (avec malloc(3)) et retourne une chaîne de caractères représentant l’entier ’n’ reçu en argument. Les nombres négatifs doivent être gérés.  
____________________  
**Function name :** ft_strmapi  
**Prototype char :** **ft_strmapi(char const *s, char (*f)(unsigned int, char));   
**Fichiers de rendu :** -  
**Paramètres :** s: La chaîne de caractères sur laquelle itérer. f: La fonction à appliquer à chaque caractère.  
**Valeur de retour :** La chaîne de caractères résultant des applications successives de ’f’. Retourne NULL si l’allocation échoue.  
**Fonctions externes autorisées :** malloc,    
**Description :** Applique la fonction ’f’ à chaque caractère de la chaîne de caractères passée en argument pour créer une nouvelle chaîne de caractères (avec malloc(3)) résultant des applications successives de ’f’.  
____________________  
**Function name :** ft_striteri  
**Prototype char :** void ft_striteri(char *s, void (*f)(unsigned int, char*));  
**Fichiers de rendu :** -  
**Paramètres :** s: La chaîne de caractères sur laquelle itérer. f: La fonction à appliquer à chaque caractère.  
**Valeur de retour :** Aucune.  
**Fonctions externes autorisées :** Aucune.  
**Description :** Applique la fonction ’f’ à chaque caractère de la chaîne de caractères transmise comme argument, et en passant son index comme premier argument. Chaque caractère est transmis par adresse à ’f’ afin d’être modifié si nécessaire.  
____________________  
**Function name :** ft_putchar_fd  
**Prototype char :** ft_putchar_fd(char c, int fd);  
**Fichiers de rendu :** -  
**Paramètres :** c: Le caractère à écrire. fd: Le descripteur de fichier sur lequel écrire.  
**Valeur de retour :** Aucune.  
**Fonctions externes autorisées :** write.  
**Description :** Écrit le caractère ’c’ sur le descripteur de fichier donné  
____________________  
**Function name :** ft_putstr_fd  
**Prototype char :** void ft_putstr_fd(char *s, int fd);  
**Fichiers de rendu :** -  
**Paramètres :** s: La chaîne de caractères à écrire. fd: Le descripteur de fichier sur lequel écrire.  
**Valeur de retour :** Aucune.  
**Fonctions externes autorisées :** write.  
**Description :** Écrit la chaîne de caractères ’s’ sur le descripteur de fichier donné.  
____________________  
**Function name :** ft_putendl_fd  
**Prototype char :** void ft_putendl_fd(char *s, int fd);  
**Fichiers de rendu :** -  
**Paramètres :** s: La chaîne de caractères à écrire. fd: Le descripteur de fichier sur lequel écrire.  
**Valeur de retour :** Aucune.  
**Fonctions externes autorisées :** write.  
**Description :** Écrit la chaîne de caractères ’s’ sur le descripteur de fichier donné suivie d’un retour à la ligne.  
____________________  
**Function name :** ft_putnbr_fd  
**Prototype char :** void ft_putnbr_fd(int n, int fd);  
**Fichiers de rendu :** -  
**Paramètres :** n: L’entier à écrire. fd: Le descripteur de fichier sur lequel écrire.  
**Valeur de retour :** Aucune.  
**Fonctions externes autorisées :** write.  
**Description :** Écrit l’entier ’n’ sur le descripteur de fichier donné suivie d’un retour à la ligne. 
  
## Partie Bonus

Vous utiliserez la structure suivante pour représenter les maillons de votre liste. Sa déclaration est à ajouter à votre fichier libft.h :  
```
typedef struct s_list
{
void *content;
struct s_list *next;
} t_list;
```
Les membres de la structure t_list sont les suivants :  
• content : La donnée contenue dans le maillon. 
void * permet de stocker une donnée de n’importe quel type.  
• next : L’adresse du maillon suivant de la liste, ou NULL si le maillon suivant est le dernier.  
Dans votre Makefile, une règle make bonus vous permettra d’ajouter les fonctions demandées à votre libft.a.  

Implémentez les fonctions suivantes afin de manipuler vos listes aisément.  

**Function name :** ft_lstnew  
**Prototype char :** t_list *ft_lstnew(void *content);  
**Fichiers de rendu :** -  
**Paramètres :** content: Le contenu du nouvel élément.  
**Valeur de retour :** Le nouvel élément  
**Fonctions externes autorisées :** malloc.  
**Description :** Alloue (avec malloc(3)) et renvoie un nouvel élément. La variable membre ’content’ est initialisée à l’aide de la valeur du paramètre ’content’. La variable ’next’ est initialisée à NULL.  
____________________  
**Function name :** ft_lstadd_front  
**Prototype char :** void ft_lstadd_front(t_list **lst, t_list *new);  
**Fichiers de rendu :** -  
**Paramètres :** lst: L’adresse du pointeur vers le premier élément de la liste. new: L’adresse du pointeur vers l’élément à rajouter à la liste.  
**Valeur de retour :** Aucune.  
**Fonctions externes autorisées :** Aucune.  
**Description :** Ajoute l’élément ’new’ au début de la liste.  
____________________  
**Function name :** ft_lstsize  
**Prototype char :** int ft_lstsize(t_list *lst);  
**Fichiers de rendu :** -  
**Paramètres :** lst: Le début de la liste.  
**Valeur de retour :** Taille de la liste  
**Fonctions externes autorisées :** Aucune.  
**Description :** Compte le nombre d’éléments de la liste.  
____________________  
**Function name :** ft_lstlast  
**Prototype char :** t_list *ft_lstlast(t_list *lst);  
**Fichiers de rendu :** -  
**Paramètres :** lst: Le début de la liste.  
**Valeur de retour :** Dernier élément de la liste  
**Fonctions externes autorisées :** Aucune.  
**Description :** Renvoie le dernier élément de la liste.  
____________________  
**Function name :** ft_lstadd_back  
**Prototype char :** void ft_lstadd_back(t_list **lst, t_list *new);  
**Fichiers de rendu :** -  
**Paramètres :** lst: L’adresse du pointeur vers le premier élément de la liste. new: L’adresse du pointeur vers l’élément à rajouter à la liste.  
**Valeur de retour :** Aucune.  
**Fonctions externes autorisées :** Aucune.  
**Description :** Ajoute l’élément ’new’ à la fin de la liste.  
____________________  
**Function name :** ft_lstdelone  
**Prototype char :** void ft_lstdelone(t_list *lst, void (*del)(void*));  
**Fichiers de rendu :** -  
**Paramètres :** lst: L’élément à free. del: L’adresse de la fonction permettant de supprimer le contenu de l’élément.  
**Valeur de retour :** Aucune.  
**Fonctions externes autorisées :** free.  
**Description :** Libère la mémoire de l’élément passé en argument en utilisant la fonction ’del’ puis avec free(3). La mémoire de ’next’ ne doit pas être free.  
____________________  
**Function name :** ft_lstclear  
**Prototype char :** void ft_lstclear(t_list **lst, void (*del)(void*));  
**Fichiers de rendu :** -  
**Paramètres :** lst: L’adresse du pointeur vers un élément. del: L’adresse de la fonction permettant de supprimer le contenu de l’élément.  
**Valeur de retour :** Aucune.  
**Fonctions externes autorisées :** free.  
**Description :** Supprime et libère la mémoire de l’élément passé en paramètre, et de tous les éléments qui suivent, à l’aide de ’del’ et de free(3) Enfin, le pointeur initial doit être mis à NULL.  
____________________  
**Function name :** ft_lstiter  
**Prototype char :** void ft_lstiter(t_list *lst, void (*f)(void *));  
**Fichiers de rendu :** -  
**Paramètres :** lst: L’adresse du pointeur vers un élément. f: L’adresse de la fonction à appliquer.  
**Valeur de retour :** Aucune.  
**Fonctions externes autorisées :** Aucune.  
**Description :** Itère sur la liste ’lst’ et applique la fonction ’f’ au contenu chaque élément.  
____________________  
**Function name :** ft_lstmap  
**Prototype char :** t_list *ft_lstmap(t_list *lst, void *(*f)(void *), void (*del)(void *));  
**Fichiers de rendu :** -  
**Paramètres :** lst: L’adresse du pointeur vers un élément. f: L’adresse de la fonction à appliquer. del: L’adresse de la fonction permettant de supprimer le contenu d’un élément.  
**Valeur de retour :** La nouvelle liste. NULL si l’allocation échoue.  
**Fonctions externes autorisées :** malloc, free.  
**Description :** Itère sur la liste ’lst’ et applique la fonction ’f ’au contenu de chaque élément. Crée une nouvelle liste résultant des applications successives de ’f’. La fonction ’del’ est là pour détruire le contenu d’un élément si nécessaire.  


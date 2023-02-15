# 📖 libft
####  Our very first own library

------------

Questo progetto riguarda la comprensione, l'implementazione e l'approfondimento delle funzioni standard in C.

## 💡 About the project

> Dichiarare variabili globali sarà proibito e ogni file dovrà compilare con le flag  -Wall, -Wextra -Werror

> Il Makefile deve contenere almeno le regole $(NAME), all, clean, fclean e re.

> Dobbiamo usare il comando **ar** per creare la libreria. L'uso del comando libtool è proibito.

------------

## 🛠️ Funzioni

 ##### Qui sotto gli appunti per alcune delle funzioni:

* **bzero** scrive n byte di valore zero nella stringa s


* **split** divide una stringa in base ad un carattere e ritorna un array di stringhe


* **strnstr** ritorna un puntatore alla prima occorrenza della stringa needle nella stringa haystack


* **strlcat** concatena la stringa src alla stringa dst di dimensione size in modo che la stringa dst abbia una dimensione totale di size - 1 e che la stringa dst sia terminata da un null byte ('\0')


* **strlcpy** copia la stringa src nella stringa dst di dimensione size in modo che la stringa dst abbia una dimensione totale di size - 1 e che la stringa dst sia terminata da un null byte ('\0')


* **substr** alloca (con malloc(3)) e ritorna una stringa che è il risultato della copia della stringa s a partire dall'indice start per un massimo di len caratteri.


* **strtrim** rimuove i caratteri specificati dalla stringa iniziale e finale


* **memset** scrive len byte del valore c (convertito in unsigned char) nella stringa b


* **memcpy** copia un numero n di bytes dalla memoria src alla memoria dst. in caso queste due coincidessero la funzione usa memmove. questa funzione ritorna il valore originari di dst


* **memmove** copia len bytes da src a dst. le due stringe devono sovrapporsi in maniera non distruttiva lmao


* **memcmp** prende due stringhe di n caratteri e ritorna 0 se sono identiche altrimenti la differenza unsigned tra i primi due byte che differiscono le stringhe di 0 byte sono sempre identiche


    iniziamo creando due puntatori a char nei quali casteremo le nostre stringhe e un contatore size_t
    che useremo per comparare entrambi i paramentri s1 e s2 castati a loro volta dentro i nuovi puntatori a char
    vogliamo che il nostro loop continui fintanto che i < n ma non appena il carattere in str1 differisce da str2 vogliamo che
    che la funzione ritorni la differenza in byte tra i due unsigned char.
    una volta raggiunta la nostra n ritorniamo 0 */

* **strjoin** assegna memoria sufficiente e ritorna una nuova stringa terminata da "\0" data dal risultato del concatenamento dei parametri s1 e s2.


    iniziamo dichiarando due contatori per muoverci attraverso le stringhe
    una terza variabile a cui assegneremo la nostra memoria per poter tornare
    le nostre stringhe concatenate
	
    impostiamo entrambi i counter a 0 e utiliziamo malloc
    con una combinazione della nostra funzione strlen, per entrambi i parametri s1 e s2,	
    in modo da avere la lunghezza totale di *str + 1 per collocare anche il carattere "\0"
    ritorna NULL in caso malloc fallisse
	
    iniziamo la nostra catena di stringhe partendo da un loop
    fino alla fine di s1, impostando lo stesso index sia per il nuovo parametro str
    che per il nostro s1, fatto questo procediamo al prossimo loop
    questo loop è esattamente come il precedente se non fosse che prende
    in considerazione anche la nostra variabile j, che ancora equivale a 0.
    per la nostra neonata str su i + j in questo modo manterremo il loop
    la nostra posizione i dal loop precedente e conteremo s2 sulla nostra j
    una volta raggiunta la fine di s2 aggiungiamo il "\0" e torniamo la nostra freschissima str   

* **atoi** converte una stringa di caratteri char ad int cercando al suo interno ogni cifra da 0 a 9 trascrivendo il suo valore in ascii e moltiplicandolo per 10
   
	
    la prima variabile conterrà il nostro risultato, usiamo long per
	garantire abbastanza spazio: da -2147483647 a 2147483647
	la seconda variabile verrà utilizzata nel caso in cui il numero in str sia negativo,
	anch'esso long per poterlo moltiplicare per il nostro risultato
	e infine un unsigned int come contatore
	
	impostiamo sign come 1 assumendo di trovare un valore positivo
	se falso cambieremo il nostro sign a -1
	
	per prima cosa la nostra funzione ignora ogni tipo di spazio
	che potrebbe trovarsi all'inizio della stringa
	
	il nostro loop convertirà ogni char tra 0 e 9 al valore ascii corrispondente.
	iniziamo considerando ogni cifra stampabile e moltiplichiamo * 10 il nostro res
	per assicurarci che la nostra cifra venga scritta in maniera sequenziale.
	sottraendo il valore ascii di 0 alla nostra coordinata str[i] otteniamo
	il valore asci del carattere corrente.
	Il loop finisce una volta incontrato un carattere non compreso tra 0 e 9

* **itoa** assegna memoria e ritorna una freschissima stringa di caratteri equivalente ad un int passato come parametro, lo stesso vale per i numeri negativi

	
	impostiamo la nostra str al valore di strjoin con parametro
	e chiudiamo la ricorsiva con un -n in modo da rendere positivi (^_^) gli int
	infine ci stiamo chiedendo se il nostro int è maggiore di 10 in questo caso
	andremo a scomporlo in maniera ricorsiva per ricostruirlo come una stringa
	
	tutto questo è possibile impostando la nostra ormai memorizzata str
	sulla nostra ft_strjoin precedente e passandola come parametro per itoa con
	n / 10 e itoa con n % 10 questo utilizzo di ft_strjoin non avverrà	
	
	fintanto che stiamo chiamando itoa ancora e ancora, questo dividerà i nostri int per 10,
	salverà il risultato e inizierà la funzione di nuovo fino a raggiungere
	il primissimo o qualsivoglia ultimo numero del nostro int  ¯\_(ツ)_/¯

------------

## ✅ Bonus part

> Le funzioni per manipolare la memoria e le stringhe sono molto utili. 
Ma presto scoprirai che manipolare le liste è ancora più utile.

Ogni lista collega vari punti di memoria tramite un **puntatore**, ogni elemento della lista è chiamato **nodo**.

* **lstadd_front** aggiunge l'elemento new all'inizio della lista.


* **lstsize** conta il numero di elementi in una lista.


* **lstlast** restituisce l'ultimo elemento della lista.


* **lstdelone** prende come parametro l'indirizzo di un elemento e libera la memoria del contenuto dell'elemento con la funzione del e della memoria dell'elemento stesso con free(3)


* **lstclear** prende come parametro l'indirizzo di un elemento e libera la memoria del contenuto di ogni elemento con la funzione del e della memoria di ogni elemento con free(3)


* **lstiter** itera la lista lst e applica la funzione f al contenuto di ogni elemento.


* **lstnew** alloca (con malloc(3)) e ritorna un nuovo elemento. Il campo content viene inizializzato con il valore del parametro content. Il campo next viene inizializzato a NULL.

> Per rappresentare un nodo della lista useremo la seguente struttura:
 
        typedef struct s_list
        {
            void			*content;
            struct s_list	*next;
        }	t_list;

> aggiungiendo la sua dichiarazione al nostro file **libft.h**

------------

## 📋 Testing

L'intera libreria è stata realizzata con l'aiuto dei commenti del collega **[pbie](https://github.com/pbie42/libft42commented)**
e testata utilizzando il [**supreme-tester di ffrau**](https://github.com/FranFrau/Supreme-Tester-Libft)

🚨 **Stay vigilant**, è importante testare le funzioni singolarmente per garantirne il funzionamento!

## 🪅 Riconoscimenti

> Ci prenderemo del tempo per espandere libft durante tutto l'anno.
Tuttavia, lavorando su un nuovo progetto, dovremmo assicurarci
che le funzioni utilizzate siano consentite nelle linee guida.


Ci tengo a ringraziare i compagni che piú mi sono stati appresso durante questo progetto:

* https://github.com/stenterello
* https://github.com/mcapalbo
* https://github.com/lmorelli333
* https://github.com/equadrin
* https://github.com/TizianoPiras
* https://github.com/misidori



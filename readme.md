# 📖 libft
####  Our very first own library
Questo progetto cercheremo di comprendere, implementare e approfondire le funzioni standard in **C**.

------------

## 💡 About the project

**libft** è una collezione di funzioni che ci permetteranno di lavorare con le **stringhe**, le **liste**, le **matrici** e altre **strutture dati**.

> Dichiarare variabili globali sarà **proibito** e ogni file dovrà compilare con le flag  -Wall, -Wextra -Werror

> Il **Makefile** deve contenere almeno le regole $(NAME), all, clean, fclean e re.

> Dobbiamo usare il comando **ar** per creare la libreria. L'uso del comando libtool è proibito.

------------

## 🛠️ Funzioni

 ##### Qui sotto gli appunti per alcune delle funzioni:

|    Nome     | Funzione                                                                                                                                                                             |
|:-----------:|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  **bzero**  | scrive n byte con valore 0 sulla stringa s                                                                                                                                           |
|  **split**  | divide una stringa in base al parametro c e ritorna una matrice                                                                                                                      |
| **strnstr** | ritorna un puntatore la prima volta che s1 viene individuata in s2                                                                                                                   |
| **strlcat** | concatena src su dst per size byte                                                                                                                                                   |
| **strlcpy** | scrive src all'interno della stringa dst per n size di byte                                                                                                                          |
| **substr**  | individua e alloca memoria per una copia di s1 per un massimo di len caratteri                                                                                                       |
| **strtrim** | rimuove gli apici di una stringa finche corrispondono ai caratteri passati nei parametri                                                                                             |
| **memset**  | scrive len byte di calore c (convertito unsigned char) sulla stringa b                                                                                                               |
| **memmove** | copia len bytes da src a dst. le due stringe devono sovrapporsi in maniera non distruttiva lmao                                                                                      |
| **memcpy**  | copia un numero n di byters dalla memoria src alla memoria dst, questa funzione riporta il valore originario di dst                                                                  |
| **memcmp**  | prende due stringhe di n caratteri e ritorna 0 se sono identiche altrimenti la differenza unsigned tra i primi due byte che differiscono le stringhe di 0 byte sono sempre identiche |
| **strjoin** | assegna memoria sufficiente e ritorna una nuova stringa terminata da "\0" data dal risultato del concatenamento dei parametri s1 e s2.                                               |
|  **atoi**   | converte una stringa di caratteri char ad int cercando al suo interno ogni cifra da 0 a 9 trascrivendo il suo valore in ascii e moltiplicandolo per 10                               |
|  **itoa**   | assegna memoria e ritorna una freschissima stringa di caratteri equivalente ad un int passato come parametro, lo stesso vale per i numeri negativi                                   |

------------

## ✅ Bonus part

> Le funzioni per manipolare la memoria e le stringhe sono molto utili. 
Ma presto scopriremo che manipolare le liste è ancora più utile.

Ogni lista collega vari punti di memoria tramite un **puntatore**, ogni elemento della lista è chiamato **nodo**.

|     Lista     | Funzione                                                                 |
|:-------------:|--------------------------------------------------------------------------|
|  **lstadd**   | aggiungono un elemento new all'inizio o alla fine della lista            |
|  **lstsize**  | conta il numero di elementi in una lista.                                |
|  **lstlast**  | restituisce l'ultimo elemento della lista.                               |
| **lstdelone** | prende come parametro l'indirizzo di un elemento e ne libera la memoria  |
| **lstclear**  | libera la memoria di ogni nodo                                           |
|  **lstiter**  | scorre attraverso lst e applica la funzione f al contenuto di ogni nodo. |
|  **lstnew**   | alloca memoria e ritorna un nuovo nodo.                                  |

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

Ci tengo a ringraziare i compagni che piú mi sono stati appresso durante questo progetto:

 <details>

  <summary> Check them out! </summary>

* https://github.com/stenterello
* https://github.com/mcapalbo
* https://github.com/lmorelli333
* https://github.com/equadrin
* https://github.com/TizianoPiras
* https://github.com/misidori

</details>
Up
> Ci prenderemo del tempo per espandere libft durante tutto l'anno.
Tuttavia, lavorando su un nuovo progetto, dovremmo assicurarci
che le funzioni utilizzate siano consentite nelle linee guida.

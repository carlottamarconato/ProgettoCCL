# ProgettoCCL
**Sudoku risolto con un SAT solver (Z3)**

Il progetto consiste in un gioco di Sudoku in cui tutta la logica, risoluzione e generazione dei puzzle, è delegata a un SAT solver, Z3, invece di essere implementata con un algoritmo tradizionale di backtracking.

L'idea di base è che il Sudoku è un problema di soddisfacibilità booleana: le sue regole (una cifra per cella, cifre uniche per riga, colonna e blocco 3×3) vengono tradotte in un insieme di variabili e vincoli logici. Per ogni cella e ogni possibile cifra viene creata una variabile booleana, e vincoli del tipo "esattamente una di queste è vera" codificano tutte le regole del gioco, in totale 729 variabili e circa 12 mila clausole. Risolvere il Sudoku diventa così equivalente a chiedere al solver se questa formula è soddisfacibile.

Oltre alla risoluzione, il progetto genera puzzle nuovi partendo da una griglia completa casuale e rimuovendo numeri uno alla volta, verificando ad ogni passo che il puzzle mantenga sempre una soluzione unica.

Il tutto è racchiuso in un'interfaccia grafica realizzata con Tkinter, che permette di giocare, chiedere suggerimenti al solver, verificare le proprie mosse o far risolvere l'intero puzzle da Z3, mostrando anche in tempo reale il numero di variabili, di clausole e il tempo impiegato dal solver ad ogni chiamata.

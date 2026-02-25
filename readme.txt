Istruzioni.

Sotto lo stesso livello della cartella monitora che dalla ditta sarebbe la cartella
nella quale vengono generati i CSV dalla macchina XRay,
va creata la cartella  risultati e al di sotto la cartella da_importare e al suo interno
va messo un file Xray.csv  anche vuoto. 

Tutto questa preparazione è necessaria perchè l'I/E può partire automaticamente
tramite bat e bub solo se lui sa già il percorso dal quale prendere il file e il nome del file.
Quindi così facendo quantomeno lui parte e poi chiama l'inizialize che si occupa
poi di creare il vero file aggregato XRay.csv che finirà in prima battuta nella cartella da_importare
e poi nella terminate viene spostato negli importati.

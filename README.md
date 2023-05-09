# LINQDb
-Per incominciare dobbiamo creare una cartella con il nome es(.cancellieri.andrea.4h.Linqdb) e successivamente aprirla con Visual studio.\
-Eseguire nel terminare 'DOTNET NEW CONSOLE'.\
-Ricercare su internet '[chinook.db](https://www.sqlitetutorial.net/sqlite-sample-database/)', scaricare il file e poi inserirlo nella cartella che abbiamo creato in precedenza.\
Chinook.db è un database possa essere utilizzato come fonte di dati per un'ampia varietà di applicazioni. Il database contiene diverse tabelle che sono correlate tra loro attraverso chiavi esterne, consentendo di accedere ai dati in modo efficiente e preciso.\


-Successivamnet iniziamo a compilare il codice.\
-Ricordarsi di di aggiungere 'Using SQLite'.\
-Aggiungere tramite il terminale la libreria.\

PS C:\Users\PC05\Desktop\Cancellieri.andrea.4h.Linqdb> dotnet  add package sqlite-net-pc1\

-Il comando che ci permette di accedere alla libreria è :
###
    SQLiteConnection cn1 = new SQLiteConnection("chinook.db");
###

-Possiamo selezionare dal DB tramite :
###
    var tblArtist = cn1.Query<Artist>("select * from artists");
###

-Il comando che ci permette di ordinare gli ID degli artisti è:
###
    var temporanea = tblArtist.OderByDescending(x => x.Name).Max( y => y.ArtistId ) ;
###    

- In seguito proseguimo con l' utilizzo di un foreach il quale scorre  e scrive i record ed anche il numero dei record presenti:
###
    foreach( var record in tblArtist)
    {
      Console.WriteLine($"{record.Name}");
    }
    Console.WriteLine($"{temporanea}");
###
    
-Ecco il risultato ottenuto:

![image](https://github.com/Keinssz/LINQDb/assets/116791211/97e1196e-659a-4640-8ecb-7f052abc90e1)

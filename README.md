# Documentazione!!!

Benvenuto nella nostra pagina di documentazione informatica. Troverai guide dettagliate, tutorial e risorse utili per navigare nel mondo dell'informatica.

## Indice

- [**Come strutturare un sito web statico**](#come-strutturare-un-sito-statico)
- [**Come strutturare un sito web dinamico**](#come-strutturare-un-sito-dinamico)
- [**Variabili d'ambiente**](#variabili-dambiente)
    * [**Online**](#online)
- [**Come collegarsi al proprio database**](#come-collegarsi-al-proprio-database)

## Come strutturare un sito web statico

Un sito web statico è un tipo di sito web che è costituito principalmente da pagine web con contenuti fissi e immagini. Le pagine di un sito web statico rimangono invariate finché non vengono modificate __manualmente__ dallo sviluppatore. Ciò significa che il contenuto del sito non cambia <u>*dinamicamente*</u> in risposta alle azioni dell'utente o ad altri eventi. Un sito statico non prevede l’elaborazione lato server e non ha un database. Qualsiasi funzionalità <u>*dinamica*</u> associata al sito statico viene eseguita lato client, il che significa che il codice viene eseguito nel browser dei visitatori anziché sul server.

```treeview
Progetto/
|-- audio/
|   |-- file.mp3
|   `-- ...mp3
|-- css/
|   |-- file.css
|   `-- ...css
|-- immagini/
|   |-- file.png
|   `-- ...png
|-- javascript/
|   |-- file.js
|   `-- ...js
|-- video/
|   |-- file.mp4
|   `-- ...mp4
`-- index.html
```

---

Esempio di `index.html`:
```html
<!DOCTYPE html>
<html lang="it">

    <head>
        <meta charset="utf-8">
        <title>Dispositivi di I/O</title>
    </head>

    <body>
        <h1>Dispositivi di I/O</h1>
        <img src="immagini/file.png">
        <ul>
            <li>Monitor</li>
            <li>Mouse</li>
            <li>Stampante</li>
            <li>Tastiera</li>
            <li>Webcam</li>
        </ul>
    </body>

</html>
```

## Come strutturare un sito web dinamico

Un sito web dinamico è un tipo di sito web che utilizza un linguaggio di programmazione lato server fornendo così contenuti personalizzati e interattivi agli utenti. A differenza dei siti web statici, che mostrano informazioni fisse agli utenti, i siti web dinamici sono in grado di interagire con una base di dati e di generare contenuti in tempo reale in base alle richieste degli utenti o a determinati parametri.

```treeview
Progetto/
|-- audio/
|   |-- file.mp3
|   `-- ...mp3
|-- css/
|   |-- file.css
|   `-- ...css
|-- immagini/
|   |-- file.png
|   `-- ...png
|-- javascript/
|   |-- file.js
|   `-- ...js
|-- video/
|   |-- file.mp4
|   `-- ...mp4
`-- index.php
```

---

Esempio di `index.php`:
```php
<?php $dispositivi = ["Monitor", "Mouse", "Stampante", "Tastiera", "Webcam"]; ?>

<!DOCTYPE html>
<html lang="it">

    <head>
        <meta charset="utf-8">
        <title>Dispositivi di I/O</title>
    </head>

    <body>
        <h1>Dispositivi di I/O</h1>
        <img src="immagini/file.png">
        <ul>
            <?php foreach ($dispositivi as $dispositivo) { ?>
                <li><?php echo $dispositivo; ?></li>
            <?php } ?>
        </ul>
    </body>

</html>
```

## Variabili d'ambiente

In ambito informatico, una <u>***variable d'ambiente***</u> è una specifica informazione o valore che può influenzare il comportamento di un programma o del sistema operativo. Le variabili d'ambiente sono spesso utilizzate per fornire informazioni o parametri che un programma può leggere durante l'esecuzione, consentendo una maggiore flessibilità nell'adattare il comportamento del software all'ambiente in cui viene eseguito.

#### Online

La variabile d'ambiente <u>***ONLINE***</u> permette al programma di determinare se sta operando in un ambiente locale o sul server. Questa variabile fornisce informazioni cruciali al programma per adattare il suo comportamento in base alle specifiche esigenze e alle risorse disponibili nell'ambiente in cui si trova.

Per utilizzare questa variabile d'ambiente, ti basterà inserire la seguente riga di codice all'inizio del tuo programma:

```php
<?php define("ONLINE", boolval(getenv("ONLINE"))); ?>
```

Verrà quindi definita la costante booleana <u>***ONLINE***</u> che potrai usare nelle tue condizioni: 

```php
<?php define("ONLINE", boolval(getenv("ONLINE"))); ?>

<!DOCTYPE html>
<html lang="it">

    <head>
        <meta charset="utf-8">
        <title>Ambiente</title>
    </head>
    
    <body>
        <h1>Ambiente: <?php echo ONLINE ? "Server" : "Locale"; ?></h1>
    </body>
    
</html>
```

## Come collegarsi al proprio database

```php
<?php

$username = "username";
$password = "password";
$database = "test";

// Crea la connessione
$connection = mysqli_connect("database.lab.school", $username, $password, "lab_{$username}_{$database}");

// Controlla la connessione
if (!$connection) {
    // Errore di connessione
    die("Connessione fallita: " . mysqli_connect_error());
}

// Connesso!

?>
```

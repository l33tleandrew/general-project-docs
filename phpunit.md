# Configuring PHPStorm, PHPUnit and PHPUnit Bridge in a Symfony project

Quando viene eseguita la funzione di Debug dell'IDE, PHPStorm utilizza le impostazioni del progetto, definite nella sezione ***Test Frameworks***, ed applica tali impostazioni all'applicazione o al singolo script che si vuole eseguire, creando così una configurazione di Run/Debug apposita per lo script in questione. 

Seppur le impostazioni del framework di test si applicano all'intero progetto, è comunque possibile modificare e personalizzare la configurazione di esecuzione e di debug di ogni singolo script accedendo alla sezione ***Run/Debug configurations*** facilmente accessibile dal menù a tendina situato nella barra in alto della barra degli strumenti.

In questo modo è possibile creare profili di configurazioni diversi per ogni tipo di script ed esigenza.


phpunit-bridge è un componente symfony che possiede funzionalità aggiuntive e modificate di PHPUnit.

Se questo componente viene utilizzato all'interno di una applicazione symfony assicurarsi di includere 
il file config/bootstrap.php all'interno del file di configurazione phpunit.xml

```
<phpunit xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:noNamespaceSchemaLocation="http://schema.phpunit.de/6.5/phpunit.xsd"
         backupGlobals="false"
         colors="true"
         bootstrap="config/bootstrap.php"
         verbose="true"
>
```

Se invece viene utilizzato al di fuori di una applicazione Symfony, assicurarsi di includere il file
vendor/autoload.php all'interno del file di configurazione phpunit.xml

```
<phpunit xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:noNamespaceSchemaLocation="http://schema.phpunit.de/6.5/phpunit.xsd"
         backupGlobals="false"
         colors="true"
         bootstrap="vendor/autoload.php"
         verbose="true"
>
```

Eseguire il comando /bin/phpunit NEL TERMINALE di PHPStorm posizionandosi nella root folder del progetto
in modo da eseguire la suite di test utilizzando il componente phpunit-bridge. Questo comando installerà
una versione specifica di phpunit all'interno della cartella /bin/phpunit/.phpunit

Configurare PHPStorm, nella sezione Test Framework usando un path al file phpunit.phar, 
in modo da puntare alla versione specifica del file phpunit all'interno della cartella appena creata. 
Es. /bin/.phpunit/phpunit-7.5/phpunit

Assicurarsi di eliminare pre esistenti configurazione di debug per specifiche classi e funzioni.

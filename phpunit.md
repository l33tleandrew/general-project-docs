Le funzionalità di Run e Debug all'interno di PHPStorm vengono eseguite prendendo in considerazione le impostazioni 
di PHPStorm ed applicando tali impostazioni alla particolare classe o funzione. Da questo processo ne deriva
una configurazione di Run/Debug per tale classe o funzione che si può trovare nella dropdown delle configurazioni di PHPStorm.


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

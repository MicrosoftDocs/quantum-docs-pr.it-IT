# <a name="articles"></a>Articoli

In questa directory è possibile trovare gli articoli per la documentazione di Quantum Development Kit. Questa directory contiene:

- **Directory degli articoli**: contengono gli articoli per ogni sezione della documentazione. In queste directory è possibile trovare il contenuto seguente:
  
  - Ogni directory contiene un `toc.yml` file per visualizzare il contenuto della directory nel sommario principale (sommario).
  - Articoli Markdown che contengono la documentazione. Questi articoli devono seguire le linee guida della [Guida per i collaboratori Microsoft docs](https://docs.microsoft.com/en-us/contribute/).
  - Sottodirectory degli articoli. Queste sottodirectory devono contenere anche il proprio `toc.yml` file.

> :p encil: anche se è possibile fare riferimento ai `*.md` file direttamente nel file padre `TOC.yml` , per evitare che le cose siano ordinate, è possibile farvi riferimento solo dalla `toc.yml` della directory corrente.

- ** `TOC.yml` File del sommario principale (sommario)**: in questo file le sezioni del sommario del sito Web sono elencate insieme al riferimento al `toc.yml` file principale della directory di ogni sezione.
- **`index.yml`** YAML con la configurazione della pagina di destinazione della documentazione.
- **`\media`**: Una directory in cui archiviare tutte le immagini utilizzate nella documentazione. Contiene una `\media\src` sottodirectory per archiviare i file di origine delle immagini.
- **File di licenza**: file contenenti licenze legali
- **File tecnici**: file contenenti macro e metadati.

## <a name="guidelines"></a>Linee guida

Alcune linee guida generali sull'organizzazione di questa directory per i collaboratori:

- Ogni directory o sottodirectory deve contenere il proprio `toc.yml` file in cui vengono indicati gli articoli dello stesso livello o i `toc.yml` file delle relative directory figlio.
- L'organizzazione delle directory del repository deve essere il più vicino possibile all'organizzazione del sommario del sito Web della documentazione.
- Tutte le immagini devono essere archiviate in `articles\media` e non nella cartella articles.
- I titoli degli articoli, i nomi nel sommario e l' *UID* dei metadati devono essere il più vicino possibile tra loro e rappresentare chiaramente l'intestazione H1 del documento Markdown.

## <a name="adding-images"></a>Aggiunta di immagini

Per fare in modo che le immagini vengano renderizzate correttamente in modalità scura, è necessario evitare lucidi.
- Per i `*.jpg` file non è necessario eseguire alcuna operazione poiché il formato del file non supporta elementi trasparenti.
- Per `*.png` i file è necessario aggiungere uno sfondo bianco o modificare il valore del canale alfa in 100. Il modo più semplice per eseguire questa operazione in Windows consiste nell'aprire il file in Paint e salvare, sovrascrivendo il file originale.
- Per `*.svg` i file è necessario aggiungere un rettangolo bianco nel livello più basso. Questa operazione può essere eseguita con Inkscape:
  - Aprire il file `*.svg` .
  - Selezionare lo strumento creatore quadrato e tracciare un rettangolo bianco nella parte superiore della figura originale.
  - Selezionare lo strumento "Seleziona e trasforma oggetti" facendo clic sulla freccia scura o premendo F1.
  - Quando il rettangolo è selezionato, fare clic sull'elemento barra degli strumenti "bassa selezione in basso (fine)".
  - Modificare il rettangolo con il mouse o i tasti di direzione.

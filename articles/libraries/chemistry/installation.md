---
title: 'Installazione e convalida della libreria di chimica Q # Microsoft'
description: Informazioni su come installare la libreria Microsoft Quantum Chemistry e usarla con la piattaforma di chimica computazionale NWChem.
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.installation
ms.openlocfilehash: 48bf7bc980e238e622053f5c2bdd09604c572596
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907359"
---
# <a name="chemistry-library-installation-and-validation"></a>Installazione e convalida della libreria di chimica

Quantum Development Kit fornisce il supporto per le applicazioni di chimica quantistica tramite il pacchetto NuGet [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) .
Come per gli altri pacchetti NuGet, è facile aggiungere la libreria di chimica al progetto.

**Visual Studio 2019:** Se si usa Visual Studio 2019, è possibile aggiungere i pacchetti di chimica quantistica usando Gestione pacchetti NuGet.
Per aprire Gestione pacchetti, fare clic con il pulsante destro del mouse sul progetto a cui si vuole aggiungere la libreria di chimica e selezionare "Gestisci pacchetti NuGet", come nella schermata seguente.

![Uso di gestione pacchetti NuGet in Visual Studio 2019](~/media/vs2017-nuget-manage-packages.png)

Dalla scheda Sfoglia cercare il nome del pacchetto "Microsoft. Quantum. Chemistry".

> [!NOTE]
> Assicurarsi di eseguire il segno di "Includi versione preliminare".

![Casella di controllo Includi versione preliminare](~/media/vs2017-nuget-package-search.png)

In questo elenco vengono elencati i pacchetti disponibili per il download.
Fare clic su "Microsoft. Quantum. Chemistry nel riquadro a sinistra, selezionare la versione provvisoria più recente nel riquadro di destra e fare clic su" Installa ":

![Installare il pacchetto Microsoft. Quantum. Chemistry più recente](~/media/vs2017-nuget-select-chem.png)

Per ulteriori informazioni, vedere la [Guida dell'interfaccia utente di gestione pacchetti](https://docs.microsoft.com/nuget/tools/package-manager-ui).

In alternativa, è possibile usare la console di gestione pacchetti per aggiungere la libreria Quantum Chemistry al progetto con un'interfaccia della riga di comando.

![Usare la console di gestione pacchetti dalla riga di comando](~/media/vs2017-nuget-console-menu.png)

Dalla console di gestione pacchetti eseguire le operazioni seguenti:

```
Install-Package Microsoft.Quantum.Chemistry
```

Per ulteriori informazioni, vedere la [Guida della console di gestione pacchetti](https://docs.microsoft.com/nuget/tools/package-manager-console).

**Riga di comando o Visual Studio Code:** Usando la riga di comando autonomamente o dall'interno di Visual Studio Code, è possibile usare il comando `dotnet` per aggiungere il riferimento al pacchetto NuGet al progetto:

```dotnetcli
dotnet add package Microsoft.Quantum.Chemistry
```

## <a name="verifying-your-installation"></a>Verifica dell'installazione 

Come il resto del kit di sviluppo Quantum, la libreria Quantum Chemistry comprende una serie di esempi completamente documentati che consentono di iniziare subito a funzionare.
Per testare l'installazione usando questi esempi, clonare il [repository main Samples](https://github.com/Microsoft/Quantum), quindi eseguire uno degli esempi.  Per eseguire ad esempio il [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen) esempio:

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/chemistry/MolecularHydrogen
dotnet run
```

Per verificare l'installazione della libreria Quantum Chemistry usando Microsoft Visual Studio dopo la clonazione del repository:
    1. Aprire la soluzione ChemistrySamples. sln nella cartella chimica.  
    2. Selezionare Samples/1. Semplici molecole/MolecularHydrogen come progetto di avvio.
    3. Premere F5 per eseguire la demo relativa alla valutazione della fase Quantum a idrogeno molecolare.

Per altre informazioni su come stimare i valori dei livelli di energia, vedere [ottenere stime del livello di energia](xref:microsoft.quantum.chemistry.examples.energyestimate) .   


## <a name="using-the-quantum-development-kit-with-nwchem"></a>Uso di Quantum Development Kit con NWChem ##

Nell'esempio MolecularHydrogen vengono utilizzati dati di input molecolari configurati manualmente.  Sebbene si tratti di un problema per piccoli esempi, la chimica quantistica su larga scala richiede hamiltonians con milioni o miliardi di termini. Tali hamiltonians, generati da pacchetti di chimica computazionale scalabile, sono troppo grandi per essere importati manualmente. 

La libreria Quantum Chemistry per Quantum Development Kit è stata progettata per funzionare correttamente con i pacchetti di chimica computazionale, in particolare la piattaforma di chimica computazionale [**nwchem**](http://www.nwchem-sw.org/) sviluppata da Environmental Molecular Science Laboratory (EMSL) di Pacific Northwest National Laboratory.
In particolare, il pacchetto di `Microsoft.Quantum.Chemistry` fornisce strumenti per il caricamento di istanze di problemi di simulazione della chimica quantistica rappresentati nello [schema Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), supportati anche per l'esportazione da versioni recenti di nwchem.

Per iniziare a usare NWChem insieme a Quantum Development Kit, è consigliabile usare uno dei metodi seguenti:
- Iniziare a usare i file Broombridge esistenti forniti con gli esempi in [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML).
- Usare il [Generatore di frecce EMSL per la Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) , che è un front-end basato sul Web con nwchem, per generare nuovi file di input molecolari in formato Broombridge.  
- Usare l' [immagine Docker](https://hub.docker.com/r/nwchemorg/nwchem-qc/) fornita da PNNL per eseguire nwchem
- [Compilare nwchem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) per la piattaforma.

Vedere [end-to-end con nwchem](xref:microsoft.quantum.chemistry.examples.endtoend) per altre informazioni su come usare nwchem per i modelli chimici per l'analisi con la libreria di chimica Quantum Developers Kit.

### <a name="getting-started-using-broombridge-files-provided-with-the-samples"></a>Introduzione all'uso dei file Broombridge forniti con gli esempi

La cartella [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) nel repository di esempi di Quantum Development Kit contiene file di dati di molecole in formato Broombridge.  

Come esempio semplice, usare l'esempio di libreria di chimica, [GetGateCount](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/GetGateCount) per caricare l'Hamiltoniana da uno dei file Broombridge ed eseguire stime di controllo della simulazione quantistica algorigthms:

```bash
cd Quantum/Chemistry/GetGateCount
dotnet run -- --path=../IntegralData/YAML/h2.yaml --format=YAML
```

Per altre informazioni su come inserire le molecole rappresentate dallo schema Broombridge, vedere [caricamento di un'Hamiltoniana da un file](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) .  

Per altre informazioni sulla stima delle risorse, vedere [ottenere i conteggi delle risorse](xref:microsoft.quantum.chemistry.examples.resourcecounts) .  

### <a name="getting-started-using-the-emsl-arrows-builder"></a>Introduzione all'uso del generatore di frecce EMSL

EMSL Arrows è uno strumento che usa NWChem e database di calcolo chimici per generare dati molecolari.  [Il generatore di frecce EMSL per il Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) consente di immettere il modello usando più generatori di modelli molecolari e di generare il file di file di Broombridge che verrà usato dal quantum Development Kit.  

Dalla pagina EMSL, fare clic sulla scheda [' instuctions '] e seguire le istruzioni [' simple examples '] per generare file Broombridge.  Provare quindi a eseguire [' GetGateCount '] per visualizzare le stime delle risorse Quantum per queste molecole.

### <a name="installing-nwchem-from-source"></a>Installazione di NWChem dall'origine

Le istruzioni complete su come installare NWChem dall'origine [sono fornite da PNNL](http://www.nwchem-sw.org/index.php/Compiling_NWChem).

> [!TIP]
> Se si vuole usare NWChem da Windows 10, il sottosistema Windows per Linux è un'ottima opzione.
> Dopo aver installato [Ubuntu 18,04 LTS per Windows](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab), eseguire `ubuntu18.04` dal terminale preferito e seguire le istruzioni riportate sopra per installare nwchem dall'origine.

Dopo aver compilato NWChem dall'origine, è possibile eseguire lo script `yaml_driver` fornito con NWChem per produrre rapidamente istanze di Broombridge dai Deck di input di NWChem:

```bash
$NWCHEM_TOP/contrib/quasar/yaml_driver input.nw
```

Questo comando creerà un nuovo file di `input.yaml` nel formato Broombridge all'interno della directory corrente.

### <a name="using-nwchem-with-docker"></a>Uso di NWChem con Docker

Le immagini predefinite per l'uso di NWChem sono disponibili tra piattaforme diverse tramite l' [Hub Docker](https://hub.docker.com).
Per iniziare, seguire le istruzioni di installazione di Docker per la piattaforma:

- [Installare Docker per Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
- [Installare Docker per macOS](https://docs.docker.com/docker-for-mac/install/)
- [Installare Docker per Windows 10](https://docs.docker.com/docker-for-windows/install/)

> [!TIP]
> Se si usa Docker per Windows, sarà necessario condividere l'unità che contiene la directory temporanea (in genere si tratta dell'unità `C:\`) con il daemon docker. Per altri dettagli, vedere la [documentazione di Docker](https://docs.docker.com/docker-for-windows/#shared-drives) .

Una volta installato Docker, è possibile usare il modulo di PowerShell fornito con gli esempi di Quantum Development Kit per eseguire l'immagine oppure è possibile eseguire l'immagine manualmente.
Qui viene illustrato in dettaglio l'uso di PowerShell. Se si vuole usare manualmente l'immagine Docker, vedere la [documentazione fornita con l'immagine](https://hub.docker.com/r/nwchemorg/nwchem-qc/).

#### <a name="running-nwchem-through-powershell-core"></a>Esecuzione di NWChem tramite PowerShell Core

Per usare l'immagine Docker NWChem con Quantum Development Kit, viene fornito un modulo di PowerShell di piccole dimensioni che gestisce automaticamente i file in e da NWChem.
Se PowerShell Core non è ancora installato, è possibile scaricarlo multipiattaforma dal [repository di PowerShell su GitHub](https://github.com/PowerShell/PowerShell#get-powershell).

> [!NOTE]
> PowerShell core viene usato anche per alcuni esempi per illustrare l'interoperabilità con data science e flussi di lavoro di analisi business.

Dopo aver installato PowerShell core, importare `InvokeNWChem.psm1` per rendere disponibili i comandi NWChem nella sessione corrente:

```powershell
cd Quantum/utilities/
Import-Module ./InvokeNWChem.psm1
```

In questo modo il comando `Convert-NWChemToBroombridge` verrà reso disponibile nella sessione corrente di PowerShell.
Per scaricare le immagini necessarie da Docker e usarle per eseguire i deck di input NWChem e acquisire l'output in Broombridge, eseguire le operazioni seguenti:

```powershell
Convert-NWChemToBroombridge ./input.nw
```

Verrà creato un file Broombridge eseguendo NWChem in `input.nw`.
Per impostazione predefinita, l'output di Broombridge avrà lo stesso nome e percorso del deck di input, con l'estensione `.nw` sostituita da `.yaml`.
Questa operazione può essere sottoposta a override utilizzando il parametro `-DestinationPath` per `Convert-NWChemToBroombridge`.
Per ottenere altre informazioni, è possibile usare la funzionalità integrata della Guida di PowerShell:

```powershell
Convert-NWChemToBroombridge -?
Get-Help Convert-NWChemToBroombridge -Full
```

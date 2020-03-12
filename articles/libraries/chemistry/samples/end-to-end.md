---
title: Programma Quantum NWChem di esempio
description: Usando un deck di input NWChem, esaminare un esempio di come ottenere i conteggi dei Gate per la simulazione della chimica quantistica.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/23/2018
uid: microsoft.quantum.chemistry.examples.endtoend
ms.openlocfilehash: 7605676e05ee352e47791657eeaafceef5dbb493
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/10/2020
ms.locfileid: "79022502"
---
# <a name="end-to-end-with-nwchem"></a>End-to-end con NWChem #

Questo articolo illustra un esempio di come ottenere i conteggi dei Gate per la simulazione della chimica quantistica, a partire da un deck di input di [nwchem](http://www.nwchem-sw.org/index.php/Main_Page) .
Prima di procedere con questo esempio, assicurarsi di avere installato Docker, seguendo la Guida all' [installazione e alla convalida](xref:microsoft.quantum.chemistry.concepts.installation).

Per altre informazioni:
- [Struttura dei deck di input NWChem](https://github.com/nwchemgit/nwchem/wiki/Getting-Started#input-file-structure)
    - [Comandi del deck di input da usare con Quantum Development Kit](https://github.com/nwchemgit/nwchem/tree/master/contrib/quasar)
- [Installazione della libreria di chimica e delle dipendenze](xref:microsoft.quantum.chemistry.concepts.installation)
- [Conteggio delle risorse](xref:microsoft.quantum.chemistry.examples.resourcecounts)

> [!NOTE]
> Questo esempio richiede l'esecuzione di Windows PowerShell core.
> Scaricare PowerShell core per Windows, macOS o Linux in https://github.com/PowerShell/PowerShell.

## <a name="importing-required-powershell-modules"></a>Importazione di moduli di PowerShell necessari ##

Se non è già stato fatto, clonare il [repository Microsoft/Quantum](https://github.com/Microsoft/Quantum), che contiene esempi e utilità per l'uso di Quantum Development Kit:

```powershell
git clone https://github.com/Microsoft/Quantum
```

Dopo aver clonato `Microsoft/Quantum`, eseguire `cd` nella cartella `utilities/` e importare il modulo di PowerShell per l'uso di Docker e NWChem:

```powershell
cd utilities
Import-Module InvokeNWChem.psm1
```

> [!NOTE]
> Per impostazione predefinita, Windows impedisce l'esecuzione di qualsiasi script o modulo come misura di sicurezza.
> Per consentire l'esecuzione di moduli come `Invoke-NWChem.psm1` in Windows, potrebbe essere necessario modificare i criteri di esecuzione.
> A tale scopo, eseguire il comando `Set-ExecutionPolicy`:
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope Process
> ```
> Quando si esce da PowerShell, i criteri di esecuzione verranno ripristinati.
> Se si desidera salvare i criteri di esecuzione, utilizzare un valore diverso per `-Scope`:
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
> ```

A questo punto dovrebbe essere disponibile il comando `Convert-NWChemToBroombridge`:

```powershell
Get-Command -Module InvokeNWChem
```

Si importerà quindi il comando `Get-GateCount` fornito con l'esempio **GetGateCount** .
Per informazioni complete, vedere le [istruzioni fornite con l'esempio](https://github.com/Microsoft/Quantum/tree/master/samples/chemistry/GetGateCount).
Eseguire quindi il comando seguente, sostituendo `<runtime>` con `win10-x64`, `osx-x64`o `linux-x64`, a seconda del sistema operativo:

```powershell
cd ../Chemistry/GetGateCount
dotnet publish --self-contained -r <runtime>
Import-Module ./bin/Debug/netcoreapp2.1/<runtime>/publish/get-gatecount.dll
```

A questo punto dovrebbe essere disponibile il comando `Get-GateCount`:

```powershell
Get-Command Get-GateCount
```

## <a name="input-decks"></a>Deck di input ##

Il pacchetto NWChem accetta un file di testo denominato _mazzo di input_ che specifica un problema di chimica quantistica da risolvere, insieme ad altri parametri, ad esempio le impostazioni di allocazione della memoria.
Per questo esempio verrà usato uno dei deck di input predefiniti forniti con NWChem.
Innanzitutto, clonare il [repository nwchemgit/nwchem](https://github.com/nwchemgit/nwchem):

> [!NOTE]
> Poiché si tratta di un repository di grandi dimensioni, è possibile eseguire un clone superficiale per risparmiare spazio su disco e larghezza di banda, usando l'argomento `--depth 1`.
> Questa operazione è tuttavia facoltativa.
> La clonazione funzionerà correttamente senza `--depth 1`.

```powershell
git clone https://github.com/nwchemgit/nwchem --depth 1
```

Il repository `nwchemgit/nwchem` dispone di un'ampia gamma di deck di input destinati all'uso con Quantum Development Kit, elencato nella [cartella`QA/chem_library_tests`](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests).
Per questo esempio verrà usato il deck di input `H4`:

```powershell
cd nwchem/QA/chem_library_tests/H4
Get-Content h4_sto6g_0.000.nw
```

La molecola in questione è un sistema di 4 atomi idrogeno disposti in una determinata geometria che dipende da un angolo, il parametro `alpha` come indicato nel nome `h4_sto6g_alpha.nw` del mazzo. H4 è un [benchmark molecolare](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) noto per la chimica computazionale dal 1970. Il parametro `sto6g` indica che il deck implementa una rappresentazione per quanto riguarda un orbitale di tipo Slater, in particolare una rappresentazione rispetto a un [set di base di sto-ng](https://en.wikipedia.org/wiki/STO-nG_basis_sets) con 6 funzioni di base gaussiana. Questo deck di input contiene inoltre diverse istruzioni per il motore di contratti di NWChem tensore che indirizza NWChem a produrre le informazioni necessarie per l'interoperabilità con Quantum Development Kit:

```
...
set tce:print_integrals T
set tce:qorb 18
set tce:qela  9
set tce:qelb  9
```

## <a name="producing-and-consuming-broombridge-output-from-nwchem"></a>Produzione e utilizzo dell'output Broombridge da NWChem ##

Sono ora disponibili tutti gli elementi necessari per produrre e utilizzare documenti Broombridge.
Per eseguire NWChem e produrre un documento Broombridge per il `h4_sto6g_0.000.nw` Deck di input, eseguire `Convert-NWChemToBroombridge`:

> [!NOTE]
> La prima volta che si esegue questo comando, Docker Scarica l'immagine del `nwchemorg/nwchem-qc`.
> Questa operazione può richiedere alcuni minuti, a seconda della velocità di connessione, offrendo possibilmente un'opportunità per ottenere una tazza di caffè.

```powershell
Convert-NWChemToBroombridge h4_sto6g_0.000.nw 
```

Verrà generato un documento Broombridge denominato `h4_sto6g_0.000.yaml` che è possibile usare con `Get-GateCount`:

```powershell
Get-GateCount -Format YAML h4_sto6g_0.000.yaml
```

Verrà visualizzato l'output della console che contiene la stima delle risorse, ad esempio il conteggio T, il numero di rotazioni, il numero di CNOT e così via, per vari metodi di simulazione Quantum:

```powershell 
IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Trotter
TCount              : 0
RotationsCount      : 92
CNOTCount           : 520
ElapsedMilliseconds : 327

IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Qubitization
TCount              : 438
RotationsCount      : 516
CNOTCount           : 2150
ElapsedMilliseconds : 528

IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Optimized Qubitization
TCount              : 3540
RotationsCount      : 18
CNOTCount           : 7932
ElapsedMilliseconds : 721
```

Di seguito sono riportate alcune operazioni da eseguire: 
- Provare a usare diversi Deck di input predefiniti, ad esempio variando il parametro `alpha` in `h4_sto6g_alpha.nw` 
- Provare a modificare i deck modificando direttamente i deck NWChem, ad esempio esplorando `STO-nG` modelli per diverse opzioni di n, 
- Provare altri deck di input NWChem predefiniti disponibili in `nwchem/qa/chem_library_tests`,
- Provare una suite di benchmark Broombridge YAML predefiniti che sono stati generati da NWChem e sono disponibili come parte del [repository Microsoft/Quantum](https://github.com/Microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML). Questi benchmark includono: 
    - molecole piccole, ad esempio idrogeno molecolare (H2), berillio (be), litio idruro (LiH),
    - molecole più grandi, ad esempio Ozone (O3), Beta-Carotone, citosina e molto altro ancora. 
- Provare le [frecce EMSL](https://arrows.emsl.pnnl.gov/api/qsharp_chem) front-end grafiche che dispongono di un'interfaccia per la Microsoft Quantum Development Kit. 


## <a name="producing-broombridge-output-from-emsl-arrows"></a>Generazione dell'output Broombridge dalle frecce EMSL ##

Per iniziare a usare le frecce EMSL front-end basate sul Web, esplorare un browser [qui](https://arrows.emsl.pnnl.gov/api/qsharp_chem). 

> [!NOTE]
> L'esecuzione di frecce EMSL in un Web browser richiede l'abilitazione di JavaScript. Per informazioni su come abilitare JavaScript nel browser, fare riferimento a queste [istruzioni](https://www.enable-javascript.com/) . 

Per prima cosa, immettere una molecola nella casella della query che indica ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.`` 

È possibile immettere molte molecole in base al nome familiare, ad esempio "caffeina" anziché "1, 3, 7-Trimethylxanthine". 

Fare quindi clic sul pulsante ``theory{qsharp_chem}``. Questa operazione consente di popolare ulteriormente la finestra di query con un'istruzione che indica all'esecuzione di esportare l'output nel formato YAML di Broombridge. 

Ora, clock on ``Run Arrows``. A seconda delle dimensioni dell'input, l'operazione potrebbe richiedere alcuni minuti. In alternativa, nel caso in cui il modello specifico sia già stato calcolato in precedenza, è possibile eseguire la stessa operazione in modo estremamente rapido, in quanto sarà sufficiente per una ricerca in un database. In entrambi i casi, si passerà a una nuova pagina che contiene una pletora di informazioni sulla particolare esecuzione di NWChem sul deck specificato dall'input. 

È possibile scaricare e salvare il file YAML Broombridge dalla sezione che inizia con l'intestazione seguente: 
```powershell
+==================================================+
||              Molecular Calculation             ||
+==================================================+

Id     = 48443

NWOutput = Link to NWChem Output (download)

Datafiles:
qsharp_chem.yaml-2018-10-23-14:37:42 (download)
...
```

Fare clic su ``download``, che consente di salvare una copia locale con un nome file univoco, ad esempio ``qsharp_chem48443.yaml`` (il nome specifico sarà diverso per ogni esecuzione). È quindi possibile elaborare ulteriormente il file come sopra, ad esempio con 
```powershell
Get-GateCount -Format YAML qsharp_chem48443.yaml
```
per ottenere i conteggi delle risorse. 

È possibile utilizzare il generatore di molecole 3D a cui è possibile accedere dalla scheda ``Arrows Entry - 3D Builder`` della pagina iniziale delle frecce EMSL. Se si fa clic sull'immagine [JSMol](http://wiki.jmol.org/index.php/JSmol) 3D della molecola visualizzata, sarà possibile modificarla. È possibile spostare gli atomi, trascinare gli atomi in modo da modificare le distanze intermolecolari, aggiungere/rimuovere atomi e così via. Per ognuna di queste opzioni, dopo aver aggiunto ``theory{qsharp_chem}`` nella casella query, è possibile generare un'istanza dello schema YAML Broombridge ed esplorarla ulteriormente usando la libreria Quantum Chemistry. 

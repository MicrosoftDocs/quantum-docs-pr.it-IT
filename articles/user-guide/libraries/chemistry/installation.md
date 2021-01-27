---
title: Installazione di Microsoft Q# Chemistry Library
description: Informazioni su come installare la libreria Microsoft Quantum Chemistry e usarla con la piattaforma di chimica computazionale NWChem.
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.installation
no-loc:
- Q#
- $$v
ms.openlocfilehash: 5d32544bbce527a376345023d5549308fd4e7c79
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854072"
---
# <a name="chemistry-library-installation"></a>Installazione della libreria di chimica

Nell' [esempio **MolecularHydrogen**](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogen) vengono utilizzati dati di input molecolari configurati manualmente.
Sebbene si tratti di un problema per piccoli esempi, la chimica quantistica su larga scala richiede hamiltonians con milioni o miliardi di termini.
Tali hamiltonians, generati da pacchetti di chimica computazionale scalabile, sono troppo grandi per essere importati manualmente.

La libreria Quantum Chemistry per Quantum Development Kit è stata progettata per funzionare correttamente con i pacchetti di chimica computazionale, in particolare la piattaforma di chimica computazionale [**nwchem**](http://www.nwchem-sw.org/) sviluppata da Environmental Molecular Science Laboratory (EMSL) di Pacific Northwest National Laboratory.
In particolare, il [pacchetto **Microsoft. Quantum. Chemistry**](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) fornisce strumenti per il caricamento di istanze di problemi di simulazione della chimica quantistica rappresentati nello [schema Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), supportati anche per l'esportazione da versioni recenti di nwchem.

Quantum Development Kit Chemistry Library fornisce anche uno strumento da riga di comando, `qdk-chem` , per la conversione tra formati legacy e [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).

Questa sezione illustra in dettaglio come usare Quantum Development Kit con NWChem e Broombridge oppure con formati legacy e `qdk-chem` .

## <a name="using-the-quantum-development-kit-with-nwchem"></a>Uso di Quantum Development Kit con NWChem

Per iniziare a usare NWChem insieme a Quantum Development Kit, usare uno dei metodi seguenti:

- Iniziare a usare i file Broombridge esistenti forniti con gli esempi in [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/IntegralData/YAML).
- Usare il [Generatore di frecce EMSL per la Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) , che è un front-end basato sul Web con nwchem, per generare nuovi file di input molecolari in formato Broombridge.  
- Usare l' [immagine Docker](https://hub.docker.com/r/nwchemorg/nwchem-qc/) fornita da PNNL per eseguire nwchem
- [Compilare nwchem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) per la piattaforma.

Vedere [end-to-end con nwchem](xref:microsoft.quantum.chemistry.examples.endtoend) per altre informazioni su come usare nwchem per i modelli chimici per l'analisi con la libreria di chimica Quantum Developers Kit.

### <a name="getting-started-using-broombridge-files-provided-with-the-samples"></a>Introduzione all'uso dei file Broombridge forniti con gli esempi

La cartella [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/IntegralData/YAML) nel repository di esempi di Quantum Development Kit contiene file di dati di molecole in formato Broombridge.  

Come esempio semplice, usare l'esempio di libreria di chimica, [GetGateCount](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/GetGateCount) per caricare l'Hamiltoniana da uno dei file Broombridge ed eseguire stime di controllo della simulazione quantistica algorigthms:

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

Dopo aver compilato NWChem dall'origine, è possibile eseguire lo `yaml_driver` script fornito con nwchem per produrre rapidamente istanze di Broombridge dai Deck di input di nwchem:

```bash
$NWCHEM_TOP/contrib/quasar/yaml_driver input.nw
```

Questo comando creerà un nuovo `input.yaml` file nel formato Broombridge all'interno della directory corrente.

### <a name="using-nwchem-with-docker"></a>Uso di NWChem con Docker

Le immagini predefinite per l'uso di NWChem sono disponibili tra piattaforme diverse tramite l' [Hub Docker](https://hub.docker.com).
Per iniziare, seguire le istruzioni di installazione di Docker per la piattaforma:

- [Installare Docker per Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
- [Installare Docker per macOS](https://docs.docker.com/docker-for-mac/install/)
- [Installare Docker per Windows 10](https://docs.docker.com/docker-for-windows/install/)

> [!TIP]
> Se si usa Docker per Windows, sarà necessario condividere l'unità contenente la directory temporanea (in genere questa è l' `C:\` unità) con il daemon docker. Per altri dettagli, vedere la [documentazione di Docker](https://docs.docker.com/docker-for-windows/#shared-drives) .

Una volta installato Docker, è possibile usare il modulo di PowerShell fornito con gli esempi di Quantum Development Kit per eseguire l'immagine oppure è possibile eseguire l'immagine manualmente.
Qui viene illustrato in dettaglio l'uso di PowerShell. Se si vuole usare manualmente l'immagine Docker, vedere la [documentazione fornita con l'immagine](https://hub.docker.com/r/nwchemorg/nwchem-qc/).

#### <a name="running-nwchem-through-powershell-core"></a>Esecuzione di NWChem tramite PowerShell Core

Per usare l'immagine Docker NWChem con Quantum Development Kit, viene fornito un modulo di PowerShell di piccole dimensioni che gestisce automaticamente i file in e da NWChem.
Se PowerShell Core non è ancora installato, è possibile scaricarlo multipiattaforma dal [repository di PowerShell su GitHub](https://github.com/PowerShell/PowerShell#get-powershell).

> [!NOTE]
> PowerShell core viene usato anche per alcuni esempi per illustrare l'interoperabilità con data science e flussi di lavoro di analisi business.

Dopo aver installato PowerShell core, importare `InvokeNWChem.psm1` per rendere disponibili i comandi nwchem nella sessione corrente:

```powershell
cd Quantum/utilities/
Import-Module ./InvokeNWChem.psm1
```

In questo modo il `Convert-NWChemToBroombridge` comando verrà reso disponibile nella sessione corrente di PowerShell.
Per scaricare le immagini necessarie da Docker e usarle per eseguire i deck di input NWChem e acquisire l'output in Broombridge, eseguire le operazioni seguenti:

```powershell
Convert-NWChemToBroombridge ./input.nw
```

Verrà creato un file Broombridge eseguendo NWChem in `input.nw` .
Per impostazione predefinita, l'output di Broombridge avrà lo stesso nome e percorso del deck di input, con l' `.nw` estensione sostituita da `.yaml` .
È possibile eseguire l'override di questo oggetto utilizzando il `-DestinationPath` parametro per `Convert-NWChemToBroombridge` .
Per ottenere altre informazioni, è possibile usare la funzionalità integrata della Guida di PowerShell:

```powershell
Convert-NWChemToBroombridge -?
Get-Help Convert-NWChemToBroombridge -Full
```

## <a name="using-the-quantum-development-kit-with-qdk-chem"></a>Utilizzo del kit di sviluppo Quantum con `qdk-chem`

Per installare `qdk-chem` , è possibile usare il .NET Core SDK dalla riga di comando:

```dotnetcli
dotnet tool install --global Microsoft.Quantum.Chemistry.Tools
```

Una volta installato `qdk-chem` , è possibile usare l' `--help` opzione per ottenere altri dettagli sulle funzionalità offerte dallo `qdk-chem` strumento.

Per eseguire la conversione da e verso Broombridge, è possibile usare il `qdk-chem convert` comando:

```
qdk-chem convert --from fcidump --to broombridge data.fcidump --out data.yml
```

Il `qdk-chem convert` comando può anche accettare i dati dall'input standard e può scrivere nell'output standard. ciò è particolarmente utile all'interno degli script e per l'integrazione con strumenti che esportano in formati legacy.
Ad esempio, in Bash:

```bash
cat data.fcidump | qdk-convert --from fcidump --to broombridge - > data.yml
```

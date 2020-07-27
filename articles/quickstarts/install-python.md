---
title: Sviluppare con Q# e Python
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: ec5e66e0c85d89888a8ff1e7d6bf18bf89ff44ac
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871587"
---
# <a name="develop-with-q-and-python"></a>Sviluppare con Q# e Python

Installare il QDK per sviluppare programmi host Python che chiamino operazioni Q#.

## <a name="install-the-qsharp-python-package"></a>Installare il pacchetto Python `qsharp`

### <a name="install-using-conda-recommended"></a>[Installazione con conda (scelta consigliata)](#tab/tabid-conda)

1. Installare [Miniconda](https://docs.conda.io/en/latest/miniconda.html) o [Anaconda](https://www.anaconda.com/products/individual#Downloads). **Nota:** è richiesta l'installazione a 64 bit.

1. Aprire un prompt di Anaconda.

   - In alternativa, se si preferisce usare PowerShell o pwsh, aprire una shell, eseguire `conda init powershell`, quindi chiudere e riaprire la shell.

1. Creare e attivare un nuovo ambiente conda denominato `qsharp-env` con i pacchetti necessari, inclusi Jupyter Notebook e IQ#, eseguendo i comandi seguenti:

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. Eseguire `python -c "import qsharp"` dallo stesso terminale per verificare l'installazione e popolare la cache del pacchetto locale con tutti i componenti di QDK necessari.

### <a name="install-using-net-cli-and-pip-advanced"></a>[Installazione con l'interfaccia della riga di comando .NET e pip (opzione avanzata)](#tab/tabid-dotnetcli)

1. Prerequisiti:

    - [Python](https://www.python.org/downloads/) 3.6 o versione successiva
    - Gestione pacchetti Python [PIP](https://pip.pypa.io/en/stable/installing)
    - [.NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. Installare `qsharp`, un pacchetto Python che consente l'interoperabilità tra Q# e Python.

    ```
    pip install qsharp
    ```

1. Installare IQ#, un kernel usato principalmente da Jupyter e Python che fornisce le funzionalità essenziali per la compilazione e l'esecuzione di operazioni Q#.

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > Se durante il passaggio `dotnet iqsharp install` viene visualizzato un errore, aprire una nuova finestra del terminale e riprovare.
    > Se il problema persiste, provare a individuare lo strumento `dotnet-iqsharp` installato (in Windows `dotnet-iqsharp.exe`) ed eseguire:
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > dove `/path/to/dotnet-iqsharp` deve essere sostituito con il percorso assoluto dello strumento `dotnet-iqsharp` nel file system.
    > Tale strumento si trova in genere in `.dotnet/tools` nella cartella del profilo utente.
    
***

L'operazione è terminata. Sono ora disponibili il pacchetto Python `qsharp` e il kernel IQ# per Jupyter, che fornisce la funzionalità di base per la compilazione e l'esecuzione di operazioni Q# da Python e consente di usare notebook di Jupyter Q#.

## <a name="choose-your-ide"></a>Scegliere l'IDE

Anche se è possibile usare Q# con Python in qualsiasi IDE, è consigliabile usare l'IDE di Visual Studio Code (VS Code) per le applicazioni che combinano Q# e Python. Con l'estensione QDK di Visual Studio Code è possibile accedere a funzionalità più avanzate, ad esempio avvisi, evidenziazione della sintassi, modelli di progetto e altro ancora.

Se si vuole usare VS Code:

- Installare [VS Code](https://code.visualstudio.com/download) (Windows, Linux e Mac).
- Installare l'[estensione QDK per VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

Se si vuole usare un editor diverso, è possibile seguire le istruzioni sopra riportate.

## <a name="write-your-first-q-program"></a>Scrivere il primo programma Q#

A questo punto è possibile verificare l'installazione del pacchetto Python `qsharp` scrivendo ed eseguendo un semplice programma Q#.

1. Creare un'operazione Q# minima creando un file denominato `Operation.qs` e aggiungendovi il codice seguente:

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="3-14":::

1. Nella stessa cartella di `Operation.qs`creare un programma Python denominato `host.py` per simulare l'operazione `SampleQuantumRandomNumberGenerator()` Q#:

    ```python
    import qsharp
    from Qrng import SampleQuantumRandomNumberGenerator

    SampleQuantumRandomNumberGenerator.simulate()
    ```

1. Nell'ambiente creato durante l'installazione, ovvero l'ambiente conda o l'ambiente Python in cui è stato installato `qsharp`, eseguire il programma:

    ```
    python host.py
    ```

1. Verrà visualizzato il risultato dell'operazione richiamata. In questo caso, poiché l'operazione genera un risultato casuale, sullo schermo verrà visualizzato `Zero` o `One`. Se il programma viene eseguito ripetutamente, si vedrà ogni risultato per circa la metà del tempo.

> [!NOTE]
> * Il codice Python è un normale programma Python. Per scrivere il programma Python e chiamare le operazioni Q#, è possibile usare qualsiasi ambiente Python, inclusi i notebook di Jupyter basati su Python. Il programma Python può importare operazioni Q# da qualsiasi file con estensione qs situato nella stessa cartella del codice Python.

## <a name="next-steps"></a>Passaggi successivi

Ora che è stato installato Quantum Development Kit nell'ambiente preferito, è possibile seguire questa esercitazione per scrivere ed eseguire [il primo programma quantistico](xref:microsoft.quantum.quickstarts.qrng).

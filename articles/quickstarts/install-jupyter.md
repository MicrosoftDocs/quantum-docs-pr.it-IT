---
title: Sviluppare con notebook di Jupyter Q#
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 10b1faafa70c87a99ea09916e2c386b32f9a570f
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87866809"
---
# <a name="develop-with-no-locq-jupyter-notebooks"></a>Sviluppare con notebook di Jupyter Q#

Installare il QDK per sviluppare operazioni Q# nei notebook di Jupyter Q#.

I notebook di Jupyter consentono l'esecuzione di codice sul posto, unitamente a istruzioni, note e altro contenuto. Questo ambiente è ideale per la scrittura di codice Q# con spiegazioni incorporate o esercitazioni interattive sul calcolo quantistico. Ecco cosa occorre fare per iniziare a creare notebook Q#.

> [!NOTE]
> * Nei notebook di Jupyter per Q# è possibile eseguire solo codice Q# e non è possibile chiamare operazioni da programmi host esterni, ad esempio file Python o C#. Questo ambiente non è appropriato se si intende combinare un programma host classico esterno con il programma quantistico.

## <a name="install-the-ino-locq-jupyter-kernel"></a>Installare il kernel IQ# per Jupyter

IQ# (pronunciato i-q-sharp) è un'estensione usata principalmente da Jupyter e Python in .NET Core SDK che fornisce le funzionalità essenziali per la compilazione e la simulazione di operazioni Q#.

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

### <a name="install-using-net-cli-advanced"></a>[Installazione con l'interfaccia della riga di comando .NET (opzione avanzata)](#tab/tabid-dotnetcli)

1. Prerequisiti:

    - [Python](https://www.python.org/downloads/) 3.6 o versione successiva
    - [Notebook di Jupyter](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. Installare il pacchetto `Microsoft.Quantum.IQSharp`.

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

L'operazione è terminata. A questo punto, è disponibile il kernel IQ# per Jupyter, che fornisce la funzionalità di base per la compilazione e l'esecuzione di operazioni Q# da notebook di Jupyter Q#.

## <a name="create-your-first-no-locq-notebook"></a>Creare il primo notebook Q#

A questo punto è possibile verificare l'installazione del notebook di Jupyter Q# scrivendo ed eseguendo una semplice operazione Q#.

1. Nell'ambiente creato durante l'installazione, ovvero l'ambiente conda creato o l'ambiente Python in cui è stato installato Jupyter, eseguire il comando seguente per avviare il server di notebook di Jupyter:

    ```
    jupyter notebook
    ```

    - Se il notebook di Jupyter non si apre automaticamente nel browser, copiare e incollare l'URL fornito dalla riga di comando nel browser.

1. Scegliere "Nuovo" → "Q#" per creare un notebook di Jupyter con un kernel Q# e aggiungere il codice seguente nella prima cella del notebook:

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="6-13":::

1. Eseguire la cella del notebook:

    ![Cella di notebook di Jupyter con codice Q#](~/media/install-guide-jupyter.png)

    Nell'output della cella verrà visualizzato `SampleQuantumRandomNumberGenerator`. Quando è in esecuzione in Jupyter Notebook, il codice Q# viene compilato e la cella restituisce il nome di tutte le operazioni che trova.

1. In una nuova cella eseguire l'operazione appena creata (in un simulatore) usando il comando `%simulate`:

    ![Cella di notebook di Jupyter con il magic %simulate](~/media/install-guide-jupyter-simulate.png)

    Verrà visualizzato il risultato dell'operazione richiamata. In questo caso, poiché l'operazione genera un risultato casuale, sullo schermo verrà visualizzato `Zero` o `One`. Se la cella viene eseguita ripetutamente, si vedrà ogni risultato per circa la metà del tempo.

## <a name="next-steps"></a>Passaggi successivi

Ora che è stato installato QDK per notebook di Jupyter Q#, è possibile scrivere ed eseguire il [primo programma quantistico](xref:microsoft.quantum.quickstarts.qrng) scrivendo il codice Q# direttamente nell'ambiente di Jupyter Notebook.

Per altri esempi sulle operazioni che è possibile eseguire con i notebook di Jupyter Q#, vedere:

- [Introduzione a Q# e Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/). Questo articolo include un notebook di Jupyter Q# che fornisce altri dettagli su come usare Q# in questo ambiente.
- [Quantum Katas](xref:microsoft.quantum.overview.katas), una raccolta open source di esercitazioni autogestite e set di esercizi di programmazione sotto forma di notebook di Jupyter Q#. I [notebook delle esercitazioni di Quantum Katas](https://github.com/microsoft/QuantumKatas#tutorial-topics) costituiscono un valido punto di partenza. Le esercitazioni Quantum Katas sono infatti ideali per apprendere sia i concetti del calcolo quantistico che della programmazione Q#. Si tratta di un ottimo esempio del tipo di contenuto che è possibile creare con i notebook di Jupyter Q#.

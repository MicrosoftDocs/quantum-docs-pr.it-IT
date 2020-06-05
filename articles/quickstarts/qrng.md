---
title: Creazione di un generatore quantistico di numeri casuali
description: Compilare un progetto Q# che illustra i concetti fondamentali del calcolo quantistico, ad esempio la sovrapposizione, creando un generatore quantistico di numeri casuali.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: 8fafbccfe2a94a824353221b5e7eb8bac16c42f2
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327357"
---
# <a name="tutorial-implement-a-quantum-random-number-generator-in-q"></a>Esercitazione: Implementare un generatore quantistico di numeri casuali in Q\#

Un semplice esempio di algoritmo quantistico scritto in Q# è un generatore quantistico di numeri casuali. Questo algoritmo sfrutta la natura dei meccanismi quantistici per generare un numero casuale.

## <a name="prerequisites"></a>Prerequisiti

- Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- Creare un progetto Q# [usando Q# dalla riga di comando](xref:microsoft.quantum.install.standalone) oppure con un [programma host Python](xref:microsoft.quantum.install.python) o un [programma host C#](xref:microsoft.quantum.install.cs).

## <a name="write-a-q-operation"></a>Scrivere un'operazione Q#

### <a name="q-operation-code"></a>Codice dell'operazione Q#

1. Sostituire il contenuto del file Program.qs con il codice seguente:

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-15,34":::

Come illustrato nell'articolo [Informazioni sul calcolo quantistico](xref:microsoft.quantum.overview.understanding), un qubit è un'unità di informazioni quantistiche che possono essere in sovrapposizione. Quando viene misurato, il valore di un qubit può essere solo 0 o 1. Tuttavia, durante l'esecuzione lo stato del qubit rappresenta la probabilità di leggere un valore 0 o 1 con una misura. Questo stato probabilistico è noto come sovrapposizione. È possibile usare questa probabilità per generare numeri casuali.

Nell'operazione Q# viene introdotto il tipo di dati `Qubit`, nativo per Q#. È possibile allocare un `Qubit` solo con un'istruzione `using`. Quando viene allocato, un qubit è sempre nello stato `Zero`. 

Con l'operazione `H`, è possibile posizionare il `Qubit` in sovrapposizione. Per misurare un qubit e leggerne il valore, si usa l'operazione `M` intrinseca.

Posizionando il `Qubit` in sovrapposizione e misurandolo, il risultato sarà un valore diverso ogni volta che viene richiamato il codice.

Quando un `Qubit` viene deallocato, deve essere impostato in modo esplicito sullo stato `Zero`. In caso contrario, il simulatore restituirà un errore di runtime. A tale scopo, richiamare `Reset`.

### <a name="visualizing-the-code-with-the-bloch-sphere"></a>Visualizzazione del codice con la sfera di Bloch

Nella sfera di Bloch il polo nord rappresenta il valore classico **0** e il polo sud rappresenta il valore classico **1**. Qualsiasi sovrapposizione può essere rappresentata da un punto sulla sfera (rappresentato da una freccia). Più vicina è la fine della freccia a un polo, più alta è la probabilità che il qubit collassi nel valore classico assegnato a tale polo quando viene misurato. Ad esempio, lo stato del qubit rappresentato dalla freccia rossa nella figura seguente ha una probabilità più elevata di restituire il valore **0** se lo si misura.

<img src="~/media/qrng-Bloch.png" width="175" alt="A qubit state with a high probability of measuring zero">

È possibile usare questa rappresentazione per visualizzare le operazioni eseguite dal codice:

* Innanzitutto si inizia con un qubit inizializzato nello stato **0** e si applica `H` per creare una sovrapposizione in cui le probabilità per **0** e **1** sono le stesse.

<img src="~/media/qrng-H.png" width="450" alt="Preparing a qubit in superposition">

* Si misura quindi il qubit e si salva l'output:

<img src="~/media/qrng-meas.png" width="450" alt="Measuring a qubit and saving the output">

Poiché il risultato della misura è completamente casuale, è stato ottenuto un bit casuale. È possibile chiamare questa operazione più volte per creare valori integer. Ad esempio, se si chiama l'operazione tre volte per ottenere tre bit casuali, è possibile creare numeri casuali a 3 bit, ovvero un numero casuale compreso tra 0 e 7.


## <a name="creating-a-complete-random-number-generator"></a>Creazione di un generatore di numeri casuali completo

Ora che è disponibile un'operazione Q # che genera bit casuali, è possibile usarla per compilare un generatore di numeri casuali quantistici completo. È possibile usare applicazioni da riga di comando Q# o un programma host.



### <a name="q-command-line-applications-with-visual-studio-or-visual-studio-code"></a>[Applicazioni da riga di comando Q# con Visual Studio o Visual Studio Code](#tab/tabid-qsharp)

Per creare l'applicazione da riga di comando Q# completa, aggiungere il punto di ingresso seguente al programma Q#: 

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="17-33":::

Il file eseguibile eseguirà l'operazione o la funzione contrassegnata con l'attributo `@EntryPoint()` in un simulatore o in un'utilità di stima delle risorse, a seconda della configurazione del progetto e delle opzioni della riga di comando.

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-34":::

In Visual Studio è sufficiente premere CTRL+F5 per eseguire lo script.

In VS Code compilare Program.qs per la prima volta digitando quanto segue nel terminale:

```dotnetcli
dotnet build
```

Per le esecuzioni successive non è necessario ripetere la compilazione. Per eseguirlo, digitare il comando seguente e premere INVIO:

```dotnetcli
dotnet run --no-build
```

### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Python con Visual Studio Code o riga di comando](#tab/tabid-python)

Per eseguire il nuovo programma Q# da Python, salvare il codice seguente come `host.py`:

:::code language="python" source="~/quantum/samples/interoperability/qrng/host.py" range="11-30":::

È quindi possibile eseguire il programma host Python dalla riga di comando:

```bash
$ python host.py
Preparing Q# environment...
..The random number generated is 42
```

### <a name="c-with-visual-studio-code-or-visual-studio"></a>[C# con Visual Studio Code o Visual Studio](#tab/tabid-csharp)

Per eseguire il nuovo programma Q# da C#, modificare `Driver.cs` per includere il codice C# seguente:

:::code language="csharp" source="~/quantum/samples/interoperability/qrng/Host.cs" range="4-39":::

È quindi possibile eseguire il programma host C# dalla riga di comando (in Visual Studio è necessario premere F5):

```bash
$ dotnet run
The random number generated is 42
```

***

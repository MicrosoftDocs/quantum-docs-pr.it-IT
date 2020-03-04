---
title: Creazione di un generatore quantistico di numeri casuali
description: Compilare un progetto Q# che illustra i concetti fondamentali del calcolo quantistico, ad esempio la sovrapposizione, creando un generatore quantistico di numeri casuali.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: b9c8592b1296a7de1b9ad5d0538ad1972ec25e31
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906985"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a>Guida introduttiva: Implementare un generatore quantistico di numeri casuali in Q#
Un semplice esempio di algoritmo quantistico scritto in Q# è un generatore quantistico di numeri casuali. Questo algoritmo sfrutta la natura dei meccanismi quantistici per generare un numero casuale. 

## <a name="prerequisites"></a>Prerequisiti

- Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- [Creare un progetto Q#](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a>Scrivere un'operazione Q#

### <a name="q-operation-code"></a>Codice dell'operazione Q#

1. Sostituire il contenuto del file Operation.qs con il codice seguente:

 :::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-14":::

Come illustrato nell'articolo [Che cos'è il calcolo quantistico](xref:microsoft.quantum.overview.what), un qubit è un'unità di informazioni quantistiche che possono essere in sovrapposizione. Quando viene misurato, il valore di un qubit può essere solo 0 o 1. Tuttavia, durante l'esecuzione lo stato del qubit rappresenta la probabilità di leggere un valore 0 o 1 con una misura. Questo stato probabilistico è noto come sovrapposizione. È possibile usare questa probabilità per generare numeri casuali.

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

## <a name="creating-a-complete-random-number-generator-using-a-host-program"></a>Creazione di un generatore di numeri casuali completo con un programma host

Ora che è disponibile un'operazione Q # che genera bit casuali, è possibile usarla per compilare un generatore di numeri casuali quantistici completo con un programma host.

 ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Python con Visual Studio Code o riga di comando](#tab/tabid-python)
 
 Per eseguire il nuovo programma Q# da Python, salvare il codice seguente come `host.py`:
 
:::code language="python" source="~/quantum/samples/getting-started/qrng/host.py" range="11-30":::

 È quindi possibile eseguire il programma host Python dalla riga di comando:
 ```bash
 $ python host.py
 Preparing Q# environment...
 ..The random number generated is 42
 ```
 ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[C# con Visual Studio Code o riga di comando](#tab/tabid-csharp)
 
 Per eseguire il nuovo programma Q# da C#, modificare `Driver.cs` per includere il codice C# seguente:
 
 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::
 
 È quindi possibile eseguire il programma host C# dalla riga di comando:
 
 ```bash
 $ dotnet run
 The random number generated is 42
 ```

 ### <a name="c-with-visual-studio-2019"></a>[C# con Visual Studio 2019](#tab/tabid-vs2019)

 Per eseguire il nuovo programma Q# da C# in Visual Studio, modificare `Driver.cs` per includere il codice C# seguente:

 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::

 Premere quindi F5. L'esecuzione del programma verrà avviata e verrà visualizzata una nuova finestra con il numero casuale generato: 

 ```bash
 $ dotnet run
 The random number generated is 42
 ```
 ***

---
title: Creazione di un generatore quantistico di numeri casuali
description: Compilare un progetto Q# che illustra i concetti fondamentali del calcolo quantistico, ad esempio la sovrapposizione, creando un generatore quantistico di numeri casuali.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: c3039b92c4b3235a397d5cf31280ac2673706e9d
ms.sourcegitcommit: 2ca4755d1a63431e3cb2d2918a10ad477ec2e368
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73462829"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a>Guida introduttiva: Implementare un generatore quantistico di numeri casuali in Q#
Un semplice esempio di algoritmo quantistico scritto in Q# è un generatore quantistico di numeri casuali. Questo algoritmo sfrutta la natura dei meccanismi quantistici per generare un numero casuale. 

## <a name="prerequisites"></a>Prerequisiti

- Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- [Creare un progetto Q#](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a>Scrivere un'operazione Q#

### <a name="q-operation-code"></a>Codice dell'operazione Q#

1. Sostituire il contenuto del file Operation.qs con il codice seguente:

    ```qsharp
    namespace Quantum {
        open Microsoft.Quantum.Intrinsic;

        operation QuantumRandomNumberGenerator() : Result {
            using(q = Qubit())  { // Allocate a qubit.
                H(q);             // Put the qubit to superposition. It now has a 50% chance of being 0 or 1.
                let r = M(q);     // Measure the qubit value.
                Reset(q);
                return r;
            }
        }
    }
    ```

Come illustrato nell'articolo [Che cos'è il calcolo quantistico](xref:microsoft.quantum.overview.what), un qubit è un'unità di informazioni quantistiche che possono essere in sovrapposizione. Quando viene misurato, il valore di un qubit può essere solo 0 o 1. Tuttavia, durante l'esecuzione lo stato del qubit rappresenta la probabilità di leggere un valore 0 o 1 con una misura. Questo stato probabilistico è noto come sovrapposizione. È possibile usare questa probabilità per generare numeri casuali.

Nell'operazione Q# viene introdotto il tipo di dati `Qubit`, nativo per Q#. È possibile allocare un `Qubit` solo con un'istruzione `using`. Quando viene allocato, un qubit è sempre nello stato `Zero`. 

Con l'operazione `H`, è possibile posizionare il `Qubit` in sovrapposizione. Per misurare un qubit e leggerne il valore, si usa l'operazione `M` intrinseca.

Posizionando il `Qubit` in sovrapposizione e misurandolo, il risultato sarà un valore diverso ogni volta che viene richiamato il codice. 

Quando un `Qubit` viene deallocato, deve essere impostato in modo esplicito sullo stato `Zero`. In caso contrario, il simulatore restituirà un errore di runtime. A tale scopo, richiamare `Reset`.

### <a name="visualizing-the-code-with-the-bloch-sphere"></a>Visualizzazione del codice con la sfera di Bloch

Nella sfera di Bloch il polo nord rappresenta il valore classico **0** e il polo sud rappresenta il valore classico **1**. Qualsiasi sovrapposizione può essere rappresentata da un punto sulla sfera (rappresentato da una freccia). Più vicina è la fine della freccia a un polo, più alta è la probabilità che il qubit collassi nel valore classico assegnato a tale polo quando viene misurato. Ad esempio, lo stato del qubit rappresentato dalla freccia rossa nella figura seguente ha una probabilità più elevata di restituire il valore **0** se lo si misura.

<img src="./Bloch.svg" width="175">

È possibile usare questa rappresentazione per visualizzare le operazioni eseguite dal codice:

* Innanzitutto si inizia con un qubit inizializzato nello stato **0** e si applica `H` per creare una sovrapposizione in cui le probabilità per **0** e **1** sono le stesse.

<img src="./H.svg" width="450">

* Si misura quindi il qubit e si salva l'output:

<img src="./Measurement2.svg" width="450">

Poiché il risultato della misura è completamente casuale, è stato ottenuto un bit casuale. È possibile chiamare questa operazione più volte per creare valori integer. Ad esempio, se si chiama l'operazione tre volte per ottenere tre bit casuali, è possibile creare numeri casuali a 3 bit, ovvero un numero casuale compreso tra 0 e 7.

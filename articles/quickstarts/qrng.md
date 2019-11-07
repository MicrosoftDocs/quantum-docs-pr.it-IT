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
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a><span data-ttu-id="af439-103">Guida introduttiva: Implementare un generatore quantistico di numeri casuali in Q#</span><span class="sxs-lookup"><span data-stu-id="af439-103">Quickstart: Implement a Quantum Random Number Generator in Q#</span></span>
<span data-ttu-id="af439-104">Un semplice esempio di algoritmo quantistico scritto in Q# è un generatore quantistico di numeri casuali.</span><span class="sxs-lookup"><span data-stu-id="af439-104">A simple example of a quantum algorithm written in Q# is a quantum random number generator.</span></span> <span data-ttu-id="af439-105">Questo algoritmo sfrutta la natura dei meccanismi quantistici per generare un numero casuale.</span><span class="sxs-lookup"><span data-stu-id="af439-105">This algorithm leverages the nature of quantum mechanics to produce a random number.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="af439-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="af439-106">Prerequisites</span></span>

- <span data-ttu-id="af439-107">Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="af439-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- [<span data-ttu-id="af439-108">Creare un progetto Q#</span><span class="sxs-lookup"><span data-stu-id="af439-108">Create a Q# Project</span></span>](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a><span data-ttu-id="af439-109">Scrivere un'operazione Q#</span><span class="sxs-lookup"><span data-stu-id="af439-109">Write a Q# operation</span></span>

### <a name="q-operation-code"></a><span data-ttu-id="af439-110">Codice dell'operazione Q#</span><span class="sxs-lookup"><span data-stu-id="af439-110">Q# operation code</span></span>

1. <span data-ttu-id="af439-111">Sostituire il contenuto del file Operation.qs con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="af439-111">Replace the contents of the Operation.qs file with the following code:</span></span>

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

<span data-ttu-id="af439-112">Come illustrato nell'articolo [Che cos'è il calcolo quantistico](xref:microsoft.quantum.overview.what), un qubit è un'unità di informazioni quantistiche che possono essere in sovrapposizione.</span><span class="sxs-lookup"><span data-stu-id="af439-112">As mentioned in our [What is Quantum Computing?](xref:microsoft.quantum.overview.what) article, a qubit is a unit of quantum information that can be in superposition.</span></span> <span data-ttu-id="af439-113">Quando viene misurato, il valore di un qubit può essere solo 0 o 1.</span><span class="sxs-lookup"><span data-stu-id="af439-113">When measured, a qubit can only be either 0 or 1.</span></span> <span data-ttu-id="af439-114">Tuttavia, durante l'esecuzione lo stato del qubit rappresenta la probabilità di leggere un valore 0 o 1 con una misura.</span><span class="sxs-lookup"><span data-stu-id="af439-114">However, during execution the state of the qubit represents the probability of reading either a 0 or a 1 with a measurement.</span></span> <span data-ttu-id="af439-115">Questo stato probabilistico è noto come sovrapposizione.</span><span class="sxs-lookup"><span data-stu-id="af439-115">This probabilistic state is known as superposition.</span></span> <span data-ttu-id="af439-116">È possibile usare questa probabilità per generare numeri casuali.</span><span class="sxs-lookup"><span data-stu-id="af439-116">We can use this probability to generate random numbers.</span></span>

<span data-ttu-id="af439-117">Nell'operazione Q# viene introdotto il tipo di dati `Qubit`, nativo per Q#.</span><span class="sxs-lookup"><span data-stu-id="af439-117">In our Q# operation, we introduce the `Qubit` datatype, native to Q#.</span></span> <span data-ttu-id="af439-118">È possibile allocare un `Qubit` solo con un'istruzione `using`.</span><span class="sxs-lookup"><span data-stu-id="af439-118">We can only allocate a `Qubit` with a `using` statement.</span></span> <span data-ttu-id="af439-119">Quando viene allocato, un qubit è sempre nello stato `Zero`.</span><span class="sxs-lookup"><span data-stu-id="af439-119">When it gets allocated a qubit is always in the `Zero`  state.</span></span> 

<span data-ttu-id="af439-120">Con l'operazione `H`, è possibile posizionare il `Qubit` in sovrapposizione.</span><span class="sxs-lookup"><span data-stu-id="af439-120">Using the `H` operation, we are able to put our `Qubit` in superposition.</span></span> <span data-ttu-id="af439-121">Per misurare un qubit e leggerne il valore, si usa l'operazione `M` intrinseca.</span><span class="sxs-lookup"><span data-stu-id="af439-121">To measure a qubit and read its value, you use the `M` intrinsic operation.</span></span>

<span data-ttu-id="af439-122">Posizionando il `Qubit` in sovrapposizione e misurandolo, il risultato sarà un valore diverso ogni volta che viene richiamato il codice.</span><span class="sxs-lookup"><span data-stu-id="af439-122">By putting our `Qubit` in superposition and measuring it, our result will be a different value each time the code is invoked.</span></span> 

<span data-ttu-id="af439-123">Quando un `Qubit` viene deallocato, deve essere impostato in modo esplicito sullo stato `Zero`. In caso contrario, il simulatore restituirà un errore di runtime.</span><span class="sxs-lookup"><span data-stu-id="af439-123">When a `Qubit` is de-allocated it must be explicitly set back to the `Zero` state, otherwise the simulator will report a runtime error.</span></span> <span data-ttu-id="af439-124">A tale scopo, richiamare `Reset`.</span><span class="sxs-lookup"><span data-stu-id="af439-124">An easy way to achieve this is invoking `Reset`.</span></span>

### <a name="visualizing-the-code-with-the-bloch-sphere"></a><span data-ttu-id="af439-125">Visualizzazione del codice con la sfera di Bloch</span><span class="sxs-lookup"><span data-stu-id="af439-125">Visualizing the code with the Bloch sphere</span></span>

<span data-ttu-id="af439-126">Nella sfera di Bloch il polo nord rappresenta il valore classico **0** e il polo sud rappresenta il valore classico **1**.</span><span class="sxs-lookup"><span data-stu-id="af439-126">In the Bloch sphere the north pole represents the classical value **0** and the south pole represents the classical value **1**.</span></span> <span data-ttu-id="af439-127">Qualsiasi sovrapposizione può essere rappresentata da un punto sulla sfera (rappresentato da una freccia).</span><span class="sxs-lookup"><span data-stu-id="af439-127">Any superposition can be represented by a point on the sphere (represented by an arrow).</span></span> <span data-ttu-id="af439-128">Più vicina è la fine della freccia a un polo, più alta è la probabilità che il qubit collassi nel valore classico assegnato a tale polo quando viene misurato.</span><span class="sxs-lookup"><span data-stu-id="af439-128">When the closer the end of the arrow to a pole, the higher the probability the qubit collapses into the classical value assigned to that pole when measured.</span></span> <span data-ttu-id="af439-129">Ad esempio, lo stato del qubit rappresentato dalla freccia rossa nella figura seguente ha una probabilità più elevata di restituire il valore **0** se lo si misura.</span><span class="sxs-lookup"><span data-stu-id="af439-129">For example, the qubit state represented by the red arrow below has a higher probability of giving the value **0** if we measure it.</span></span>

<img src="./Bloch.svg" width="175">

<span data-ttu-id="af439-130">È possibile usare questa rappresentazione per visualizzare le operazioni eseguite dal codice:</span><span class="sxs-lookup"><span data-stu-id="af439-130">We can use this representation to visualize what the code is doing:</span></span>

* <span data-ttu-id="af439-131">Innanzitutto si inizia con un qubit inizializzato nello stato **0** e si applica `H` per creare una sovrapposizione in cui le probabilità per **0** e **1** sono le stesse.</span><span class="sxs-lookup"><span data-stu-id="af439-131">First we start with a qubit initalizated in the state **0** and apply `H` to create a superposition in which the probabilities for **0** and **1** are the same.</span></span>

<img src="./H.svg" width="450">

* <span data-ttu-id="af439-132">Si misura quindi il qubit e si salva l'output:</span><span class="sxs-lookup"><span data-stu-id="af439-132">Then we measure the qubit and save the output:</span></span>

<img src="./Measurement2.svg" width="450">

<span data-ttu-id="af439-133">Poiché il risultato della misura è completamente casuale, è stato ottenuto un bit casuale.</span><span class="sxs-lookup"><span data-stu-id="af439-133">Since the outcome of the measurement is completely random, we have obtained a random bit.</span></span> <span data-ttu-id="af439-134">È possibile chiamare questa operazione più volte per creare valori integer.</span><span class="sxs-lookup"><span data-stu-id="af439-134">We can call this operation several times to create integers.</span></span> <span data-ttu-id="af439-135">Ad esempio, se si chiama l'operazione tre volte per ottenere tre bit casuali, è possibile creare numeri casuali a 3 bit, ovvero un numero casuale compreso tra 0 e 7.</span><span class="sxs-lookup"><span data-stu-id="af439-135">For example, if we call the operation three times to obtain three random bits, we can build random 3-bit numbers (that is, a random number between 0 and 7).</span></span>

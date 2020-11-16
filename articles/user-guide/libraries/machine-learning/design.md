---
title: Progettare un classificatore personalizzato con QDK
description: Informazioni sui concetti di base per la progettazione di modelli di circuito per il classificatore incentrato sul circuito Quantum.
author: geduardo
ms.author: v-edsanc
ms.date: 02/17/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.design
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: 221479e616ff7a03c4ac20e0062125660314e95b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691155"
---
# <a name="design-your-own-classifier"></a><span data-ttu-id="07d7a-103">Progettare un classificatore personalizzato</span><span class="sxs-lookup"><span data-stu-id="07d7a-103">Design your own classifier</span></span>

<span data-ttu-id="07d7a-104">In questa guida si apprenderanno i concetti di base della progettazione dei modelli di circuito per il classificatore incentrato sul circuito Quantum.</span><span class="sxs-lookup"><span data-stu-id="07d7a-104">In this guide you will learn the basic concepts behind the design of circuit models for the quantum circuit centric classifier.</span></span>

<span data-ttu-id="07d7a-105">Come nell'apprendimento avanzato classico, non esiste alcuna regola generale per la scelta di un'architettura specifica.</span><span class="sxs-lookup"><span data-stu-id="07d7a-105">As in classical deep learning, there is no general rule for choosing a specific architecture.</span></span> <span data-ttu-id="07d7a-106">A seconda del problema, alcune architetture offriranno prestazioni migliori rispetto ad altre.</span><span class="sxs-lookup"><span data-stu-id="07d7a-106">Depending on the problem some architectures will perform better than others.</span></span> <span data-ttu-id="07d7a-107">Tuttavia, esistono alcuni concetti che possono risultare utili durante la progettazione del circuito:</span><span class="sxs-lookup"><span data-stu-id="07d7a-107">But, there are some concepts that might be useful when designing the circuit:</span></span>

- <span data-ttu-id="07d7a-108">Un numero elevato di parametri implica un modello più flessibile, che può essere adatto per creare limiti di classificazione complessi, ma che possono anche essere più vulnerabili all'overfitting.</span><span class="sxs-lookup"><span data-stu-id="07d7a-108">A large number of parameters implies a more flexible model, which may be suitable to draw complicated classification boundaries but which may also be more susceptible to overfitting.</span></span>

- <span data-ttu-id="07d7a-109">Le attività di controllo tra qubits sono essenziali per l'acquisizione delle correlazioni tra le funzionalità Quantum.</span><span class="sxs-lookup"><span data-stu-id="07d7a-109">Entangling gates between qubits are essential to capture the correlations between the quantum features.</span></span>

## <a name="how-to-build-a-classifier-with-q"></a><span data-ttu-id="07d7a-110">Come compilare un classificatore con Q\#</span><span class="sxs-lookup"><span data-stu-id="07d7a-110">How to build a classifier with Q\#</span></span>

<span data-ttu-id="07d7a-111">Per compilare un classificatore, è possibile concatenare le rotazioni controllate da con parametri nel modello di circuito.</span><span class="sxs-lookup"><span data-stu-id="07d7a-111">To build a classifier we are going to concatenate parametrized controlled rotations in our circuit model.</span></span> <span data-ttu-id="07d7a-112">A tale scopo, è possibile usare il tipo [`ControlledRotation`](xref:Microsoft.Quantum.MachineLearning.ControlledRotation) definito nella libreria Quantum Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="07d7a-112">To do it we can use the type [`ControlledRotation`](xref:Microsoft.Quantum.MachineLearning.ControlledRotation) defined in the Quantum Machine Learning library.</span></span> <span data-ttu-id="07d7a-113">Questo tipo accetta quattro argomenti che determinano: l'indice della qubit di destinazione, la matrice di indici del controllo qubits, l'asse di rotazione e l'indice del parametro associato nella matrice di parametri che definiscono il modello.</span><span class="sxs-lookup"><span data-stu-id="07d7a-113">This type accepts four arguments that determine: the index of the target qubit, the array of indices of the control qubits, the axis of rotation, and index of the associated parameter in the array of parameters defining the model.</span></span>

<span data-ttu-id="07d7a-114">Viene ora visualizzato un esempio di classificatore.</span><span class="sxs-lookup"><span data-stu-id="07d7a-114">Let's see an example of a classifier.</span></span> <span data-ttu-id="07d7a-115">Nell' [esempio Half Moons](https://github.com/microsoft/Quantum/tree/main/samples/machine-learning/half-moons)è possibile trovare il classificatore seguente definito nel file `Training.qs` .</span><span class="sxs-lookup"><span data-stu-id="07d7a-115">In the [half-moons sample](https://github.com/microsoft/Quantum/tree/main/samples/machine-learning/half-moons), we can find the following classifier defined in the file `Training.qs`.</span></span>

```qsharp
    function ClassifierStructure() : ControlledRotation[] {
        return [
            ControlledRotation((0, new Int[0]), PauliX, 4),
            ControlledRotation((0, new Int[0]), PauliZ, 5),
            ControlledRotation((1, new Int[0]), PauliX, 6),
            ControlledRotation((1, new Int[0]), PauliZ, 7),
            ControlledRotation((0, [1]), PauliX, 0),
            ControlledRotation((1, [0]), PauliX, 1),
            ControlledRotation((1, new Int[0]), PauliZ, 2),
            ControlledRotation((1, new Int[0]), PauliX, 3)
        ];
    }
 ```

<span data-ttu-id="07d7a-116">Ciò che viene definito qui è una funzione che restituisce una matrice di `ControlledRotation` elementi, che insieme a una matrice di parametri e una distorsione definirà il [`SequentialModel`](xref:Microsoft.Quantum.MachineLearning.SequentialModel) .</span><span class="sxs-lookup"><span data-stu-id="07d7a-116">What we are defining here is a function that returns an array of `ControlledRotation` elements, that together with an array of parameters and a bias will define our [`SequentialModel`](xref:Microsoft.Quantum.MachineLearning.SequentialModel).</span></span> <span data-ttu-id="07d7a-117">Questo tipo è fondamentale nella libreria Quantum Machine Learning e definisce il classificatore.</span><span class="sxs-lookup"><span data-stu-id="07d7a-117">This type is fundamental in the Quantum Machine Learning library and defines the classifier.</span></span> <span data-ttu-id="07d7a-118">Il circuito definito nella funzione precedente fa parte di un classificatore in cui ogni campione del set di dati contiene due funzionalità.</span><span class="sxs-lookup"><span data-stu-id="07d7a-118">The circuit defined in the function above is part of a classifier in which each sample of the dataset contains two features.</span></span> <span data-ttu-id="07d7a-119">Quindi, sono necessari solo due qubits.</span><span class="sxs-lookup"><span data-stu-id="07d7a-119">Therefore we only need two qubits.</span></span> <span data-ttu-id="07d7a-120">La rappresentazione grafica del circuito è:</span><span class="sxs-lookup"><span data-stu-id="07d7a-120">The graphical representation of the circuit is:</span></span>

 ![Esempio di modello di circuito](~/media/circuit_model_1.PNG)

<span data-ttu-id="07d7a-122">Si noti che per impostazione predefinita, le operazioni della libreria Quantum Machine Learning misurano l'ultimo qubit del registro per stimare le probabilità di classificazione.</span><span class="sxs-lookup"><span data-stu-id="07d7a-122">Note that by default the operations of the Quantum Machine Learning library measure the last qubit of the register to estimate the classification probabilities.</span></span> <span data-ttu-id="07d7a-123">È necessario tenere presente questo fatto quando si progetta il circuito.</span><span class="sxs-lookup"><span data-stu-id="07d7a-123">You should keep in mind this fact when designing your circuit.</span></span>

## <a name="use-the-library-functions-to-write-layers-of-gates"></a><span data-ttu-id="07d7a-124">Usare le funzioni della libreria per scrivere livelli di controllo</span><span class="sxs-lookup"><span data-stu-id="07d7a-124">Use the library functions to write layers of gates</span></span>

<span data-ttu-id="07d7a-125">Si supponga di avere un set di dati con funzionalità di 784 per ogni istanza, ad esempio immagini di 28 × 28 pixel come il set di dati MNIST.</span><span class="sxs-lookup"><span data-stu-id="07d7a-125">Suppose we have a dataset with 784 features per instance, e.g. images of 28×28 pixels like the MNIST dataset.</span></span> <span data-ttu-id="07d7a-126">In questo caso, la larghezza del circuito diventa sufficientemente grande da consentire la scrittura manuale di ogni singolo controllo diventa un'attività possibile ma non pratica.</span><span class="sxs-lookup"><span data-stu-id="07d7a-126">In this case, the width of the circuit becomes large enough so that writing by hand each individual gate becomes a possible but impractical task.</span></span> <span data-ttu-id="07d7a-127">Questo è il motivo per cui la libreria Quantum Machine Learning fornisce un set di strumenti per generare automaticamente livelli di rotazioni con parametri.</span><span class="sxs-lookup"><span data-stu-id="07d7a-127">This is why the Quantum Machine Learning library provides a set of tools to automatically generate layers of parametrized rotations.</span></span> <span data-ttu-id="07d7a-128">Ad esempio, la funzione [`LocalRotationsLayer`](xref:Microsoft.Quantum.MachineLearning.LocalRotationsLayer) restituisce una matrice di rotazioni a singolo qubit non controllate lungo un asse specificato, con una rotazione per ogni qubit nel registro, ciascuna con parametri da un parametro di modello diverso.</span><span class="sxs-lookup"><span data-stu-id="07d7a-128">For instance, the function [`LocalRotationsLayer`](xref:Microsoft.Quantum.MachineLearning.LocalRotationsLayer) returns an array of uncontrolled single-qubit rotations along a given axis, with one rotation for each qubit in the register, each parametrized by a different model parameter.</span></span> <span data-ttu-id="07d7a-129">Ad esempio, `LocalRotationsLayer(4, X)` restituisce il seguente set di controlli:</span><span class="sxs-lookup"><span data-stu-id="07d7a-129">For example, `LocalRotationsLayer(4, X)` returns the following set of gates:</span></span>

 ![Livello di rotazione locale](~/media/local_rotations_layer.PNG)

<span data-ttu-id="07d7a-131">Si consiglia di esplorare il [riferimento API della libreria Quantum Machine Learning](xref:Microsoft.Quantum.MachineLearning) per individuare tutti gli strumenti disponibili per semplificare la progettazione del circuito.</span><span class="sxs-lookup"><span data-stu-id="07d7a-131">We recommend you explore the [API reference of the Quantum Machine Learning library](xref:Microsoft.Quantum.MachineLearning) to discover all the tools available to streamline the circuit design.</span></span>

## <a name="next-steps"></a><span data-ttu-id="07d7a-132">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="07d7a-132">Next steps</span></span>

 <span data-ttu-id="07d7a-133">Provare strutture diverse negli esempi forniti dagli esempi.</span><span class="sxs-lookup"><span data-stu-id="07d7a-133">Try different structures in the examples provided by the samples.</span></span> <span data-ttu-id="07d7a-134">Vengono visualizzate le modifiche apportate alle prestazioni del modello?</span><span class="sxs-lookup"><span data-stu-id="07d7a-134">Do you see any changes in the performance of the model?</span></span> <span data-ttu-id="07d7a-135">Nell'esercitazione successiva si apprenderà [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load) come caricare i set di impostazioni per provare ed esplorare le nuove architetture dei classificatori.</span><span class="sxs-lookup"><span data-stu-id="07d7a-135">In the next tutorial, [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load), you will learn how to load datasets to try and explore new architectures of classifiers.</span></span>

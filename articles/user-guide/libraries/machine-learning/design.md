---
title: Progettare un classificatore personalizzato con QDK
description: Informazioni sui concetti di base per la progettazione di modelli di circuito per il classificatore incentrato sul circuito Quantum.
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/17/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.design
ms.openlocfilehash: b304b9d1a15f164f4dfe758aaed31b7b2369b18c
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276042"
---
# <a name="design-your-own-classifier"></a><span data-ttu-id="21e80-103">Progettare un classificatore personalizzato</span><span class="sxs-lookup"><span data-stu-id="21e80-103">Design your own classifier</span></span>

<span data-ttu-id="21e80-104">In questa guida si apprenderanno i concetti di base della progettazione dei modelli di circuito per il classificatore incentrato sul circuito Quantum.</span><span class="sxs-lookup"><span data-stu-id="21e80-104">In this guide you will learn the basic concepts behind the design of circuit models for the quantum circuit centric classifier.</span></span>

<span data-ttu-id="21e80-105">Come nell'apprendimento avanzato classico, non esiste alcuna regola generale per la scelta di un'architettura specifica.</span><span class="sxs-lookup"><span data-stu-id="21e80-105">As in classical deep learning, there is no general rule for choosing a specific architecture.</span></span> <span data-ttu-id="21e80-106">A seconda del problema, alcune architetture offriranno prestazioni migliori rispetto ad altre.</span><span class="sxs-lookup"><span data-stu-id="21e80-106">Depending on the problem some architectures will perform better than others.</span></span> <span data-ttu-id="21e80-107">Tuttavia, esistono alcuni concetti che possono risultare utili durante la progettazione del circuito:</span><span class="sxs-lookup"><span data-stu-id="21e80-107">But, there are some concepts that might be useful when designing the circuit:</span></span>

- <span data-ttu-id="21e80-108">Un numero elevato di parametri implica un modello più flessibile, che può essere adatto per creare limiti di classificazione complessi, ma che possono anche essere più vulnerabili all'overfitting.</span><span class="sxs-lookup"><span data-stu-id="21e80-108">A large number of parameters implies a more flexible model, which may be suitable to draw complicated classification boundaries but which may also be more susceptible to overfitting.</span></span>

- <span data-ttu-id="21e80-109">Le attività di controllo tra qubits sono essenziali per l'acquisizione delle correlazioni tra le funzionalità Quantum.</span><span class="sxs-lookup"><span data-stu-id="21e80-109">Entangling gates between qubits are essential to capture the correlations between the quantum features.</span></span>

## <a name="how-to-build-a-classifier-with-q"></a><span data-ttu-id="21e80-110">Come compilare un classificatore con Q\#</span><span class="sxs-lookup"><span data-stu-id="21e80-110">How to build a classifier with Q\#</span></span>

<span data-ttu-id="21e80-111">Per compilare un classificatore, è possibile concatenare le rotazioni controllate da con parametri nel modello di circuito.</span><span class="sxs-lookup"><span data-stu-id="21e80-111">To build a classifier we are going to concatenate parametrized controlled rotations in our circuit model.</span></span> <span data-ttu-id="21e80-112">A tale scopo, è possibile usare il tipo [`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation) definito nella libreria Quantum Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="21e80-112">To do it we can use the type [`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation) defined in the Quantum Machine Learning library.</span></span> <span data-ttu-id="21e80-113">Questo tipo accetta quattro argomenti che determinano: l'indice della qubit di destinazione, la matrice di indici del controllo qubits, l'asse di rotazione e l'indice del parametro associato nella matrice di parametri che definiscono il modello.</span><span class="sxs-lookup"><span data-stu-id="21e80-113">This type accepts four arguments that determine: the index of the target qubit, the array of indices of the control qubits, the axis of rotation, and index of the associated parameter in the array of parameters defining the model.</span></span>

<span data-ttu-id="21e80-114">Viene ora visualizzato un esempio di classificatore.</span><span class="sxs-lookup"><span data-stu-id="21e80-114">Let's see an example of a classifier.</span></span> <span data-ttu-id="21e80-115">Nell' [esempio Half Moons](https://github.com/microsoft/Quantum/tree/master/samples/machine-learning/half-moons)è possibile trovare il classificatore seguente definito nel file `Training.qs` .</span><span class="sxs-lookup"><span data-stu-id="21e80-115">In the [half-moons sample](https://github.com/microsoft/Quantum/tree/master/samples/machine-learning/half-moons), we can find the following classifier defined in the file `Training.qs`.</span></span>

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

<span data-ttu-id="21e80-116">Ciò che viene definito qui è una funzione che restituisce una matrice di `ControlledRotation` elementi, che insieme a una matrice di parametri e una distorsione definirà il [`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel) .</span><span class="sxs-lookup"><span data-stu-id="21e80-116">What we are defining here is a function that returns an array of `ControlledRotation` elements, that together with an array of parameters and a bias will define our [`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel).</span></span> <span data-ttu-id="21e80-117">Questo tipo è fondamentale nella libreria Quantum Machine Learning e definisce il classificatore.</span><span class="sxs-lookup"><span data-stu-id="21e80-117">This type is fundamental in the Quantum Machine Learning library and defines the classifier.</span></span> <span data-ttu-id="21e80-118">Il circuito definito nella funzione precedente fa parte di un classificatore in cui ogni campione del set di dati contiene due funzionalità.</span><span class="sxs-lookup"><span data-stu-id="21e80-118">The circuit defined in the function above is part of a classifier in which each sample of the dataset contains two features.</span></span> <span data-ttu-id="21e80-119">Quindi, sono necessari solo due qubits.</span><span class="sxs-lookup"><span data-stu-id="21e80-119">Therefore we only need two qubits.</span></span> <span data-ttu-id="21e80-120">La rappresentazione grafica del circuito è:</span><span class="sxs-lookup"><span data-stu-id="21e80-120">The graphical representation of the circuit is:</span></span>

 ![Esempio di modello di circuito](~/media/circuit_model_1.PNG)

## <a name="use-the-library-functions-to-write-layers-of-gates"></a><span data-ttu-id="21e80-122">Usare le funzioni della libreria per scrivere livelli di controllo</span><span class="sxs-lookup"><span data-stu-id="21e80-122">Use the library functions to write layers of gates</span></span>

<span data-ttu-id="21e80-123">Si supponga di avere un set di dati con funzionalità di 784 per ogni istanza, ad esempio immagini di 28 × 28 pixel come il set di dati MNIST.</span><span class="sxs-lookup"><span data-stu-id="21e80-123">Suppose we have a dataset with 784 features per instance, e.g. images of 28×28 pixels like the MNIST dataset.</span></span> <span data-ttu-id="21e80-124">In questo caso, la larghezza del circuito diventa sufficientemente grande da consentire la scrittura manuale di ogni singolo controllo diventa un'attività possibile ma non pratica.</span><span class="sxs-lookup"><span data-stu-id="21e80-124">In this case, the width of the circuit becomes large enough so that writing by hand each individual gate becomes a possible but impractical task.</span></span> <span data-ttu-id="21e80-125">Questo è il motivo per cui la libreria Quantum Machine Learning fornisce un set di strumenti per generare automaticamente livelli di rotazioni con parametri.</span><span class="sxs-lookup"><span data-stu-id="21e80-125">This is why the Quantum Machine Learning library provides a set of tools to automatically generate layers of parametrized rotations.</span></span> <span data-ttu-id="21e80-126">Ad esempio, la funzione [`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer) restituisce una matrice di rotazioni a singolo qubit non controllate lungo un asse specificato, con una rotazione per ogni qubit nel registro, ciascuna con parametri da un parametro di modello diverso.</span><span class="sxs-lookup"><span data-stu-id="21e80-126">For instance, the function [`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer) returns an array of uncontrolled single-qubit rotations along a given axis, with one rotation for each qubit in the register, each parametrized by a different model parameter.</span></span> <span data-ttu-id="21e80-127">Ad esempio, `LocalRotationsLayer(4, X)` restituisce il seguente set di controlli:</span><span class="sxs-lookup"><span data-stu-id="21e80-127">For example, `LocalRotationsLayer(4, X)` returns the following set of gates:</span></span>

 ![Livello di rotazione locale](~/media/local_rotations_layer.PNG)

<span data-ttu-id="21e80-129">Si consiglia di esplorare il [riferimento API della libreria Quantum Machine Learning](xref:microsoft.quantum.machinelearning) per individuare tutti gli strumenti disponibili per semplificare la progettazione del circuito.</span><span class="sxs-lookup"><span data-stu-id="21e80-129">We recommend you explore the [API reference of the Quantum Machine Learning library](xref:microsoft.quantum.machinelearning) to discover all the tools available to streamline the circuit design.</span></span>

## <a name="next-steps"></a><span data-ttu-id="21e80-130">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="21e80-130">Next steps</span></span>

 <span data-ttu-id="21e80-131">Provare strutture diverse negli esempi forniti dagli esempi.</span><span class="sxs-lookup"><span data-stu-id="21e80-131">Try different structures in the examples provided by the samples.</span></span> <span data-ttu-id="21e80-132">Vengono visualizzate le modifiche apportate alle prestazioni del modello?</span><span class="sxs-lookup"><span data-stu-id="21e80-132">Do you see any changes in the performance of the model?</span></span> <span data-ttu-id="21e80-133">Nell'esercitazione successiva si apprenderà [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load) come caricare i set di impostazioni per provare ed esplorare le nuove architetture dei classificatori.</span><span class="sxs-lookup"><span data-stu-id="21e80-133">In the next tutorial, [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load), you will learn how to load datasets to try and explore new architectures of classifiers.</span></span>

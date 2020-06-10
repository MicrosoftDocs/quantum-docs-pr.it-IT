---
title: Progettare un classificatore personalizzato con QDK
description: Informazioni sui concetti di base per la progettazione di modelli di circuito per il classificatore incentrato sul circuito Quantum.
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/17/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.design
ms.openlocfilehash: b304b9d1a15f164f4dfe758aaed31b7b2369b18c
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630256"
---
# <a name="design-your-own-classifier"></a>Progettare un classificatore personalizzato

In questa guida si apprenderanno i concetti di base della progettazione dei modelli di circuito per il classificatore incentrato sul circuito Quantum.

Come nell'apprendimento avanzato classico, non esiste alcuna regola generale per la scelta di un'architettura specifica. A seconda del problema, alcune architetture offriranno prestazioni migliori rispetto ad altre. Tuttavia, esistono alcuni concetti che possono risultare utili durante la progettazione del circuito:

- Un numero elevato di parametri implica un modello più flessibile, che può essere adatto per creare limiti di classificazione complessi, ma che possono anche essere più vulnerabili all'overfitting.

- Le attività di controllo tra qubits sono essenziali per l'acquisizione delle correlazioni tra le funzionalità Quantum.

## <a name="how-to-build-a-classifier-with-q"></a>Come compilare un classificatore con Q\#

Per compilare un classificatore, è possibile concatenare le rotazioni controllate da con parametri nel modello di circuito. A tale scopo, è possibile usare il tipo [`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation) definito nella libreria Quantum Machine Learning. Questo tipo accetta quattro argomenti che determinano: l'indice della qubit di destinazione, la matrice di indici del controllo qubits, l'asse di rotazione e l'indice del parametro associato nella matrice di parametri che definiscono il modello.

Viene ora visualizzato un esempio di classificatore. Nell' [esempio Half Moons](https://github.com/microsoft/Quantum/tree/master/samples/machine-learning/half-moons)è possibile trovare il classificatore seguente definito nel file `Training.qs` .

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

Ciò che viene definito qui è una funzione che restituisce una matrice di `ControlledRotation` elementi, che insieme a una matrice di parametri e una distorsione definirà il [`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel) . Questo tipo è fondamentale nella libreria Quantum Machine Learning e definisce il classificatore. Il circuito definito nella funzione precedente fa parte di un classificatore in cui ogni campione del set di dati contiene due funzionalità. Quindi, sono necessari solo due qubits. La rappresentazione grafica del circuito è:

 ![Esempio di modello di circuito](~/media/circuit_model_1.PNG)

## <a name="use-the-library-functions-to-write-layers-of-gates"></a>Usare le funzioni della libreria per scrivere livelli di controllo

Si supponga di avere un set di dati con funzionalità di 784 per ogni istanza, ad esempio immagini di 28 × 28 pixel come il set di dati MNIST. In questo caso, la larghezza del circuito diventa sufficientemente grande da consentire la scrittura manuale di ogni singolo controllo diventa un'attività possibile ma non pratica. Questo è il motivo per cui la libreria Quantum Machine Learning fornisce un set di strumenti per generare automaticamente livelli di rotazioni con parametri. Ad esempio, la funzione [`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer) restituisce una matrice di rotazioni a singolo qubit non controllate lungo un asse specificato, con una rotazione per ogni qubit nel registro, ciascuna con parametri da un parametro di modello diverso. Ad esempio, `LocalRotationsLayer(4, X)` restituisce il seguente set di controlli:

 ![Livello di rotazione locale](~/media/local_rotations_layer.PNG)

Si consiglia di esplorare il [riferimento API della libreria Quantum Machine Learning](xref:microsoft.quantum.machinelearning) per individuare tutti gli strumenti disponibili per semplificare la progettazione del circuito.

## <a name="next-steps"></a>Passaggi successivi

 Provare strutture diverse negli esempi forniti dagli esempi. Vengono visualizzate le modifiche apportate alle prestazioni del modello? Nell'esercitazione successiva si apprenderà [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load) come caricare i set di impostazioni per provare ed esplorare le nuove architetture dei classificatori.

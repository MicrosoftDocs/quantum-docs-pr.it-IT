---
uid: Microsoft.Quantum.Characterization.EstimateFrequency
title: Operazione EstimateFrequency
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequency
qsharp.summary: Given a preparation and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 30b21a8e86eb5a4dd8dd8207dbdc6a0970308319
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216252"
---
# <a name="estimatefrequency-operation"></a>Operazione EstimateFrequency

Spazio dei nomi: [Microsoft. Quantum. characteration](xref:Microsoft.Quantum.Characterization)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Data una preparazione e una misurazione, stima la frequenza con cui la misurazione ha esito positivo (restituisce `Zero` ) eseguendo un determinato numero di prove.

```qsharp
operation EstimateFrequency (preparation : (Qubit[] => Unit), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Input

### <a name="preparation--qubit--unit"></a>preparazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unità](xref:microsoft.quantum.lang-ref.unit)> 

Un'operazione $P $ che prepara un dato stato $ \rho $ al relativo registro di input.


### <a name="measurement--qubit--__invalidresult__"></a>misurazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __non <Result> valido__ 

Operazione $M $ che rappresenta la misura di interesse.


### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Numero di qubits in cui ogni azione viene preparata e misurata.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Il numero di volte in cui deve essere eseguita la misurazione per stimare la frequenza di interesse.



## <a name="output--double"></a>Output: [Double](xref:microsoft.quantum.lang-ref.double)

Una stima $ \hat{p} $ della frequenza con cui $M (P (\ket{00 \cdots 0} \bra{00 \cdots 0})) $ restituisce `Zero` , ottenuta utilizzando lo strumento di stima binomiale senza distorsione $ \hat{p} = n \_ {\uparrow}/n \_ {\Text{Measurements}} $, dove $n \_ {\uparrow} $ indica il numero di `Zero` risultati osservati.

Questa operazione è particolarmente importante nei computer di destinazione che rispettano le limitazioni fisiche, in modo che non sia possibile misurare le probabilità.
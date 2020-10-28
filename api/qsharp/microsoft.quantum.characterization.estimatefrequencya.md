---
uid: Microsoft.Quantum.Characterization.EstimateFrequencyA
title: Operazione EstimateFrequencyA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequencyA
qsharp.summary: Given a preparation that is adjointable and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 88f0a237975c158bffcc015f79d2134b210ce83b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715067"
---
# <a name="estimatefrequencya-operation"></a>Operazione EstimateFrequencyA

Spazio dei nomi: [Microsoft. Quantum. characteration](xref:Microsoft.Quantum.Characterization)

Pacchetto [](https://nuget.org/packages/)


Data una preparazione che è adjointable e la misura, stima la frequenza con cui la misurazione ha esito positivo (restituisce `Zero` ) eseguendo un determinato numero di prove.

```qsharp
operation EstimateFrequencyA (preparation : (Qubit[] => Unit is Adj), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Input

### <a name="preparation--qubit--unit-adj"></a>preparazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => ADJ [unità](xref:microsoft.quantum.lang-ref.unit)

Un'operazione adjointable $P $ che prepara un dato stato $ \rho $ al relativo registro di input.


### <a name="measurement--qubit--__invalidresult__"></a>misurazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __non <Result> valido__ 

Operazione $M $ che rappresenta la misura di interesse.


### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Numero di qubits in cui ogni azione viene preparata e misurata.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Il numero di volte in cui deve essere eseguita la misurazione per stimare la frequenza di interesse.



## <a name="output--double"></a>Output: [Double](xref:microsoft.quantum.lang-ref.double)

Una stima $ \hat{p} $ della frequenza con cui $M (P (\ket{00 \cdots 0} \bra{00 \cdots 0})) $ restituisce `Zero` , ottenuta utilizzando lo strumento di stima binomiale senza distorsione $ \hat{p} = n \_ {\uparrow}/n \_ {\Text{Measurements}} $, dove $n \_ {\uparrow} $ indica il numero di `Zero` risultati osservati.

## <a name="remarks"></a>Commenti

Per le operazioni adjointable, è possibile ipotizzare alcuni presupposti, ad esempio la chiamata dell'operazione, per preparare il qubits esattamente allo stesso stato, che consente ai computer di destinazione di apportare alcune ottimizzazioni delle prestazioni.
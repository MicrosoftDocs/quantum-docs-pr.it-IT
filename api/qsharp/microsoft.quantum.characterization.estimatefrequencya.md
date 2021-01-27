---
uid: Microsoft.Quantum.Characterization.EstimateFrequencyA
title: Operazione EstimateFrequencyA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequencyA
qsharp.summary: Given a preparation that is adjointable and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 6cca8dff70283e0d69441db8a5b31fb5bfb3082a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839922"
---
# <a name="estimatefrequencya-operation"></a>Operazione EstimateFrequencyA

Spazio dei nomi: [Microsoft. Quantum. characteration](xref:Microsoft.Quantum.Characterization)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Data una preparazione che è adjointable e la misura, stima la frequenza con cui la misurazione ha esito positivo (restituisce `Zero` ) eseguendo un determinato numero di prove.

```qsharp
operation EstimateFrequencyA (preparation : (Qubit[] => Unit is Adj), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Input

### <a name="preparation--qubit--unit--is-adj"></a>preparazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ

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
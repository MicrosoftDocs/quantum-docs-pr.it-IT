---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlaceCompBasis
title: Operazione AssertOperationsEqualInPlaceCompBasis
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlaceCompBasis
qsharp.summary: Checks if the operation `givenU` is equal to the operation `expectedU` on the given input size  by checking the action of the operations only on the vectors from the computational basis. This is a necessary, but not sufficient, condition for the equality of two unitaries.
ms.openlocfilehash: 3275680f86ca2a178c7f044b97d226fe41c3186c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712967"
---
# <a name="assertoperationsequalinplacecompbasis-operation"></a>Operazione AssertOperationsEqualInPlaceCompBasis

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto [](https://nuget.org/packages/)


Verifica se l'operazione `givenU` è uguale all'operazione `expectedU` sulla dimensione di input specificata controllando l'azione delle operazioni solo sui vettori dalla base computazionale.
Si tratta di una condizione necessaria, ma non sufficiente, per l'uguaglianza di due unitaries.

```qsharp
operation AssertOperationsEqualInPlaceCompBasis (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Input

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Il numero di qubits $n $ `givenU` su cui operano le operazioni e `expectedU` .


### <a name="givenu--qubit--unit"></a>dato: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unità](xref:microsoft.quantum.lang-ref.unit)> 

Operazione su $n $ qubits da controllare.


### <a name="expectedu--qubit--unit-adj"></a>previsto: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ

Operazione di riferimento su $n $ qubits da `givenU` confrontare con.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)


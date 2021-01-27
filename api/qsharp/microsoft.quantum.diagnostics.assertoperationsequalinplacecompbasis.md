---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlaceCompBasis
title: Operazione AssertOperationsEqualInPlaceCompBasis
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlaceCompBasis
qsharp.summary: Checks if the operation `givenU` is equal to the operation `expectedU` on the given input size  by checking the action of the operations only on the vectors from the computational basis. This is a necessary, but not sufficient, condition for the equality of two unitaries.
ms.openlocfilehash: f9d3aaf7e774cf2495ca69382db2470d1d0fa7b5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830490"
---
# <a name="assertoperationsequalinplacecompbasis-operation"></a>Operazione AssertOperationsEqualInPlaceCompBasis

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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


### <a name="expectedu--qubit--unit--is-adj"></a>previsto: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ

Operazione di riferimento su $n $ qubits da `givenU` confrontare con.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)


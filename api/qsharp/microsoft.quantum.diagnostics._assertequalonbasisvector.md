---
uid: Microsoft.Quantum.Diagnostics._assertEqualOnBasisVector
title: operazione _assertEqualOnBasisVector
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _assertEqualOnBasisVector
qsharp.summary: Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same. The basis state is described by `basis` parameter. See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.
ms.openlocfilehash: 01b6d5aede102e47df86ea70d071d81eba1ade6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713152"
---
# <a name="_assertequalonbasisvector-operation"></a>operazione _assertEqualOnBasisVector

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto [](https://nuget.org/packages/)


Controlla se il risultato dell'applicazione di due operazioni `givenU` e `expectedU` a uno stato di base è lo stesso. Lo stato di base è descritto dal `basis` parametro.
<xref:microsoft.quantum.extensions.fliptobasis>Per ulteriori informazioni su questa descrizione, vedere la funzione.

```qsharp
operation _assertEqualOnBasisVector (basis : Int[], givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Input

### <a name="basis--int"></a>base: [int](xref:microsoft.quantum.lang-ref.int)[]

Stato di base specificato da un ID di stato di base a qubit singolo (0 <= ID <= 3) per ogni $n $ qubits.


### <a name="givenu--qubit--unit"></a>dato: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unità](xref:microsoft.quantum.lang-ref.unit)> 

Operazione su $n $ qubits da controllare.


### <a name="expectedu--qubit--unit-adj"></a>previsto: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ

Operazione di riferimento su $n $ qubits in base a cui deve essere confrontato.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)


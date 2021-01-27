---
uid: Microsoft.Quantum.Diagnostics._assertEqualOnBasisVector
title: operazione _assertEqualOnBasisVector
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _assertEqualOnBasisVector
qsharp.summary: Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same. The basis state is described by `basis` parameter. See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.
ms.openlocfilehash: 041fecfa27ae5bd17fa8fdc89ce964f985f6124b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853591"
---
# <a name="_assertequalonbasisvector-operation"></a>operazione _assertEqualOnBasisVector

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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


### <a name="expectedu--qubit--unit--is-adj"></a>previsto: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ

Operazione di riferimento su $n $ qubits in base a cui deve essere confrontato.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)


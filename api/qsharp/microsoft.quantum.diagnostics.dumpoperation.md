---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: Operazione DumpOperation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: 444d42e2440b30b3bdf50d55a399568bed063222
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712858"
---
# <a name="dumpoperation-operation"></a>Operazione DumpOperation

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto [](https://nuget.org/packages/)


Data un'operazione, Visualizza la diagnostica sull'operazione resa disponibile dalla destinazione di esecuzione corrente.

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Input

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Numero di qubits su cui agisce l'operazione specificata.


### <a name="op--qubit--unit-adj"></a>op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => ADJ [unità](xref:microsoft.quantum.lang-ref.unit)

Operazione da diagnosticare.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

La chiamata a questa operazione non ha alcun effetto osservabile da Q #. La diagnostica esatta visualizzata, se presente, dipende dalla destinazione di esecuzione corrente e dall'ambiente dell'editor.
Ad esempio, se usato nel simulatore Quantum a stato completo, viene visualizzata una matrice unitaria usata per rappresentare `op` .

Si noti che, quando vengono eseguiti su simulatori che ammettono un'ambiguità di una fase globale (ad esempio, il simulatore di stato completo), le rappresentazioni restituite possono variare fino a una fase globale.

Analogamente, l'ordine delle rappresentazioni di righe e colonne della matrice può variare in base alle convenzioni usate da ogni simulatore che supporta questa operazione.
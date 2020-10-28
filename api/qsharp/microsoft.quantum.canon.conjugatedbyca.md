---
uid: Microsoft.Quantum.Canon.ConjugatedByCA
title: ConjugatedByCA (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByCA
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: df29bcf555026bceb13d6896db12e13671a49b9f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716453"
---
# <a name="conjugatedbyca-function"></a>ConjugatedByCA (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Date le operazioni esterne e interne, restituisce una nuova operazione che coniuga l'operazione interna all'operazione esterna.

```qsharp
function ConjugatedByCA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj + Ctl)) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a>Input

### <a name="outeroperation--t--unit-adj"></a>outerOperation:' t => ADJ [unità](xref:microsoft.quantum.lang-ref.unit)

L'operazione $U $ da usare per coniugare $V $. Si noti che l'operazione esterna $U $ deve essere adjointable, ma non deve essere controllabile.


### <a name="inneroperation--t--unit-adj--ctl"></a>innerOperation:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Operazione $V $ coniugata.



## <a name="output--t--unit-adj--ctl"></a>Output:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Nuova operazione la cui azione è rappresentata dall'unità $U ^ {\dagger} V U $.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di destinazione in cui agiscono le operazioni interne ed esterne.

## <a name="remarks"></a>Commenti

L'operazione esterna viene sempre considerata adjointable, ma non deve essere controllabile affinché l'operazione combinata sia controllabile.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. ConjugatedByA](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [Microsoft. Quantum. Canon. ConjugatedByC](xref:Microsoft.Quantum.Canon.ConjugatedByC)
- [Microsoft. Quantum. Canon. ConjugatedByCA](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [Microsoft. Quantum. Canon. ApplyWith](xref:Microsoft.Quantum.Canon.ApplyWith)
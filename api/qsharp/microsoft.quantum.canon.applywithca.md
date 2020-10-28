---
uid: Microsoft.Quantum.Canon.ApplyWithCA
title: Operazione ApplyWithCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithCA
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: abc62791416e78c1b2937a226327b71da8b8e288
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716887"
---
# <a name="applywithca-operation"></a>Operazione ApplyWithCA

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Date due operazioni, applica una come coniugata con l'altra.

```qsharp
operation ApplyWithCA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj + Ctl), target : 'T) : Unit
```


## <a name="description"></a>Descrizione

Date due operazioni, rispettivamente descritte da operatori unitari $U $ e $V $, le applicano nella sequenza $U ^ {\dagger} V U $. Questa operazione implementa quindi l'operatore unitario fornito da $V $ coniugato con $U $.

## <a name="input"></a>Input

### <a name="outeroperation--t--unit-adj"></a>outerOperation:' t => ADJ [unità](xref:microsoft.quantum.lang-ref.unit)

L'operazione $U $ da usare per coniugare $V $. Si noti che l'operazione esterna $U $ deve essere adjointable, ma non deve essere controllabile.


### <a name="inneroperation--t--unit-adj--ctl"></a>innerOperation:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Operazione $V $ coniugata.


### <a name="target--t"></a>destinazione:' t

Input da fornire alle operazioni esterne e interne.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Destinazione in cui agiscono le operazioni interne ed esterne.

## <a name="remarks"></a>Commenti

L'operazione esterna viene sempre considerata adjointable, ma non deve essere controllabile affinché l'operazione combinata sia controllabile.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. ApplyWith](xref:Microsoft.Quantum.Canon.ApplyWith)
- [Microsoft. Quantum. Canon. ApplyWithA](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [Microsoft. Quantum. Canon. ApplyWithC](xref:Microsoft.Quantum.Canon.ApplyWithC)
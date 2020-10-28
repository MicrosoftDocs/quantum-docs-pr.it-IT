---
uid: Microsoft.Quantum.Canon.ApplyWithA
title: Operazione ApplyWithA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithA
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: f1ff31da53952931426d358cbedad44a50d87f5e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716929"
---
# <a name="applywitha-operation"></a>Operazione ApplyWithA

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Date due operazioni, applica una come coniugata con l'altra.

```qsharp
operation ApplyWithA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj), target : 'T) : Unit
```


## <a name="description"></a>Descrizione

Date due operazioni, rispettivamente descritte da operatori unitari $U $ e $V $, le applicano nella sequenza $U ^ {\dagger} V U $. Questa operazione implementa quindi l'operatore unitario fornito da $V $ coniugato con $U $.

## <a name="input"></a>Input

### <a name="outeroperation--t--unit-adj"></a>outerOperation:' t => ADJ [unità](xref:microsoft.quantum.lang-ref.unit)

L'operazione $U $ da usare per coniugare $V $. Si noti che l'operazione esterna $U $ deve essere adjointable, ma non deve essere controllabile.


### <a name="inneroperation--t--unit-adj"></a>innerOperation:' t => ADJ [unità](xref:microsoft.quantum.lang-ref.unit)

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
- [Microsoft. Quantum. Canon. ApplyWithC](xref:Microsoft.Quantum.Canon.ApplyWithC)
- [Microsoft. Quantum. Canon. ApplyWithCA](xref:Microsoft.Quantum.Canon.ApplyWithCA)
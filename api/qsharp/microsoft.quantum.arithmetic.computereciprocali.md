---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalI
title: Operazione ComputeReciprocalI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalI
qsharp.summary: Computes the reciprocal 1/x for an unsigned integer x using integer division. The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.
ms.openlocfilehash: b99e816ed69af6e6d1758442d6f95c5ab0e5c07a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721227"
---
# <a name="computereciprocali-operation"></a>Operazione ComputeReciprocalI

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Calcola il reciproco 1/x per un Unsigned Integer x usando la divisione di interi. Il risultato, interpretato come un numero intero, sarà `floor(2^(2*n-1) / x)` .

```qsharp
operation ComputeReciprocalI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>Input

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Unsigned Integer a n bit


### <a name="result--littleendian"></a>risultato: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

l'output a 2n bit deve essere inizialmente in $ \ket {0} $.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Per l'input x = 0, l'output sarà tutti quelli.
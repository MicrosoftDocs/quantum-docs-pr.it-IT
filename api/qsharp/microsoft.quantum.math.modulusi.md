---
uid: Microsoft.Quantum.Math.ModulusI
title: Funzione moduloi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 7bad044db9e2229c85cb3909dc4802bceaee6382
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847298"
---
# <a name="modulusi-function"></a>Funzione moduloi

Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Calcola il residuo canonico del `value` modulo `modulus` .

```qsharp
function ModulusI (value : Int, modulus : Int) : Int
```


## <a name="input"></a>Input

### <a name="value--int"></a>valore: [int](xref:microsoft.quantum.lang-ref.int)

Valore di cui viene calcolato il residuo


### <a name="modulus--int"></a>modulo: [int](xref:microsoft.quantum.lang-ref.int)

Il modulo in base al quale vengono presi i residui deve essere positivo



## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)

Integer $r $ tra 0 e `modulus - 1` così `value - r` divisibile per modulo

## <a name="remarks"></a>Commenti

Questa funzione si comporta in modo diverso a seconda del comportamento dell'operatore `%` in C# e Q # come nel risultato è sempre un numero intero non negativo compreso tra 0 e `modulus - 1` , anche se il valore è negativo.
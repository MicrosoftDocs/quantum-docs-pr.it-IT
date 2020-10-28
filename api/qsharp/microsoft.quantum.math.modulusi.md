---
uid: Microsoft.Quantum.Math.ModulusI
title: Funzione moduloi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 3f698a00b2c8d94b7cb3cca4f1721c659918f4a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723093"
---
# <a name="modulusi-function"></a>Funzione moduloi

Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pacchetto [](https://nuget.org/packages/)


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

Questa funzione si comporta in modo diverso a seconda del comportamento dell'operatore `%` in C# e Q # come nel risultato è sempre un numero intero positivo compreso tra 0 e `modulus - 1` , anche se il valore è negativo.
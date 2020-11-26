---
uid: Microsoft.Quantum.Math.ModulusL
title: Funzione modulo
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 5c9a8ceceac5d2cdac6b82f7f74a85e9443382a2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194934"
---
# <a name="modulusl-function"></a>Funzione modulo

Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Calcola il residuo canonico del `value` modulo `modulus` .

```qsharp
function ModulusL (value : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a>Input

### <a name="value--bigint"></a>valore: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Valore di cui viene calcolato il residuo


### <a name="modulus--bigint"></a>modulo: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Il modulo in base al quale vengono presi i residui deve essere positivo



## <a name="output--bigint"></a>Output: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Integer $r $ tra 0 e `modulus - 1` così `value - r` divisibile per modulo

## <a name="remarks"></a>Osservazioni

Questa funzione si comporta in modo diverso a seconda del comportamento dell'operatore `%` in C# e Q # come nel risultato è sempre un numero intero positivo compreso tra 0 e `modulus - 1` , anche se il valore è negativo.
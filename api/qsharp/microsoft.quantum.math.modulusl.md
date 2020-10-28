---
uid: Microsoft.Quantum.Math.ModulusL
title: Funzione modulo
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: e7e692059051fde295634c37892ec54e2cf1b095
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725098"
---
# <a name="modulusl-function"></a>Funzione modulo

Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pacchetto [](https://nuget.org/packages/)


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

## <a name="remarks"></a>Commenti

Questa funzione si comporta in modo diverso a seconda del comportamento dell'operatore `%` in C# e Q # come nel risultato è sempre un numero intero positivo compreso tra 0 e `modulus - 1` , anche se il valore è negativo.
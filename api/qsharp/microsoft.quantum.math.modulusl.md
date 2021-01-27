---
uid: Microsoft.Quantum.Math.ModulusL
title: Funzione modulo
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 6be2edb052cf55f8e8465c76b5dcadeb61ff11ea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842734"
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

## <a name="remarks"></a>Commenti

Questa funzione si comporta in modo diverso a seconda del comportamento dell'operatore `%` in C# e Q # come nel risultato è sempre un numero intero non negativo compreso tra 0 e `modulus - 1` , anche se il valore è negativo.
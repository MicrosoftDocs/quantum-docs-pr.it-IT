---
uid: Microsoft.Quantum.Math.InverseModI
title: InverseModI (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModI
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: 217ce4cd113ecbc6a06ed83c6c1dcb7baa46387d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195376"
---
# <a name="inversemodi-function"></a>InverseModI (funzione)

Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce $b $ in modo che $a \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $.

```qsharp
function InverseModI (a : Int, modulus : Int) : Int
```


## <a name="input"></a>Input

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

Numero da invertire


### <a name="modulus--int"></a>modulo: [int](xref:microsoft.quantum.lang-ref.int)

Modulo in base al quale vengono invertiti i numeri



## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)

Integer $b $ tale che $a \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $.
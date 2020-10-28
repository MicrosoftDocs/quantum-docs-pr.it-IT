---
uid: Microsoft.Quantum.Math.InverseModI
title: InverseModI (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModI
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: 6efc9da5f5ebb64065a90e749daa629dc2dce9cf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723639"
---
# <a name="inversemodi-function"></a>InverseModI (funzione)

Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pacchetto [](https://nuget.org/packages/)


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
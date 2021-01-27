---
uid: Microsoft.Quantum.Bitwise.Xor
title: XOR (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: Xor
qsharp.summary: Returns the bitwise exclusive-OR (XOR) of two integers. This performs the same computation as the built-in `^^^` operator.
ms.openlocfilehash: ac31ba973ff06424dbd16168dac14a79b2691b3f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842076"
---
# <a name="xor-function"></a>XOR (funzione)

Spazio dei nomi: [Microsoft. Quantum. bit per bit](xref:Microsoft.Quantum.Bitwise)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Restituisce l'OR esclusivo bit per bit (XOR) di due Integer.
Esegue lo stesso calcolo dell' `^^^` operatore incorporato.

```qsharp
function Xor (a : Int, b : Int) : Int
```


## <a name="input"></a>Input

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)




### <a name="b--int"></a>b: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)



## <a name="example"></a>Esempio

```qsharp
let a = 248;       //                 11111000₂
let b = 63;        //                 00111111₂
let x = Xor(a, b); // x : Int = 199 = 11000111₂.
```

## <a name="remarks"></a>Commenti

Per ulteriori informazioni, vedere l' [operatore C# ^](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/xor-operator) .
---
uid: Microsoft.Quantum.Bitwise.Parity
title: Funzione di parità
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: Parity
qsharp.summary: Returns the bitwise PARITY of an integer (1 if its binary representation contains odd number of ones and 0 otherwise).
ms.openlocfilehash: b34ef36b0336ec1dea7fdbd878c6d695b38d623e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842137"
---
# <a name="parity-function"></a>Funzione di parità

Spazio dei nomi: [Microsoft. Quantum. bit per bit](xref:Microsoft.Quantum.Bitwise)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Restituisce la parità bit per bit di un Integer (1 se la relativa rappresentazione binaria contiene un numero dispari di quelli e 0 in caso contrario).

```qsharp
function Parity (a : Int) : Int
```


## <a name="input"></a>Input

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)



## <a name="example"></a>Esempio

```qsharp
let a = 248;
let x = Parity(a); // x : Int = 1.
```
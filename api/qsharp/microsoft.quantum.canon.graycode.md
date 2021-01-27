---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: 0a9a19685f0511c44942df7d0bc8d257ad6b18c6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840506"
---
# <a name="graycode-function"></a>GrayCode (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Crea sequenze di codice grigio

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a>Input

### <a name="n--int"></a>n: [int](xref:microsoft.quantum.lang-ref.int)

Numero di bit



## <a name="output--intint"></a>Output: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []

Matrice di Tuple. Il primo valore in tupla è il valore in GrayCode Sequence second value in Tuple è position to change in Current Value per ottenere quello successivo.

## <a name="example"></a>Esempio

```qsharp
GrayCode(2); // [(0, 0),(1, 1),(3, 0),(2, 1)]
```
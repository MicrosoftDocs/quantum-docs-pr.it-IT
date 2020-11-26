---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: b15586c57180b00064721afc990436320824cba2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206885"
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
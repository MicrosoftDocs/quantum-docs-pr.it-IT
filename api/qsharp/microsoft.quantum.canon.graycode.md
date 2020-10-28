---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: fc673ae21a952788b5beb74c1bad94ee9fe54480
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716162"
---
# <a name="graycode-function"></a>GrayCode (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Crea sequenze di codice grigio

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a>Input

### <a name="n--int"></a>n: [int](xref:microsoft.quantum.lang-ref.int)

Numero di bit



## <a name="output--intint"></a>Output: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []

Matrice di Tuple. Il primo valore in tupla è il valore in GrayCode Sequence second value in Tuple è position to change in Current Value per ottenere quello successivo.
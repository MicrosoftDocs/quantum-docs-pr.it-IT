---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Sequencel (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 3e5c7f64825f09d82792d3e46fe3f53f5814510b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220264"
---
# <a name="sequencel-function"></a>Sequencel (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Ottiene una matrice di numeri interi in un intervallo specificato.

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a>Input

### <a name="from--bigint"></a>da: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Indice di inizio inclusivo dell'intervallo.


### <a name="to--bigint"></a>a: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Indice finale inclusivo dell'intervallo non più piccolo di `from` .



## <a name="output--bigint"></a>Output: [bigint](xref:microsoft.quantum.lang-ref.bigint)[]

Matrice contenente la sequenza di numeri,,... `from` `from + 1` , `to` .

## <a name="remarks"></a>Commenti

La differenza tra `from` e `to` deve rientrare in un `Int` valore.
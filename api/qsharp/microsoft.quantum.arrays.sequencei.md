---
uid: Microsoft.Quantum.Arrays.SequenceI
title: Sequencei (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 5f03e5f2baff8077c1fa3fb5f1f079528ef0e215
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220298"
---
# <a name="sequencei-function"></a>Sequencei (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Ottiene una matrice di numeri interi in un intervallo specificato.

```qsharp
function SequenceI (from : Int, to : Int) : Int[]
```


## <a name="input"></a>Input

### <a name="from--int"></a>da: [int](xref:microsoft.quantum.lang-ref.int)

Indice di inizio inclusivo dell'intervallo.


### <a name="to--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

Indice finale inclusivo dell'intervallo non più piccolo di `from` .



## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)[]

Matrice contenente la sequenza di numeri,,... `from` `from + 1` , `to` .
---
uid: Microsoft.Quantum.Arrays.SequenceI
title: Sequencei (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5dc4377c696e14b505c63701c2f5ca0dadca672
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718899"
---
# <a name="sequencei-function"></a>Sequencei (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


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
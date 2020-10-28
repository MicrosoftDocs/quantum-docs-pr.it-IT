---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: b033723a50fb85e77c9d4baec1f94231327e9b25
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725221"
---
# <a name="decomposedon-function"></a>DecomposedOn (funzione)

Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacchetto [](https://nuget.org/packages/)


Scompone una permutazione su una variabile

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a>Descrizione

Data una permutazione $ \Pi $ ( `perm` ) e un indice $i $ ( `index` ), questo metodo restituisce tre permutazioni $ ((\ pi_l, \ pi_r), \Pi ') $ in modo tale che le immagini di $ \ pi_l $ e $ \ pi_r $ non modifichino i bit nei rispettivi elementi a indici diversi da $i $ e immagini di $ \Pi ' $ non cambiano bit $i $ nei relativi elementi.

## <a name="input"></a>Input

### <a name="perm--int"></a>Perm: [int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="index--int"></a>Indice: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--intintint"></a>Output: (([int](xref:microsoft.quantum.lang-ref.int)[],[int](xref:microsoft.quantum.lang-ref.int)[]),[int](xref:microsoft.quantum.lang-ref.int)[])


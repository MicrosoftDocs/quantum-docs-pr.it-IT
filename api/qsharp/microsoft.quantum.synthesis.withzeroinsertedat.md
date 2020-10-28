---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: WithZeroInsertedAt (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 6e13251741dadb19740b208cdfc13a14964a48dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725154"
---
# <a name="withzeroinsertedat-function"></a>WithZeroInsertedAt (funzione)

Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacchetto [](https://nuget.org/packages/)


Inserire un valore a 0 bit in un Integer

```qsharp
function WithZeroInsertedAt (position : Int, value : Int) : Int
```


## <a name="description"></a>Descrizione

Questa operazione accetta un Integer, inserisce un oggetto a bit 0 `position` e restituisce il valore aggiornato come Integer.  Se, ad esempio, si inserisce un valore 0 nella posizione 2 nel numero 10 ($10 _ {10} = 1010_ {2} $), viene restituito il numero 18 ($ 18 _ {10} = 10010_ {2} $).

## <a name="input"></a>Input

### <a name="position--int"></a>Posizione: [int](xref:microsoft.quantum.lang-ref.int)

Posizione in cui viene inserito 0


### <a name="value--int"></a>valore: [int](xref:microsoft.quantum.lang-ref.int)

Valore modificato



## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)

Valore modificato
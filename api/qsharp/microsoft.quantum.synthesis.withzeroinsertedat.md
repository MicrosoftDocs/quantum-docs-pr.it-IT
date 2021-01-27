---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: WithZeroInsertedAt (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 7d5f8838b6ae555524fb0e82e14f93e6c77e43d4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855203"
---
# <a name="withzeroinsertedat-function"></a>WithZeroInsertedAt (funzione)

Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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
---
uid: Microsoft.Quantum.Synthesis.DecompositionState
title: Tipo definito dall'utente DecompositionState
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecompositionState
qsharp.summary: State during decomposition based on variable indexes
ms.openlocfilehash: 0547c04828a80b4f696cc17e13c8cc57d0379f96
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725210"
---
# <a name="decompositionstate-user-defined-type"></a>Tipo definito dall'utente DecompositionState

Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacchetto [](https://nuget.org/packages/)


Stato durante la scomposizione in base agli indici delle variabili

```qsharp

newtype DecompositionState = (Perm : Int[], Lfunctions : (BigInt, Int)[], Rfunctions : (BigInt, Int)[]);
```



## <a name="named-items"></a>Elementi denominati

### <a name="perm--int"></a>Perm: [int](xref:microsoft.quantum.lang-ref.int)[]


### <a name="lfunctions--bigintint"></a>Lfunctions: ([bigint](xref:microsoft.quantum.lang-ref.bigint),[int](xref:microsoft.quantum.lang-ref.int)) []


### <a name="rfunctions--bigintint"></a>Rfunctions: ([bigint](xref:microsoft.quantum.lang-ref.bigint),[int](xref:microsoft.quantum.lang-ref.int)) []



## <a name="description"></a>Descrizione

Lo stato include la permutazione corrente e le funzioni attualmente generate per i cancelli controllati a sinistra e i cancelli controllati a destra.
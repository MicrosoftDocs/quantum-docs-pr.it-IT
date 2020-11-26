---
uid: Microsoft.Quantum.Canon.Fst
title: FST (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: 634f11881a054df7fe79d889832ea6bd80a7394f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206936"
---
# <a name="fst-function"></a>FST (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Data una coppia, restituisce il primo elemento.

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a>Input

### <a name="pair--tu"></a>coppia: (t,' U)

Tupla con due elementi.



## <a name="output--t"></a>Output:' t

Primo elemento di `pair`.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo del primo membro della coppia.
### <a name="u"></a>' U

Tipo del secondo membro della coppia.
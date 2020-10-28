---
uid: Microsoft.Quantum.Canon.Delayed
title: Funzione ritardata
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 820a38c2b4de2e0151d55bd88fb4f69567182f6b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716257"
---
# <a name="delayed-function"></a>Funzione ritardata

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Restituisce un'operazione che applica l'operazione specificata con l'argomento specificato.

```qsharp
function Delayed<'T, 'U> (op : ('T => 'U), arg : 'T) : (Unit => 'U)
```


## <a name="input"></a>Input

### <a name="op--t--u"></a>op:' t =>' U 

Operazione da applicare.


### <a name="arg--t"></a>ARG:' t

Input a cui viene applicata l'operazione.



## <a name="output--unit--u"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit) =>' U 

Nuova operazione applicata con l' `op` input `arg`

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di input dell'operazione da ritardare.
### <a name="u"></a>' U

Tipo restituito dell'operazione da ritardare.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. DelayedC](xref:Microsoft.Quantum.Canon.DelayedC)
- [Microsoft. Quantum. Canon. Delaya](xref:Microsoft.Quantum.Canon.DelayedA)
- [Microsoft. Quantum. Canon. DelayedCA](xref:Microsoft.Quantum.Canon.DelayedCA)
- [Microsoft. Quantum. Canon. Delay](xref:Microsoft.Quantum.Canon.Delay)
---
uid: Microsoft.Quantum.Canon.CControlled
title: CControlled (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlled
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens.
ms.openlocfilehash: a155b00806b17258b3f87629659bc7d786e4e11d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716593"
---
# <a name="ccontrolled-function"></a>CControlled (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Data un'operazione operativa, restituisce una nuova operazione che applica l'op se un bit del controllo classico è true. Se `false` , non viene eseguita alcuna operazione.

```qsharp
function CControlled<'T> (op : ('T => Unit)) : ((Bool, 'T) => Unit)
```


## <a name="input"></a>Input

### <a name="op--t--unit"></a>op:' t = [unità](xref:microsoft.quantum.lang-ref.unit)> 

Operazione da applicare in modo condizionale.



## <a name="output--boolt--unit"></a>Output: ([bool](xref:microsoft.quantum.lang-ref.bool),' t) => [unità](xref:microsoft.quantum.lang-ref.unit) 

Una nuova operazione che è op se il bit del controllo classico è true.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di input dell'operazione da applicare in modo condizionale.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. CControlledC](xref:Microsoft.Quantum.Canon.CControlledC)
- [Microsoft. Quantum. Canon. CControlledA](xref:Microsoft.Quantum.Canon.CControlledA)
- [Microsoft. Quantum. Canon. CControlledCA](xref:Microsoft.Quantum.Canon.CControlledCA)
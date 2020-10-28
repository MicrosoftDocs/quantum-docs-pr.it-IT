---
uid: Microsoft.Quantum.Canon.CControlledCA
title: CControlledCA (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledCA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 20a8c9ccf931261f7bc6e347ccc144c92f0d0545
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716568"
---
# <a name="ccontrolledca-function"></a>CControlledCA (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Data un'operazione operativa, restituisce una nuova operazione che applica l'op se un bit del controllo classico è true. Se `false` , non viene eseguita alcuna operazione.
Il modificatore `CA` indica che l'operazione è controllabile e adjointable.

```qsharp
function CControlledCA<'T> (op : ('T => Unit is Ctl + Adj)) : ((Bool, 'T) => Unit is Ctl + Adj)
```


## <a name="input"></a>Input

### <a name="op--t--unit-ctl--adj"></a>op:' t => [unità](xref:microsoft.quantum.lang-ref.unit) CTL + ADJ

Operazione da applicare in modo condizionale.



## <a name="output--boolt--unit-ctl--adj"></a>Output: ([bool](xref:microsoft.quantum.lang-ref.bool),' t) => [unità](xref:microsoft.quantum.lang-ref.unit) CTL + ADJ

Una nuova operazione che è op se il bit del controllo classico è true.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di input dell'operazione da applicare in modo condizionale.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. CControlled](xref:Microsoft.Quantum.Canon.CControlled)
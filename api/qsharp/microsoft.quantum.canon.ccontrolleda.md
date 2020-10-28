---
uid: Microsoft.Quantum.Canon.CControlledA
title: CControlledA (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 30b5e3408fa6e5a79b2f3d63cccc11899c0405ef
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716582"
---
# <a name="ccontrolleda-function"></a>CControlledA (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Data un'operazione operativa, restituisce una nuova operazione che applica l'op se un bit del controllo classico è true. Se `false` , non viene eseguita alcuna operazione.
Il modificatore `A` indica che l'operazione è adjointable.

```qsharp
function CControlledA<'T> (op : ('T => Unit is Adj)) : ((Bool, 'T) => Unit is Adj)
```


## <a name="input"></a>Input

### <a name="op--t--unit-adj"></a>op:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ

Operazione da applicare in modo condizionale.



## <a name="output--boolt--unit-adj"></a>Output: ([bool](xref:microsoft.quantum.lang-ref.bool),' t) => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ

Una nuova operazione che è op se il bit del controllo classico è true.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di input dell'operazione da applicare in modo condizionale.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. CControlled](xref:Microsoft.Quantum.Canon.CControlled)
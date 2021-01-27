---
uid: Microsoft.Quantum.Canon.CControlledC
title: CControlledC (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledC
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: a10c8f0f835fe7cbb8f2d89d521a548169613c0a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840971"
---
# <a name="ccontrolledc-function"></a>CControlledC (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Data un'operazione operativa, restituisce una nuova operazione che applica l'op se un bit del controllo classico è true. Se `false` , non viene eseguita alcuna operazione.
Il modificatore `C` indica che l'operazione è controllabile.

```qsharp
function CControlledC<'T> (op : ('T => Unit is Ctl)) : ((Bool, 'T) => Unit is Ctl)
```


## <a name="input"></a>Input

### <a name="op--t--unit--is-ctl"></a>op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL

Operazione da applicare in modo condizionale.



## <a name="output--boolt--unit--is-ctl"></a>Output: ([bool](xref:microsoft.quantum.lang-ref.bool),' t) => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL

Una nuova operazione che è op se il bit del controllo classico è true.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di input dell'operazione da applicare in modo condizionale.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. CControlled](xref:Microsoft.Quantum.Canon.CControlled)
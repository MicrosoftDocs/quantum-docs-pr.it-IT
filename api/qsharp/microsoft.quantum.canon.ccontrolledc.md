---
uid: Microsoft.Quantum.Canon.CControlledC
title: CControlledC (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledC
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: e5975455385e182236d7e2864e26ca00795a40c6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716579"
---
# <a name="ccontrolledc-function"></a>CControlledC (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Data un'operazione operativa, restituisce una nuova operazione che applica l'op se un bit del controllo classico è true. Se `false` , non viene eseguita alcuna operazione.
Il modificatore `C` indica che l'operazione è controllabile.

```qsharp
function CControlledC<'T> (op : ('T => Unit is Ctl)) : ((Bool, 'T) => Unit is Ctl)
```


## <a name="input"></a>Input

### <a name="op--t--unit-ctl"></a>op:' t => CTL [unit](xref:microsoft.quantum.lang-ref.unit)

Operazione da applicare in modo condizionale.



## <a name="output--boolt--unit-ctl"></a>Output: ([bool](xref:microsoft.quantum.lang-ref.bool),' t) => [unità](xref:microsoft.quantum.lang-ref.unit) CTL

Una nuova operazione che è op se il bit del controllo classico è true.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di input dell'operazione da applicare in modo condizionale.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. CControlled](xref:Microsoft.Quantum.Canon.CControlled)
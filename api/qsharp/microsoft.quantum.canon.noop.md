---
uid: Microsoft.Quantum.Canon.NoOp
title: Operazione NoOp
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: NoOp
qsharp.summary: Performs the identity operation (no-op) on an argument.
ms.openlocfilehash: 45f3c8c9d4bae8ac8f7f60c4e4f8ead5d92e7c00
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852401"
---
# <a name="noop-operation"></a>Operazione NoOp

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Esegue l'operazione di identità (no-op) su un argomento.

```qsharp
operation NoOp<'T> (input : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a>Descrizione

Questa operazione accetta un valore di qualsiasi tipo e non esegue alcuna operazione.
Questo può essere utile quando è previsto un input di un tipo di operazione, ma non è necessario intraprendere alcuna azione.
Se, ad esempio, una particolare sindrome di correzione degli errori indica che non si è verificato alcun errore, `NoOp<Qubit[]>` può essere la procedura di recupero corretta.
Analogamente, se un'operazione prevede una procedura di preparazione dello stato come input, `NoOp<Qubit[]>` può essere usata per preparare lo stato $ \ket{0 \cdots 0} $.

## <a name="input"></a>Input

### <a name="input--t"></a>input:' t

Valore da ignorare.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T



## <a name="remarks"></a>Commenti

In quasi tutti i casi, il parametro di tipo per `NoOp` deve essere specificato in modo esplicito. Ad esempio, `NoOp<Qubit>` è identico a <xref:microsoft.quantum.intrinsic.i> .

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Intrinsic. I](xref:Microsoft.Quantum.Intrinsic.I)
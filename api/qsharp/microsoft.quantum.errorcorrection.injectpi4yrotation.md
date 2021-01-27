---
uid: Microsoft.Quantum.ErrorCorrection.InjectPi4YRotation
title: Operazione InjectPi4YRotation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: InjectPi4YRotation
qsharp.summary: Rotates a single qubit by π/4 about the Y-axis.
ms.openlocfilehash: 249c347c9e9729e719eda69e4e9a21847d9a46eb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98825952"
---
# <a name="injectpi4yrotation-operation"></a>Operazione InjectPi4YRotation

Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Ruota un singolo qubit per π/4 sull'asse Y.

```qsharp
operation InjectPi4YRotation (data : Qubit, magic : Qubit) : Unit is Adj
```


## <a name="description"></a>Descrizione

Esegue una rotazione di π/4 su `Y` .

La rotazione viene eseguita utilizzando uno stato magico; ovvero una copia dello stato $ $ \begin{align} \cos\frac{\Pi} {8} \ket {0} + \sin \frac{\Pi} {8} \ket {1} .
\end{align} $ $

## <a name="input"></a>Input

### <a name="data--qubit"></a>dati: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit da ruotare circa $Y $ by $ \Pi/$4.


### <a name="magic--qubit"></a>magia: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Un qubit inizialmente nello stato Magic. L'applicazione seguente di questa operazione `magic` viene restituita allo stato $ \ket {0} $.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Gli elementi seguenti sono equivalenti:

```qsharp
Ry(PI() / 4.0, data);
```

e

```qsharp
using (magic = Qubit()) {
    Ry(PI() / 4.0, magic);
    InjectPi4YRotation(data, magic);
    Reset(magic);
}
```

Questa operazione supporta il `Adjoint` functor, nel qual caso viene utilizzato lo stesso stato magico, ma l'effetto sui dati qubit è una rotazione $-\ PI/4 $ $Y $-Rotation.
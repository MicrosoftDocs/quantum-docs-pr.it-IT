---
uid: Microsoft.Quantum.ErrorCorrection.InjectPi4YRotation
title: Operazione InjectPi4YRotation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: InjectPi4YRotation
qsharp.summary: Rotates a single qubit by π/4 about the Y-axis.
ms.openlocfilehash: 8558767050c317661dfb490143fa3c8f4ea009e2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712323"
---
# <a name="injectpi4yrotation-operation"></a>Operazione InjectPi4YRotation

Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacchetto [](https://nuget.org/packages/)


Ruota un singolo qubit per π/4 sull'asse Y.

```qsharp
operation InjectPi4YRotation (data : Qubit, magic : Qubit) : Unit
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
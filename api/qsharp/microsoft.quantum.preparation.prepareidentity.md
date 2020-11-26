---
uid: Microsoft.Quantum.Preparation.PrepareIdentity
title: Operazione PrepareIdentity
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareIdentity
qsharp.summary: >-
  Given a register, prepares that register in the maximally mixed state.

  The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.
ms.openlocfilehash: 6e0a43e61e3c49edef94db63f07ed29132d84c83
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210438"
---
# <a name="prepareidentity-operation"></a>Operazione PrepareIdentity

Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dato un registro, prepara il registro nello stato massimo misto.

Il registro viene preparato nello stato $ \boldone/2 ^ N $ applicando il canale depolarizzato completo a ogni qubit, dove $N $ è la lunghezza del registro.

```qsharp
operation PrepareIdentity (register : Qubit[]) : Unit
```


## <a name="input"></a>Input

### <a name="register--qubit"></a>Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Un registro il cui stato deve essere depolarizzato nel modo descritto in precedenza.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. preping. PrepareSingleQubitIdentity](xref:Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity)
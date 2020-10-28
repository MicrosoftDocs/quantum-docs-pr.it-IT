---
uid: Microsoft.Quantum.ErrorCorrection.EncodeOp
title: Tipo definito dall'utente EncodeOp
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeOp
qsharp.summary: >-
  Represents an operation which encodes a physical register into a logical register, using the provided scratch qubits.

  The first argument is taken to be the physical register that will be encoded, while the second argument is taken to be the scratch register that will be used.
ms.openlocfilehash: da947cdc25cb0edd3a4144022bbfc6ecb84c647f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712351"
---
# <a name="encodeop-user-defined-type"></a>Tipo definito dall'utente EncodeOp

Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacchetto [](https://nuget.org/packages/)


Rappresenta un'operazione che consente di codificare un registro fisico in un registro logico, usando il qubits di Scratch fornito.

Il primo argomento viene considerato come il registro fisico che verrà codificato, mentre il secondo argomento viene considerato come il registro Scratch che verrà usato.

```qsharp

newtype EncodeOp = (((Qubit[], Qubit[]) => Microsoft.Quantum.ErrorCorrection.LogicalRegister));
```


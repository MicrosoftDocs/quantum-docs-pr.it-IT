---
uid: Microsoft.Quantum.Oracles.ObliviousOracle
title: Tipo definito dall'utente ObliviousOracle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracle
qsharp.summary: >-
  Represents an oracle for oblivious amplitude amplification.

  The inputs to the oracle $O$ are:

  - The ancilla register $a$ that $O$ acts on. - The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.
ms.openlocfilehash: 2f92dcb28ec669229dfaf9bcb23eef9234552b8a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193880"
---
# <a name="obliviousoracle-user-defined-type"></a>Tipo definito dall'utente ObliviousOracle

Spazio dei nomi: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Rappresenta un Oracle per l'amplificazione dell'ampiezza ignari.

Gli input per Oracle $O $ sono:

- Il registro ancilla $a $ su cui $O $ agisce.
- Il registro di sistema $s $ sul quale viene applicato il gruppo di $U $ desiderato, dopo aver selezionato il registro $a $ in stato $ \ket{t} $ \_ .

```qsharp

newtype ObliviousOracle = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a>Osservazioni

Questo Oracle definito da $ $ O\ket {s} \_ a\ket {\ psi} \_ s = \Lambda\ket{t} \_ a U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{t ^ \perp} \_ a\cdots $ $ agisce sullo stato ancilla $ \ket{s} a \_ $ per implementare l'unità $U $ su qualsiasi stato del sistema $ \ket{\psi} \_ s $ con l'ampiezza $ \lambda $ nella base contrassegnata da $ \ket{t} $ \_ .
Il primo parametro è il registro qubit di $ \ket{s} \_ a $. Il secondo parametro è il registro qubit di $ \ket{\psi} \_ s $.
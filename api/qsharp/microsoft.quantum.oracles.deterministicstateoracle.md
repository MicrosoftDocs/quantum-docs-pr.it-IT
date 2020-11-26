---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracle
title: Tipo definito dall'utente DeterministicStateOracle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracle
qsharp.summary: >-
  Represents an oracle for deterministic state preparation.

  The input to the oracle $O$ is:

  - The register that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 6f8f80aacd3386ba61675101acb87e09fff5afff
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193931"
---
# <a name="deterministicstateoracle-user-defined-type"></a>Tipo definito dall'utente DeterministicStateOracle

Spazio dei nomi: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Rappresenta un oggetto Oracle per la preparazione dello stato deterministico.

L'input per Oracle $O $ è:

- Registro in cui viene archiviato lo stato quantum desiderato $ \ket{\psi} \_ s $.

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a>Osservazioni

Questo Oracle definito da $O \ket {0} = \ket{\psi} $ agisce sullo stato di base di calcolo $ \ket {0} $ per creare lo stato $ \ket{\psi} $.
Il primo parametro è il registro qubit di $ \ket{\psi} $.
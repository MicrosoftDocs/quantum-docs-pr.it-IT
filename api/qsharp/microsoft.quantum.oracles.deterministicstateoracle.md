---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracle
title: Tipo definito dall'utente DeterministicStateOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracle
qsharp.summary: >-
  Represents an oracle for deterministic state preparation.

  The input to the oracle $O$ is:

  - The register that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: f02267d48cf42fb5b02782dc6b667ac7b60a05dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724297"
---
# <a name="deterministicstateoracle-user-defined-type"></a>Tipo definito dall'utente DeterministicStateOracle

Spazio dei nomi: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)

Pacchetto [](https://nuget.org/packages/)


Rappresenta un oggetto Oracle per la preparazione dello stato deterministico.

L'input per Oracle $O $ è:

- Registro in cui viene archiviato lo stato quantum desiderato $ \ket{\psi} \_ s $.

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a>Commenti

Questo Oracle definito da $O \ket {0} = \ket{\psi} $ agisce sullo stato di base di calcolo $ \ket {0} $ per creare lo stato $ \ket{\psi} $.
Il primo parametro è il registro qubit di $ \ket{\psi} $.
---
uid: Microsoft.Quantum.Oracles.StateOracle
title: Tipo definito dall'utente StateOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracle
qsharp.summary: >-
  Represents an oracle for state preparation.

  The inputs to the oracle $O$ are:

  - An integer indexing the flag qubit $f$. - The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 65f4edcf2101190da0c6d00eb4dd21881143ceb0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724227"
---
# <a name="stateoracle-user-defined-type"></a>Tipo definito dall'utente StateOracle

Spazio dei nomi: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)

Pacchetto [](https://nuget.org/packages/)


Rappresenta un oggetto Oracle per la preparazione dello stato.

Gli input per Oracle $O $ sono:

- Intero che indicizza il flag qubit $f $.
- Il registro di sistema $s $ in cui viene archiviato lo stato quantum desiderato $ \ket{\psi} \_ s $.

```qsharp

newtype StateOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a>Commenti

Questo Oracle definito da $ $ O\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, $ $ agisce sullo stato di base di calcolo $ \ket {0} \_ {f} \ket {0} \_ s $ per creare lo stato di destinazione $ \ket{\psi} \_ s $ con l'ampiezza $ \lambda $ nella base contrassegnata da $ \ket {1} \_ f $.
Il primo parametro è un indice del registro qubit di $ \ket {0} \_ f $. Il secondo parametro include entrambi i registri.
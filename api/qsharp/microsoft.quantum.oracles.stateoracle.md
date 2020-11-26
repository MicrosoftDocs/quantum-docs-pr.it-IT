---
uid: Microsoft.Quantum.Oracles.StateOracle
title: Tipo definito dall'utente StateOracle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracle
qsharp.summary: >-
  Represents an oracle for state preparation.

  The inputs to the oracle $O$ are:

  - An integer indexing the flag qubit $f$. - The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 6b2cf09c23942a586414daccb99cbb27b5026b9d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226605"
---
# <a name="stateoracle-user-defined-type"></a>Tipo definito dall'utente StateOracle

Spazio dei nomi: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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
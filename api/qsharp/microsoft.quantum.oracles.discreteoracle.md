---
uid: Microsoft.Quantum.Oracles.DiscreteOracle
title: Tipo definito dall'utente DiscreteOracle
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DiscreteOracle
qsharp.summary: >-
  Represents a discrete-time oracle.

  This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.
ms.openlocfilehash: 4b85f58889ef9cc55518009bdd9b59bdb2b5b842
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842565"
---
# <a name="discreteoracle-user-defined-type"></a>Tipo definito dall'utente DiscreteOracle

Spazio dei nomi: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Rappresenta un Oracle a tempo discreto.

Si tratta di un Oracle che implementa $U ^ m $ per un'operazione fissa $U $ e un numero intero non negativo $m $.

```qsharp

newtype DiscreteOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```


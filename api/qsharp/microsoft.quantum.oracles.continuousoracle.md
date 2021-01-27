---
uid: Microsoft.Quantum.Oracles.ContinuousOracle
title: Tipo definito dall'utente ContinuousOracle
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ContinuousOracle
qsharp.summary: >-
  Represents a continuous-time oracle.

  This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.
ms.openlocfilehash: ac254b7556878550216d5c0c9222620fdc5c5702
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855939"
---
# <a name="continuousoracle-user-defined-type"></a>Tipo definito dall'utente ContinuousOracle

Spazio dei nomi: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Rappresenta un Oracle a tempo continuo.

Si tratta di un Oracle che implementa $U (\delta t): \ket{\psi (t)} \mapsto \ket{\psi (t + \delta t)} $ per tutti gli orari $t $, in cui $U $ è un'operazione fissa e dove $ \delta t $ è un numero reale non negativo.

```qsharp

newtype ContinuousOracle = (((Double, Qubit[]) => Unit is Adj + Ctl));
```


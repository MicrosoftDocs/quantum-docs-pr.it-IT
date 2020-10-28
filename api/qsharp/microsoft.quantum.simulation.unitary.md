---
uid: Microsoft.Quantum.Simulation.Unitary
title: Tipo definito dall'utente unitario
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: Unitary
qsharp.summary: Represents evolution under a unitary operator.
ms.openlocfilehash: d2bba42e80132d0879f42922f28ad50bef54edf3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725333"
---
# <a name="unitary-user-defined-type"></a>Tipo definito dall'utente unitario

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto [](https://nuget.org/packages/)


Rappresenta l'evoluzione in un operatore unitario.

```qsharp

newtype Unitary = ((Qubit[] => Unit is Adj + Ctl));
```


---
uid: Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem
title: Tipo definito dall'utente TimeDependentGeneratorSystem
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentGeneratorSystem
qsharp.summary: Represents a time-dependent dynamical generator as a function from time to the value of the dynamical generator at that time.
ms.openlocfilehash: 144a44448c9fda7a038b17ac7c49f63e8cc4dd55
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719874"
---
# <a name="timedependentgeneratorsystem-user-defined-type"></a>Tipo definito dall'utente TimeDependentGeneratorSystem

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto [](https://nuget.org/packages/)


Rappresenta un generatore dinamico dipendente dal tempo come funzione dal tempo al valore del generatore dinamico in quel momento.

```qsharp

newtype TimeDependentGeneratorSystem = ((Double -> Microsoft.Quantum.Simulation.GeneratorSystem));
```


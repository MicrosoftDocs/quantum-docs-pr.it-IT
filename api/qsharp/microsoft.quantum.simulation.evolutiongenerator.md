---
uid: Microsoft.Quantum.Simulation.EvolutionGenerator
title: Tipo definito dall'utente EvolutionGenerator
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionGenerator
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in terms of that basis.

  Last parameter for number of terms.
ms.openlocfilehash: 9e0fc5a232070c238aad943ab73f064999237c15
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229444"
---
# <a name="evolutiongenerator-user-defined-type"></a>Tipo definito dall'utente EvolutionGenerator

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Rappresenta un generatore dinamico come un set di porte simulabili e un'espansione in termini di tale base.

Ultimo parametro per il numero di termini.

```qsharp

newtype EvolutionGenerator = (Microsoft.Quantum.Simulation.EvolutionSet, Microsoft.Quantum.Simulation.GeneratorSystem);
```


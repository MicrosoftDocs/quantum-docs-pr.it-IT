---
uid: Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
title: Tipo definito dall'utente TimeDependentSimulationAlgorithm
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentSimulationAlgorithm
qsharp.summary: >-
  Represents a time-dependent simulation algorithm.

  A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule> to unitary time-evolution for some time-interval.
ms.openlocfilehash: 9d2a1a853005495b5a9df60ac1f0dcbfbdf7637f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725753"
---
# <a name="timedependentsimulationalgorithm-user-defined-type"></a>Tipo definito dall'utente TimeDependentSimulationAlgorithm

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto [](https://nuget.org/packages/)


Rappresenta un algoritmo di simulazione dipendente dal tempo.

Una tecnica di simulazione dipendente dal tempo converte un <xref:microsoft.quantum.simulation.evolutionschedule>
per l'evoluzione del tempo unitario per un intervallo di tempo.

```qsharp

newtype TimeDependentSimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionSchedule, Qubit[]) => Unit is Adj + Ctl));
```


---
uid: Microsoft.Quantum.Simulation.SimulationAlgorithm
title: Tipo definito dall'utente SimulationAlgorithm
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: SimulationAlgorithm
qsharp.summary: >-
  Represents a time-independent simulation algorithm.

  A time-independent simulation technique converts an <xref:microsoft.quantum.simulation.evolutiongenerator> to unitary time evolution for some time-interval.
ms.openlocfilehash: 9127a936bbf7a212e712645eabdf49fefc7a97d0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725571"
---
# <a name="simulationalgorithm-user-defined-type"></a>Tipo definito dall'utente SimulationAlgorithm

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto [](https://nuget.org/packages/)


Rappresenta un algoritmo di simulazione indipendente dal tempo.

Una tecnica di simulazione indipendente dal tempo converte un <xref:microsoft.quantum.simulation.evolutiongenerator>
per l'evoluzione dell'ora unitaria per un intervallo di tempo.

```qsharp

newtype SimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionGenerator, Qubit[]) => Unit is Adj + Ctl));
```


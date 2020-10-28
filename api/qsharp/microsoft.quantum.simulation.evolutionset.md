---
uid: Microsoft.Quantum.Simulation.EvolutionSet
title: Tipo definito dall'utente EvolutionSet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSet
qsharp.summary: >-
  Represents a set of gates that can be readily implemented and used to implement simulation algorithms.

  Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time
ms.openlocfilehash: 41504837b281b1021a2d09ef75acc10315b4fd07
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710615"
---
# <a name="evolutionset-user-defined-type"></a>Tipo definito dall'utente EvolutionSet

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto [](https://nuget.org/packages/)


Rappresenta un set di controlli che possono essere implementati facilmente e usati per implementare gli algoritmi di simulazione.

Gli elementi del set vengono indicizzati da un oggetto  <xref:microsoft.quantum.simulation.generatorindex> e ogni set viene descritto da una funzione da `GeneratorIndex` a  <xref:microsoft.quantum.simulation.evolutionunitary> , ovvero operazioni parametrizzate da un numero reale che rappresenta il tempo

```qsharp

newtype EvolutionSet = ((Microsoft.Quantum.Simulation.GeneratorIndex -> Microsoft.Quantum.Simulation.EvolutionUnitary));
```


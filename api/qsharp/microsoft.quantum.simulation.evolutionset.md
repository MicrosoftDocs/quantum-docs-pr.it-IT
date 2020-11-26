---
uid: Microsoft.Quantum.Simulation.EvolutionSet
title: Tipo definito dall'utente EvolutionSet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSet
qsharp.summary: >-
  Represents a set of gates that can be readily implemented and used to implement simulation algorithms.

  Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time
ms.openlocfilehash: ee8f3c0716f035dcb0c4fad557092fbf8dd3c356
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229410"
---
# <a name="evolutionset-user-defined-type"></a><span data-ttu-id="6ba05-102">Tipo definito dall'utente EvolutionSet</span><span class="sxs-lookup"><span data-stu-id="6ba05-102">EvolutionSet user defined type</span></span>

<span data-ttu-id="6ba05-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="6ba05-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="6ba05-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6ba05-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6ba05-105">Rappresenta un set di controlli che possono essere implementati facilmente e usati per implementare gli algoritmi di simulazione.</span><span class="sxs-lookup"><span data-stu-id="6ba05-105">Represents a set of gates that can be readily implemented and used to implement simulation algorithms.</span></span>

<span data-ttu-id="6ba05-106">Gli elementi del set vengono indicizzati da un oggetto  <xref:microsoft.quantum.simulation.generatorindex> e ogni set viene descritto da una funzione da `GeneratorIndex` a  <xref:microsoft.quantum.simulation.evolutionunitary> , ovvero operazioni parametrizzate da un numero reale che rappresenta il tempo</span><span class="sxs-lookup"><span data-stu-id="6ba05-106">Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time</span></span>

```qsharp

newtype EvolutionSet = ((Microsoft.Quantum.Simulation.GeneratorIndex -> Microsoft.Quantum.Simulation.EvolutionUnitary));
```


---
uid: Microsoft.Quantum.Simulation.EvolutionSet
title: Tipo definito dall'utente EvolutionSet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSet
qsharp.summary: >-
  Represents a set of gates that can be readily implemented and used to implement simulation algorithms.

  Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time
ms.openlocfilehash: 35c0b24da284a5871fd11b6d624102b853b89d19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856066"
---
# <a name="evolutionset-user-defined-type"></a><span data-ttu-id="f3e3c-102">Tipo definito dall'utente EvolutionSet</span><span class="sxs-lookup"><span data-stu-id="f3e3c-102">EvolutionSet user defined type</span></span>

<span data-ttu-id="f3e3c-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="f3e3c-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="f3e3c-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f3e3c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f3e3c-105">Rappresenta un set di controlli che possono essere implementati facilmente e usati per implementare gli algoritmi di simulazione.</span><span class="sxs-lookup"><span data-stu-id="f3e3c-105">Represents a set of gates that can be readily implemented and used to implement simulation algorithms.</span></span>

<span data-ttu-id="f3e3c-106">Gli elementi del set vengono indicizzati da un oggetto  <xref:microsoft.quantum.simulation.generatorindex> e ogni set viene descritto da una funzione da `GeneratorIndex` a  <xref:microsoft.quantum.simulation.evolutionunitary> , ovvero operazioni parametrizzate da un numero reale che rappresenta il tempo</span><span class="sxs-lookup"><span data-stu-id="f3e3c-106">Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time</span></span>

```qsharp

newtype EvolutionSet = ((Microsoft.Quantum.Simulation.GeneratorIndex -> Microsoft.Quantum.Simulation.EvolutionUnitary));
```


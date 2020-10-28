---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZTermToPauliMajIdx_
title: _ZTermToPauliMajIdx_ (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: 890e60c4b7c5bc474c9f00b59dac6bfddb0e891b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714146"
---
# <a name="_ztermtopaulimajidx_-function"></a><span data-ttu-id="eb536-102">_ZTermToPauliMajIdx_ (funzione)</span><span class="sxs-lookup"><span data-stu-id="eb536-102">_ZTermToPauliMajIdx_ function</span></span>

<span data-ttu-id="eb536-103">Spazio dei nomi: [Microsoft. Quantum. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="eb536-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="eb536-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eb536-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eb536-105">Converte un GeneratorIndex che descrive un termine Z in un'espressione ' GeneratorIndex []' in base a Paulis.</span><span class="sxs-lookup"><span data-stu-id="eb536-105">Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.</span></span>

```qsharp
function _ZTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a><span data-ttu-id="eb536-106">Input</span><span class="sxs-lookup"><span data-stu-id="eb536-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="eb536-107">termine: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="eb536-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="eb536-108">`GeneratorIndex` che rappresenta un termine Z.</span><span class="sxs-lookup"><span data-stu-id="eb536-108">`GeneratorIndex` representing a Z term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="eb536-109">Output: [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span><span class="sxs-lookup"><span data-stu-id="eb536-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span></span>

<span data-ttu-id="eb536-110">' GeneratorIndex []' esprime il termine Z come termini di Pauli.</span><span class="sxs-lookup"><span data-stu-id="eb536-110">'GeneratorIndex[]' expressing Z term as Pauli terms.</span></span>
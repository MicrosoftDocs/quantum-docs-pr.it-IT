---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQandPQQRTermToPauliGenIdx_
title: _PQandPQQRTermToPauliGenIdx_ (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQandPQQRTermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 17acd2c09129275af90222e30fd96a7551e18b50
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203536"
---
# <a name="_pqandpqqrtermtopauligenidx_-function"></a><span data-ttu-id="7addf-102">_PQandPQQRTermToPauliGenIdx_ (funzione)</span><span class="sxs-lookup"><span data-stu-id="7addf-102">_PQandPQQRTermToPauliGenIdx_ function</span></span>

<span data-ttu-id="7addf-103">Spazio dei nomi: [Microsoft. Quantum. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="7addf-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="7addf-104">Pacchetto: [Microsoft. Quantum. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="7addf-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="7addf-105">Converte un GeneratorIndex che descrive un termine PQ o PQQR in un'espressione ' GeneratorIndex []' in termini di Paulis</span><span class="sxs-lookup"><span data-stu-id="7addf-105">Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQandPQQRTermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="7addf-106">Input</span><span class="sxs-lookup"><span data-stu-id="7addf-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="7addf-107">termine: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="7addf-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="7addf-108">`GeneratorIndex` che rappresenta un termine PQ o PQQR.</span><span class="sxs-lookup"><span data-stu-id="7addf-108">`GeneratorIndex` representing a PQ or PQQR term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="7addf-109">Output: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="7addf-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="7addf-110">' GeneratorIndex []' esprime il termine PQ o PQQR come termini di Pauli.</span><span class="sxs-lookup"><span data-stu-id="7addf-110">'GeneratorIndex[]' expressing PQ or PQQR term as Pauli terms.</span></span>
---
uid: Microsoft.Quantum.Chemistry.HTermsToGenIdx
title: HTermsToGenIdx (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenIdx
qsharp.summary: Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.
ms.openlocfilehash: 73324a48cc4b42de0d5d8618ad9e833d289125f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714857"
---
# <a name="htermstogenidx-function"></a><span data-ttu-id="97a06-102">HTermsToGenIdx (funzione)</span><span class="sxs-lookup"><span data-stu-id="97a06-102">HTermsToGenIdx function</span></span>

<span data-ttu-id="97a06-103">Spazio dei nomi: [Microsoft. Quantum. Chemistry](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="97a06-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="97a06-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="97a06-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="97a06-105">Converte un indice in un termine hamiltoniana in `HTerm[]` formato dati in un GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="97a06-105">Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermsToGenIdx (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[], idx : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="97a06-106">Input</span><span class="sxs-lookup"><span data-stu-id="97a06-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="97a06-107">dati: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="97a06-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="97a06-108">Dati di input nel `HTerm[]` formato.</span><span class="sxs-lookup"><span data-stu-id="97a06-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="97a06-109">termType: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="97a06-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="97a06-110">Informazioni aggiuntive aggiunte a GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="97a06-110">Additional information added to GeneratorIndex.</span></span>


### <a name="idx--int"></a><span data-ttu-id="97a06-111">idx: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="97a06-111">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="97a06-112">Indicizzare un termine dell'Hamiltoniana</span><span class="sxs-lookup"><span data-stu-id="97a06-112">Index to a term of the Hamiltonian</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="97a06-113">Output: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="97a06-113">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="97a06-114">Oggetto GeneratorIndex che rappresenta un termine hamiltoniana rappresentato da `data[idx]` , insieme alle informazioni aggiuntive aggiunte da `termType` .</span><span class="sxs-lookup"><span data-stu-id="97a06-114">A GeneratorIndex representing a Hamiltonian term represented by `data[idx]`, together with additional information added by `termType`.</span></span>
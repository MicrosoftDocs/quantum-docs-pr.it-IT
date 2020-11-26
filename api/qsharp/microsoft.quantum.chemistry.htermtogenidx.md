---
uid: Microsoft.Quantum.Chemistry.HTermToGenIdx
title: HTermToGenIdx (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermToGenIdx
qsharp.summary: Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.
ms.openlocfilehash: 59391a882fdbc55172ee93a7428c1735bbb29500
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216031"
---
# <a name="htermtogenidx-function"></a><span data-ttu-id="149c1-102">HTermToGenIdx (funzione)</span><span class="sxs-lookup"><span data-stu-id="149c1-102">HTermToGenIdx function</span></span>

<span data-ttu-id="149c1-103">Spazio dei nomi: [Microsoft. Quantum. Chemistry](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="149c1-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="149c1-104">Pacchetto: [Microsoft. Quantum. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="149c1-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="149c1-105">Converte un termine hamiltoniana in `HTerm` formato dati in un GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="149c1-105">Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermToGenIdx (term : Microsoft.Quantum.Chemistry.HTerm, termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="149c1-106">Input</span><span class="sxs-lookup"><span data-stu-id="149c1-106">Input</span></span>

### <a name="term--hterm"></a><span data-ttu-id="149c1-107">termine: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span><span class="sxs-lookup"><span data-stu-id="149c1-107">term : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span></span>

<span data-ttu-id="149c1-108">Dati di input nel `HTerm` formato.</span><span class="sxs-lookup"><span data-stu-id="149c1-108">Input data in `HTerm` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="149c1-109">termType: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="149c1-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="149c1-110">Informazioni aggiuntive aggiunte a GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="149c1-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="149c1-111">Output: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="149c1-111">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="149c1-112">Oggetto GeneratorIndex che rappresenta un termine hamiltoniana rappresentato da `term` , insieme alle informazioni aggiuntive aggiunte da `termType` .</span><span class="sxs-lookup"><span data-stu-id="149c1-112">A GeneratorIndex representing a Hamiltonian term represented by `term`, together with additional information added by `termType`.</span></span>
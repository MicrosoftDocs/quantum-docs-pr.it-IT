---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: HTermsToGenSys (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: 936e1bcc58b2f1af3bdb606884128c38d2f58867
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204114"
---
# <a name="htermstogensys-function"></a><span data-ttu-id="83646-102">HTermsToGenSys (funzione)</span><span class="sxs-lookup"><span data-stu-id="83646-102">HTermsToGenSys function</span></span>

<span data-ttu-id="83646-103">Spazio dei nomi: [Microsoft. Quantum. Chemistry](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="83646-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="83646-104">Pacchetto: [Microsoft. Quantum. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="83646-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="83646-105">Converte un'Hamiltoniana in `HTerm[]` formato dati in un GeneratorSystem.</span><span class="sxs-lookup"><span data-stu-id="83646-105">Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.</span></span>

```qsharp
function HTermsToGenSys (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="83646-106">Input</span><span class="sxs-lookup"><span data-stu-id="83646-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="83646-107">dati: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="83646-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="83646-108">Dati di input nel `HTerm[]` formato.</span><span class="sxs-lookup"><span data-stu-id="83646-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="83646-109">termType: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="83646-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="83646-110">Informazioni aggiuntive aggiunte a GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="83646-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="83646-111">Output: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="83646-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="83646-112">Oggetto GeneratorSystem che rappresenta un'Hamiltoniana rappresentata dall'input `data` .</span><span class="sxs-lookup"><span data-stu-id="83646-112">A GeneratorSystem representing a Hamiltonian represented by the input `data`.</span></span>
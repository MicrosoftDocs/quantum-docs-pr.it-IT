---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: EqualityFactCP (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 1ea790debb5a9123fb8bee3a5f8a1fde0a050b37
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712771"
---
# <a name="equalityfactcp-function"></a><span data-ttu-id="c5623-102">EqualityFactCP (funzione)</span><span class="sxs-lookup"><span data-stu-id="c5623-102">EqualityFactCP function</span></span>

<span data-ttu-id="c5623-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="c5623-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="c5623-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c5623-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c5623-105">Dichiara che un numero complesso presenta il valore previsto.</span><span class="sxs-lookup"><span data-stu-id="c5623-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="c5623-106">Input</span><span class="sxs-lookup"><span data-stu-id="c5623-106">Input</span></span>

### <a name="actual--complexpolar"></a><span data-ttu-id="c5623-107">valore effettivo: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="c5623-107">actual : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="c5623-108">Valore da verificare.</span><span class="sxs-lookup"><span data-stu-id="c5623-108">The value to be checked.</span></span>


### <a name="expected--complexpolar"></a><span data-ttu-id="c5623-109">previsto: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="c5623-109">expected : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="c5623-110">Valore previsto.</span><span class="sxs-lookup"><span data-stu-id="c5623-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="c5623-111">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="c5623-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="c5623-112">Stringa del messaggio di errore da utilizzare quando viene attivata l'asserzione.</span><span class="sxs-lookup"><span data-stu-id="c5623-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c5623-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c5623-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


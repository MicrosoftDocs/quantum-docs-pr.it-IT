---
uid: Microsoft.Quantum.Diagnostics.EqualityFactC
title: EqualityFactC (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactC
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 4c7256f9a8c84b4e105b1cbff6b18d6dd99cc441
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712785"
---
# <a name="equalityfactc-function"></a><span data-ttu-id="1137e-102">EqualityFactC (funzione)</span><span class="sxs-lookup"><span data-stu-id="1137e-102">EqualityFactC function</span></span>

<span data-ttu-id="1137e-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="1137e-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="1137e-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1137e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1137e-105">Dichiara che un numero complesso presenta il valore previsto.</span><span class="sxs-lookup"><span data-stu-id="1137e-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactC (actual : Microsoft.Quantum.Math.Complex, expected : Microsoft.Quantum.Math.Complex, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="1137e-106">Input</span><span class="sxs-lookup"><span data-stu-id="1137e-106">Input</span></span>

### <a name="actual--complex"></a><span data-ttu-id="1137e-107">effettivo: [complesso](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="1137e-107">actual : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="1137e-108">Valore da verificare.</span><span class="sxs-lookup"><span data-stu-id="1137e-108">The value to be checked.</span></span>


### <a name="expected--complex"></a><span data-ttu-id="1137e-109">previsto: [complesso](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="1137e-109">expected : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="1137e-110">Valore previsto.</span><span class="sxs-lookup"><span data-stu-id="1137e-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="1137e-111">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="1137e-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="1137e-112">Stringa del messaggio di errore da utilizzare quando viene attivata l'asserzione.</span><span class="sxs-lookup"><span data-stu-id="1137e-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1137e-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1137e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

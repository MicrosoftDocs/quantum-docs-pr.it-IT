---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: EqualityFactCP (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 39b55e17302f9d2e5049169e9c1a74e53a8b1115
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201853"
---
# <a name="equalityfactcp-function"></a><span data-ttu-id="b610b-102">EqualityFactCP (funzione)</span><span class="sxs-lookup"><span data-stu-id="b610b-102">EqualityFactCP function</span></span>

<span data-ttu-id="b610b-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="b610b-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="b610b-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b610b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b610b-105">Dichiara che un numero complesso presenta il valore previsto.</span><span class="sxs-lookup"><span data-stu-id="b610b-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="b610b-106">Input</span><span class="sxs-lookup"><span data-stu-id="b610b-106">Input</span></span>

### <a name="actual--complexpolar"></a><span data-ttu-id="b610b-107">valore effettivo: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="b610b-107">actual : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="b610b-108">Valore da verificare.</span><span class="sxs-lookup"><span data-stu-id="b610b-108">The value to be checked.</span></span>


### <a name="expected--complexpolar"></a><span data-ttu-id="b610b-109">previsto: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="b610b-109">expected : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="b610b-110">Valore previsto.</span><span class="sxs-lookup"><span data-stu-id="b610b-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="b610b-111">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="b610b-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="b610b-112">Stringa del messaggio di errore da utilizzare quando viene attivata l'asserzione.</span><span class="sxs-lookup"><span data-stu-id="b610b-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b610b-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b610b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


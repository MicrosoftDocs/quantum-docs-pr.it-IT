---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: EqualityFactR (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 166dff211d6db9da5d39c607af1924ffd6d276dd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201768"
---
# <a name="equalityfactr-function"></a><span data-ttu-id="4e5d2-102">EqualityFactR (funzione)</span><span class="sxs-lookup"><span data-stu-id="4e5d2-102">EqualityFactR function</span></span>

<span data-ttu-id="4e5d2-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="4e5d2-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="4e5d2-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4e5d2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4e5d2-105">Dichiara che una variabile di risultato classica presenta il valore previsto.</span><span class="sxs-lookup"><span data-stu-id="4e5d2-105">Asserts that a classical Result variable has the expected value.</span></span>

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="4e5d2-106">Input</span><span class="sxs-lookup"><span data-stu-id="4e5d2-106">Input</span></span>

### <a name="actual--__invalidresult__"></a><span data-ttu-id="4e5d2-107">effettivo: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="4e5d2-107">actual : __invalid<Result>__</span></span>

<span data-ttu-id="4e5d2-108">Variabile da verificare.</span><span class="sxs-lookup"><span data-stu-id="4e5d2-108">The variable to be checked.</span></span>


### <a name="expected--__invalidresult__"></a><span data-ttu-id="4e5d2-109">previsto: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="4e5d2-109">expected : __invalid<Result>__</span></span>

<span data-ttu-id="4e5d2-110">Valore previsto.</span><span class="sxs-lookup"><span data-stu-id="4e5d2-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="4e5d2-111">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="4e5d2-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="4e5d2-112">Stringa del messaggio di errore da utilizzare quando viene attivata l'asserzione.</span><span class="sxs-lookup"><span data-stu-id="4e5d2-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4e5d2-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4e5d2-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


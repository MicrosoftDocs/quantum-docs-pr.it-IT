---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: EqualityFactR (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 2b293dc581ed58f7e3864a952fb3ecafa68e759c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712743"
---
# <a name="equalityfactr-function"></a><span data-ttu-id="62342-102">EqualityFactR (funzione)</span><span class="sxs-lookup"><span data-stu-id="62342-102">EqualityFactR function</span></span>

<span data-ttu-id="62342-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="62342-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="62342-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="62342-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="62342-105">Dichiara che una variabile di risultato classica presenta il valore previsto.</span><span class="sxs-lookup"><span data-stu-id="62342-105">Asserts that a classical Result variable has the expected value.</span></span>

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="62342-106">Input</span><span class="sxs-lookup"><span data-stu-id="62342-106">Input</span></span>

### <a name="actual--__invalidresult__"></a><span data-ttu-id="62342-107">effettivo: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="62342-107">actual : __invalid<Result>__</span></span>

<span data-ttu-id="62342-108">Variabile da verificare.</span><span class="sxs-lookup"><span data-stu-id="62342-108">The variable to be checked.</span></span>


### <a name="expected--__invalidresult__"></a><span data-ttu-id="62342-109">previsto: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="62342-109">expected : __invalid<Result>__</span></span>

<span data-ttu-id="62342-110">Valore previsto.</span><span class="sxs-lookup"><span data-stu-id="62342-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="62342-111">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="62342-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="62342-112">Stringa del messaggio di errore da utilizzare quando viene attivata l'asserzione.</span><span class="sxs-lookup"><span data-stu-id="62342-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="62342-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="62342-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


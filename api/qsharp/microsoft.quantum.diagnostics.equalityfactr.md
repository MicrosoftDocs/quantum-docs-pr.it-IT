---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: EqualityFactR (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 86d2ddff79f0bca7badd95a2fe2156c558fa7f86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853338"
---
# <a name="equalityfactr-function"></a><span data-ttu-id="10ca7-102">EqualityFactR (funzione)</span><span class="sxs-lookup"><span data-stu-id="10ca7-102">EqualityFactR function</span></span>

<span data-ttu-id="10ca7-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="10ca7-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="10ca7-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="10ca7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="10ca7-105">Dichiara che una variabile di risultato classica presenta il valore previsto.</span><span class="sxs-lookup"><span data-stu-id="10ca7-105">Asserts that a classical Result variable has the expected value.</span></span>

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="10ca7-106">Input</span><span class="sxs-lookup"><span data-stu-id="10ca7-106">Input</span></span>

### <a name="actual--__invalidresult__"></a><span data-ttu-id="10ca7-107">effettivo: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="10ca7-107">actual : __invalid<Result>__</span></span>

<span data-ttu-id="10ca7-108">Variabile da verificare.</span><span class="sxs-lookup"><span data-stu-id="10ca7-108">The variable to be checked.</span></span>


### <a name="expected--__invalidresult__"></a><span data-ttu-id="10ca7-109">previsto: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="10ca7-109">expected : __invalid<Result>__</span></span>

<span data-ttu-id="10ca7-110">Valore previsto.</span><span class="sxs-lookup"><span data-stu-id="10ca7-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="10ca7-111">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="10ca7-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="10ca7-112">Stringa del messaggio di errore da utilizzare quando viene attivata l'asserzione.</span><span class="sxs-lookup"><span data-stu-id="10ca7-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="10ca7-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="10ca7-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


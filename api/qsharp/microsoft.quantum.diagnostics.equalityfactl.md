---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: 2aaabf39d6ce49952466a877685776490ef438ad
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201802"
---
# <a name="equalityfactl-function"></a><span data-ttu-id="990f2-102">EqualityFactL (funzione)</span><span class="sxs-lookup"><span data-stu-id="990f2-102">EqualityFactL function</span></span>

<span data-ttu-id="990f2-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="990f2-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="990f2-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="990f2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="990f2-105">Dichiara che una variabile BigInt classica presenta il valore previsto.</span><span class="sxs-lookup"><span data-stu-id="990f2-105">Asserts that a classical BigInt variable has the expected value.</span></span>

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="990f2-106">Input</span><span class="sxs-lookup"><span data-stu-id="990f2-106">Input</span></span>

### <a name="actual--bigint"></a><span data-ttu-id="990f2-107">effettivo: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="990f2-107">actual : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="990f2-108">Numero da verificare.</span><span class="sxs-lookup"><span data-stu-id="990f2-108">The number to be checked.</span></span>


### <a name="expected--bigint"></a><span data-ttu-id="990f2-109">previsto: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="990f2-109">expected : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="990f2-110">Valore previsto.</span><span class="sxs-lookup"><span data-stu-id="990f2-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="990f2-111">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="990f2-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="990f2-112">Stringa del messaggio di errore da utilizzare quando viene attivata l'asserzione.</span><span class="sxs-lookup"><span data-stu-id="990f2-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="990f2-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="990f2-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


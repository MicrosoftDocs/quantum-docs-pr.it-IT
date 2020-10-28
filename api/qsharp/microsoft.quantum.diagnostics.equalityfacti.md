---
uid: Microsoft.Quantum.Diagnostics.EqualityFactI
title: EqualityFactI (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactI
qsharp.summary: Asserts that a classical Int variable has the expected value.
ms.openlocfilehash: 34bb38a9447f71372ec0b234731f31a5818d3af1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712760"
---
# <a name="equalityfacti-function"></a><span data-ttu-id="c7ef8-102">EqualityFactI (funzione)</span><span class="sxs-lookup"><span data-stu-id="c7ef8-102">EqualityFactI function</span></span>

<span data-ttu-id="c7ef8-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="c7ef8-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="c7ef8-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c7ef8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c7ef8-105">Dichiara che una variabile int classica presenta il valore previsto.</span><span class="sxs-lookup"><span data-stu-id="c7ef8-105">Asserts that a classical Int variable has the expected value.</span></span>

```qsharp
function EqualityFactI (actual : Int, expected : Int, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="c7ef8-106">Input</span><span class="sxs-lookup"><span data-stu-id="c7ef8-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="c7ef8-107">effettivo: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c7ef8-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c7ef8-108">Numero da verificare.</span><span class="sxs-lookup"><span data-stu-id="c7ef8-108">The number to be checked.</span></span>


### <a name="expected--int"></a><span data-ttu-id="c7ef8-109">previsto: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c7ef8-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c7ef8-110">Valore previsto.</span><span class="sxs-lookup"><span data-stu-id="c7ef8-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="c7ef8-111">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="c7ef8-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="c7ef8-112">Stringa del messaggio di errore da utilizzare quando viene attivata l'asserzione.</span><span class="sxs-lookup"><span data-stu-id="c7ef8-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c7ef8-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c7ef8-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


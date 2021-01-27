---
uid: Microsoft.Quantum.Diagnostics.EqualityFactI
title: EqualityFactI (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactI
qsharp.summary: Asserts that a classical Int variable has the expected value.
ms.openlocfilehash: c41cb5548e8dfebb4d1c1a1c052306878c85e821
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853340"
---
# <a name="equalityfacti-function"></a><span data-ttu-id="d8ed7-102">EqualityFactI (funzione)</span><span class="sxs-lookup"><span data-stu-id="d8ed7-102">EqualityFactI function</span></span>

<span data-ttu-id="d8ed7-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="d8ed7-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="d8ed7-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d8ed7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d8ed7-105">Dichiara che una variabile int classica presenta il valore previsto.</span><span class="sxs-lookup"><span data-stu-id="d8ed7-105">Asserts that a classical Int variable has the expected value.</span></span>

```qsharp
function EqualityFactI (actual : Int, expected : Int, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="d8ed7-106">Input</span><span class="sxs-lookup"><span data-stu-id="d8ed7-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="d8ed7-107">effettivo: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d8ed7-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d8ed7-108">Numero da verificare.</span><span class="sxs-lookup"><span data-stu-id="d8ed7-108">The number to be checked.</span></span>


### <a name="expected--int"></a><span data-ttu-id="d8ed7-109">previsto: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d8ed7-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d8ed7-110">Valore previsto.</span><span class="sxs-lookup"><span data-stu-id="d8ed7-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="d8ed7-111">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="d8ed7-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="d8ed7-112">Stringa del messaggio di errore da utilizzare quando viene attivata l'asserzione.</span><span class="sxs-lookup"><span data-stu-id="d8ed7-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d8ed7-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d8ed7-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


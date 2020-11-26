---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: AllEqualityFactI (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: 92b57f49407d558e5f8d0365c168b7890f1f4981
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223885"
---
# <a name="allequalityfacti-function"></a><span data-ttu-id="141ec-102">AllEqualityFactI (funzione)</span><span class="sxs-lookup"><span data-stu-id="141ec-102">AllEqualityFactI function</span></span>

<span data-ttu-id="141ec-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="141ec-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="141ec-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="141ec-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="141ec-105">Asserisce che due matrici di valori integer sono uguali.</span><span class="sxs-lookup"><span data-stu-id="141ec-105">Asserts that two arrays of integer values are equal.</span></span>

```qsharp
function AllEqualityFactI (actual : Int[], expected : Int[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="141ec-106">Input</span><span class="sxs-lookup"><span data-stu-id="141ec-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="141ec-107">effettivo: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="141ec-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="141ec-108">Matrice prodotta da un test case di interesse.</span><span class="sxs-lookup"><span data-stu-id="141ec-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--int"></a><span data-ttu-id="141ec-109">previsto: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="141ec-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="141ec-110">Matrice prevista da un test case di interesse.</span><span class="sxs-lookup"><span data-stu-id="141ec-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="141ec-111">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="141ec-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="141ec-112">Messaggio da stampare se le matrici non sono uguali.</span><span class="sxs-lookup"><span data-stu-id="141ec-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="141ec-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="141ec-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


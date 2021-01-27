---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: AllEqualityFactI (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: a7043b9c670f79e270180c583fef56b70c1a3bcb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830896"
---
# <a name="allequalityfacti-function"></a><span data-ttu-id="5c691-102">AllEqualityFactI (funzione)</span><span class="sxs-lookup"><span data-stu-id="5c691-102">AllEqualityFactI function</span></span>

<span data-ttu-id="5c691-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="5c691-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="5c691-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5c691-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5c691-105">Asserisce che due matrici di valori integer sono uguali.</span><span class="sxs-lookup"><span data-stu-id="5c691-105">Asserts that two arrays of integer values are equal.</span></span>

```qsharp
function AllEqualityFactI (actual : Int[], expected : Int[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="5c691-106">Input</span><span class="sxs-lookup"><span data-stu-id="5c691-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="5c691-107">effettivo: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="5c691-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="5c691-108">Matrice prodotta da un test case di interesse.</span><span class="sxs-lookup"><span data-stu-id="5c691-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--int"></a><span data-ttu-id="5c691-109">previsto: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="5c691-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="5c691-110">Matrice prevista da un test case di interesse.</span><span class="sxs-lookup"><span data-stu-id="5c691-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="5c691-111">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="5c691-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="5c691-112">Messaggio da stampare se le matrici non sono uguali.</span><span class="sxs-lookup"><span data-stu-id="5c691-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5c691-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5c691-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: AllEqualityFactI (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: 9ccd212010ae557de5ca4ab2a38d4724c5c29aa8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713068"
---
# <a name="allequalityfacti-function"></a><span data-ttu-id="71266-102">AllEqualityFactI (funzione)</span><span class="sxs-lookup"><span data-stu-id="71266-102">AllEqualityFactI function</span></span>

<span data-ttu-id="71266-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="71266-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="71266-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="71266-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="71266-105">Asserisce che due matrici di valori integer sono uguali.</span><span class="sxs-lookup"><span data-stu-id="71266-105">Asserts that two arrays of integer values are equal.</span></span>

```qsharp
function AllEqualityFactI (actual : Int[], expected : Int[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="71266-106">Input</span><span class="sxs-lookup"><span data-stu-id="71266-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="71266-107">effettivo: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="71266-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="71266-108">Matrice prodotta da un test case di interesse.</span><span class="sxs-lookup"><span data-stu-id="71266-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--int"></a><span data-ttu-id="71266-109">previsto: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="71266-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="71266-110">Matrice prevista da un test case di interesse.</span><span class="sxs-lookup"><span data-stu-id="71266-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="71266-111">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="71266-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="71266-112">Messaggio da stampare se le matrici non sono uguali.</span><span class="sxs-lookup"><span data-stu-id="71266-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="71266-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="71266-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


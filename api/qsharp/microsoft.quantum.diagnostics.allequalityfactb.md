---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactB
title: AllEqualityFactB (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactB
qsharp.summary: Asserts that two arrays of boolean values are equal.
ms.openlocfilehash: 100aacccbfd5b45ac9f859cd89424b0ed4007f72
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713079"
---
# <a name="allequalityfactb-function"></a><span data-ttu-id="b1de1-102">AllEqualityFactB (funzione)</span><span class="sxs-lookup"><span data-stu-id="b1de1-102">AllEqualityFactB function</span></span>

<span data-ttu-id="b1de1-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="b1de1-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="b1de1-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b1de1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b1de1-105">Asserisce che due matrici di valori booleani sono uguali.</span><span class="sxs-lookup"><span data-stu-id="b1de1-105">Asserts that two arrays of boolean values are equal.</span></span>

```qsharp
function AllEqualityFactB (actual : Bool[], expected : Bool[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="b1de1-106">Input</span><span class="sxs-lookup"><span data-stu-id="b1de1-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="b1de1-107">effettivo: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="b1de1-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="b1de1-108">Matrice prodotta da un test case di interesse.</span><span class="sxs-lookup"><span data-stu-id="b1de1-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="b1de1-109">previsto: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="b1de1-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="b1de1-110">Matrice prevista da un test case di interesse.</span><span class="sxs-lookup"><span data-stu-id="b1de1-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="b1de1-111">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="b1de1-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="b1de1-112">Messaggio da stampare se le matrici non sono uguali.</span><span class="sxs-lookup"><span data-stu-id="b1de1-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b1de1-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b1de1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


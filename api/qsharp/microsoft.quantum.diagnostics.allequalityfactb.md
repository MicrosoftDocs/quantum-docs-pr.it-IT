---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactB
title: AllEqualityFactB (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactB
qsharp.summary: Asserts that two arrays of boolean values are equal.
ms.openlocfilehash: 725291e8b5d12683ad580d5938dadd561831e88e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853549"
---
# <a name="allequalityfactb-function"></a><span data-ttu-id="1c96f-102">AllEqualityFactB (funzione)</span><span class="sxs-lookup"><span data-stu-id="1c96f-102">AllEqualityFactB function</span></span>

<span data-ttu-id="1c96f-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="1c96f-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="1c96f-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1c96f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1c96f-105">Asserisce che due matrici di valori booleani sono uguali.</span><span class="sxs-lookup"><span data-stu-id="1c96f-105">Asserts that two arrays of boolean values are equal.</span></span>

```qsharp
function AllEqualityFactB (actual : Bool[], expected : Bool[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="1c96f-106">Input</span><span class="sxs-lookup"><span data-stu-id="1c96f-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="1c96f-107">effettivo: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="1c96f-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="1c96f-108">Matrice prodotta da un test case di interesse.</span><span class="sxs-lookup"><span data-stu-id="1c96f-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="1c96f-109">previsto: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="1c96f-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="1c96f-110">Matrice prevista da un test case di interesse.</span><span class="sxs-lookup"><span data-stu-id="1c96f-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="1c96f-111">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="1c96f-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="1c96f-112">Messaggio da stampare se le matrici non sono uguali.</span><span class="sxs-lookup"><span data-stu-id="1c96f-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1c96f-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1c96f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


---
uid: Microsoft.Quantum.Arrays.Swapped
title: Funzione scambiata
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: fa5b37b4caf5d8f19ed05075ddd7bc4217036bfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718827"
---
# <a name="swapped-function"></a><span data-ttu-id="1c832-102">Funzione scambiata</span><span class="sxs-lookup"><span data-stu-id="1c832-102">Swapped function</span></span>

<span data-ttu-id="1c832-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="1c832-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="1c832-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1c832-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1c832-105">Applica uno scambio di due elementi in una matrice.</span><span class="sxs-lookup"><span data-stu-id="1c832-105">Applies a swap of two elements in an array.</span></span>

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="1c832-106">Input</span><span class="sxs-lookup"><span data-stu-id="1c832-106">Input</span></span>

### <a name="firstindex--int"></a><span data-ttu-id="1c832-107">firstIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1c832-107">firstIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1c832-108">Indice del primo elemento da scambiare.</span><span class="sxs-lookup"><span data-stu-id="1c832-108">Index of the first element to be swapped.</span></span>


### <a name="secondindex--int"></a><span data-ttu-id="1c832-109">secondIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1c832-109">secondIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1c832-110">Indice del secondo elemento da scambiare.</span><span class="sxs-lookup"><span data-stu-id="1c832-110">Index of the second element to be swapped.</span></span>


### <a name="arr--t"></a><span data-ttu-id="1c832-111">arr:' t []</span><span class="sxs-lookup"><span data-stu-id="1c832-111">arr : 'T[]</span></span>

<span data-ttu-id="1c832-112">Matrice con elementi da scambiare.</span><span class="sxs-lookup"><span data-stu-id="1c832-112">Array with elements to be swapped.</span></span>



## <a name="output--t"></a><span data-ttu-id="1c832-113">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="1c832-113">Output : 'T[]</span></span>

<span data-ttu-id="1c832-114">Matrice con lo swap sul posto applicato.</span><span class="sxs-lookup"><span data-stu-id="1c832-114">The array with the in place swap applied.</span></span>

## <a name="example"></a><span data-ttu-id="1c832-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="1c832-115">Example</span></span>

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a><span data-ttu-id="1c832-116">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="1c832-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1c832-117">T</span><span class="sxs-lookup"><span data-stu-id="1c832-117">'T</span></span>


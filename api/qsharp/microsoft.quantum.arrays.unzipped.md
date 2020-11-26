---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Funzione decompressa
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: aee1d48c9e0a1f104040bc56c78fdbb8bc4d34ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219958"
---
# <a name="unzipped-function"></a><span data-ttu-id="36b2a-102">Funzione decompressa</span><span class="sxs-lookup"><span data-stu-id="36b2a-102">Unzipped function</span></span>

<span data-ttu-id="36b2a-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="36b2a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="36b2a-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="36b2a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="36b2a-105">Data una matrice di 2 Tuple, restituisce una tupla di due matrici, ognuna contenente gli elementi delle tuple della matrice di input.</span><span class="sxs-lookup"><span data-stu-id="36b2a-105">Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.</span></span>

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a><span data-ttu-id="36b2a-106">Input</span><span class="sxs-lookup"><span data-stu-id="36b2a-106">Input</span></span>

### <a name="arr--tu"></a><span data-ttu-id="36b2a-107">arr: (t,' U) []</span><span class="sxs-lookup"><span data-stu-id="36b2a-107">arr : ('T,'U)[]</span></span>

<span data-ttu-id="36b2a-108">Matrice contenente 2 Tuple</span><span class="sxs-lookup"><span data-stu-id="36b2a-108">An array containing 2-tuples</span></span>



## <a name="output--tu"></a><span data-ttu-id="36b2a-109">Output: (' t [],' U [])</span><span class="sxs-lookup"><span data-stu-id="36b2a-109">Output : ('T[],'U[])</span></span>

<span data-ttu-id="36b2a-110">Due matrici, il primo contenente tutti i primi elementi delle tuple di input, il secondo contenente tutti i secondi elementi delle tuple di input.</span><span class="sxs-lookup"><span data-stu-id="36b2a-110">Two arrays, the first one containing all first elements of the input tuples, the second one containing all second elements of the input tuples.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="36b2a-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="36b2a-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="36b2a-112">T</span><span class="sxs-lookup"><span data-stu-id="36b2a-112">'T</span></span>

<span data-ttu-id="36b2a-113">Tipo del primo elemento in ogni tupla</span><span class="sxs-lookup"><span data-stu-id="36b2a-113">The type of the first element in each tuple</span></span>
### <a name="u"></a><span data-ttu-id="36b2a-114">' U</span><span class="sxs-lookup"><span data-stu-id="36b2a-114">'U</span></span>

<span data-ttu-id="36b2a-115">Tipo del secondo elemento in ogni tupla</span><span class="sxs-lookup"><span data-stu-id="36b2a-115">The type of the second element in each tuple</span></span>

## <a name="see-also"></a><span data-ttu-id="36b2a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36b2a-116">See Also</span></span>

- [<span data-ttu-id="36b2a-117">Microsoft.Quantum.Arrays.ZipPED</span><span class="sxs-lookup"><span data-stu-id="36b2a-117">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)
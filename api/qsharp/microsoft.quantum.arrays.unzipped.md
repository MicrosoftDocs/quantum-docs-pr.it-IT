---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Funzione decompressa
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 37c960dc5dbdb8099fbebe1ad63cb44ce642733c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718791"
---
# <a name="unzipped-function"></a><span data-ttu-id="bfe25-102">Funzione decompressa</span><span class="sxs-lookup"><span data-stu-id="bfe25-102">Unzipped function</span></span>

<span data-ttu-id="bfe25-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="bfe25-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="bfe25-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bfe25-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bfe25-105">Data una matrice di 2 Tuple, restituisce una tupla di due matrici, ognuna contenente gli elementi delle tuple della matrice di input.</span><span class="sxs-lookup"><span data-stu-id="bfe25-105">Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.</span></span>

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a><span data-ttu-id="bfe25-106">Input</span><span class="sxs-lookup"><span data-stu-id="bfe25-106">Input</span></span>

### <a name="arr--tu"></a><span data-ttu-id="bfe25-107">arr: (t,' U) []</span><span class="sxs-lookup"><span data-stu-id="bfe25-107">arr : ('T,'U)[]</span></span>

<span data-ttu-id="bfe25-108">Matrice contenente 2 Tuple</span><span class="sxs-lookup"><span data-stu-id="bfe25-108">An array containing 2-tuples</span></span>



## <a name="output--tu"></a><span data-ttu-id="bfe25-109">Output: (' t [],' U [])</span><span class="sxs-lookup"><span data-stu-id="bfe25-109">Output : ('T[],'U[])</span></span>

<span data-ttu-id="bfe25-110">Due matrici, il primo contenente tutti i primi elementi delle tuple di input, il secondo contenente tutti i secondi elementi delle tuple di input.</span><span class="sxs-lookup"><span data-stu-id="bfe25-110">Two arrays, the first one containing all first elements of the input tuples, the second one containing all second elements of the input tuples.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bfe25-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="bfe25-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bfe25-112">T</span><span class="sxs-lookup"><span data-stu-id="bfe25-112">'T</span></span>

<span data-ttu-id="bfe25-113">Tipo del primo elemento in ogni tupla</span><span class="sxs-lookup"><span data-stu-id="bfe25-113">The type of the first element in each tuple</span></span>
### <a name="u"></a><span data-ttu-id="bfe25-114">' U</span><span class="sxs-lookup"><span data-stu-id="bfe25-114">'U</span></span>

<span data-ttu-id="bfe25-115">Tipo del secondo elemento in ogni tupla</span><span class="sxs-lookup"><span data-stu-id="bfe25-115">The type of the second element in each tuple</span></span>

## <a name="see-also"></a><span data-ttu-id="bfe25-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfe25-116">See Also</span></span>

- [<span data-ttu-id="bfe25-117">Microsoft.Quantum.Arrays.ZipPED</span><span class="sxs-lookup"><span data-stu-id="bfe25-117">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)
---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Funzione decompressa
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 7eea7982721dc596b8660be5f3634df71b1ddf95
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845373"
---
# <a name="unzipped-function"></a><span data-ttu-id="a4604-102">Funzione decompressa</span><span class="sxs-lookup"><span data-stu-id="a4604-102">Unzipped function</span></span>

<span data-ttu-id="a4604-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a4604-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a4604-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a4604-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a4604-105">Data una matrice di 2 Tuple, restituisce una tupla di due matrici, ognuna contenente gli elementi delle tuple della matrice di input.</span><span class="sxs-lookup"><span data-stu-id="a4604-105">Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.</span></span>

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a><span data-ttu-id="a4604-106">Input</span><span class="sxs-lookup"><span data-stu-id="a4604-106">Input</span></span>

### <a name="arr--tu"></a><span data-ttu-id="a4604-107">arr: (t,' U) []</span><span class="sxs-lookup"><span data-stu-id="a4604-107">arr : ('T,'U)[]</span></span>

<span data-ttu-id="a4604-108">Matrice contenente 2 Tuple</span><span class="sxs-lookup"><span data-stu-id="a4604-108">An array containing 2-tuples</span></span>



## <a name="output--tu"></a><span data-ttu-id="a4604-109">Output: (' t [],' U [])</span><span class="sxs-lookup"><span data-stu-id="a4604-109">Output : ('T[],'U[])</span></span>

<span data-ttu-id="a4604-110">Due matrici, il primo contenente tutti i primi elementi delle tuple di input, il secondo contenente tutti i secondi elementi delle tuple di input.</span><span class="sxs-lookup"><span data-stu-id="a4604-110">Two arrays, the first one containing all first elements of the input tuples, the second one containing all second elements of the input tuples.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a4604-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="a4604-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a4604-112">T</span><span class="sxs-lookup"><span data-stu-id="a4604-112">'T</span></span>

<span data-ttu-id="a4604-113">Tipo del primo elemento in ogni tupla</span><span class="sxs-lookup"><span data-stu-id="a4604-113">The type of the first element in each tuple</span></span>
### <a name="u"></a><span data-ttu-id="a4604-114">' U</span><span class="sxs-lookup"><span data-stu-id="a4604-114">'U</span></span>

<span data-ttu-id="a4604-115">Tipo del secondo elemento in ogni tupla</span><span class="sxs-lookup"><span data-stu-id="a4604-115">The type of the second element in each tuple</span></span>

## <a name="example"></a><span data-ttu-id="a4604-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="a4604-116">Example</span></span>

```qsharp
// split is same as ([6, 5, 5, 3, 2, 1], [true, false, false, false, true, false])
let split = Unzipped([(6, true), (5, false), (5, false), (3, false), (2, true), (1, false)]);
```

## <a name="see-also"></a><span data-ttu-id="a4604-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4604-117">See Also</span></span>

- [<span data-ttu-id="a4604-118">Microsoft.Quantum.Arrays.ZipPED</span><span class="sxs-lookup"><span data-stu-id="a4604-118">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)
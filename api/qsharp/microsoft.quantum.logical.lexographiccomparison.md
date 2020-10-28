---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: LexographicComparison (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: f0b68974a0ea26907b58971e4fa4b1f06f5714d2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709904"
---
# <a name="lexographiccomparison-function"></a><span data-ttu-id="a5066-102">LexographicComparison (funzione)</span><span class="sxs-lookup"><span data-stu-id="a5066-102">LexographicComparison function</span></span>

<span data-ttu-id="a5066-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="a5066-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="a5066-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a5066-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a5066-105">Data una funzione di confronto, restituisce una nuova funzione che lexographically Confronta due matrici.</span><span class="sxs-lookup"><span data-stu-id="a5066-105">Given a comparison function, returns a new function that lexographically compares two arrays.</span></span>

```qsharp
function LexographicComparison<'T> (elementComparison : (('T, 'T) -> Bool)) : (('T[], 'T[]) -> Bool)
```


## <a name="input"></a><span data-ttu-id="a5066-106">Input</span><span class="sxs-lookup"><span data-stu-id="a5066-106">Input</span></span>

### <a name="elementcomparison--tt---bool"></a><span data-ttu-id="a5066-107">elementComparison: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a5066-107">elementComparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a5066-108">Funzione che confronta due elementi `x` e `y` restituisce se `x` è minore o uguale a `y` .</span><span class="sxs-lookup"><span data-stu-id="a5066-108">A function that compares two elements `x` and `y` and returns if `x` is less than or equal to `y`.</span></span>



## <a name="output--tt---bool"></a><span data-ttu-id="a5066-109">Output: (t [],' t [])-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a5066-109">Output : ('T[],'T[]) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a5066-110">Funzione che confronta due matrici `xs` e `ys` restituisce se `xs` si verifica prima o uguale a `ys` nell'ordinamento lexographical.</span><span class="sxs-lookup"><span data-stu-id="a5066-110">A function that compares two arrays `xs` and `ys` and returns if `xs` occurs before or equal to `ys` in lexographical ordering.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a5066-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="a5066-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a5066-112">T</span><span class="sxs-lookup"><span data-stu-id="a5066-112">'T</span></span>

<span data-ttu-id="a5066-113">Tipo degli elementi delle matrici da confrontare.</span><span class="sxs-lookup"><span data-stu-id="a5066-113">The type of the elements of the arrays being compared.</span></span>

## <a name="remarks"></a><span data-ttu-id="a5066-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="a5066-114">Remarks</span></span>

<span data-ttu-id="a5066-115">Il confronto lexographic tra due matrici `xs` e `ys` viene definito dalla procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="a5066-115">The lexographic comparison between two arrays `xs` and `ys` is defined by the following procedure.</span></span> <span data-ttu-id="a5066-116">Si dice che due elementi `x` e `y` sono equivalenti se `elementComparison(x, y)` e `elementComparison(y, x)` sono entrambi true.</span><span class="sxs-lookup"><span data-stu-id="a5066-116">We say that two elements `x` and `y` are equivalent if `elementComparison(x, y)` and `elementComparison(y, x)` are both true.</span></span>

- <span data-ttu-id="a5066-117">Entrambe le matrici vengono confrontate elemento per elemento fino alla prima coppia di elementi che non sono equivalenti.</span><span class="sxs-lookup"><span data-stu-id="a5066-117">Both arrays are compared element-by-element until the first pair of elements that are not equivalent.</span></span> <span data-ttu-id="a5066-118">La matrice che contiene l'elemento che si verifica per primo in base a `elementComparison` è detta prima nell'ordinamento lexographical.</span><span class="sxs-lookup"><span data-stu-id="a5066-118">The array containing the element that occurs first according to `elementComparison` is said to occur first in lexographical ordering.</span></span>
- <span data-ttu-id="a5066-119">Se non vengono trovati elementi inequivalenti e una matrice è più lunga dell'altra, viene detta prima di tutto la matrice più breve.</span><span class="sxs-lookup"><span data-stu-id="a5066-119">If no inequivalent elements are found, and one array is longer than the other, the shorter array is said to occur first.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5066-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5066-120">See Also</span></span>

- [<span data-ttu-id="a5066-121">Microsoft. Quantum. Arrays. Sorted</span><span class="sxs-lookup"><span data-stu-id="a5066-121">Microsoft.Quantum.Arrays.Sorted</span></span>](xref:Microsoft.Quantum.Arrays.Sorted)
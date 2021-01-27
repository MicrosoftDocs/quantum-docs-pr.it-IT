---
uid: Microsoft.Quantum.Arrays.EqualA
title: Equala (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: fe22e208f67d2c289b0b2d99f19ff26fc5abc3d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848697"
---
# <a name="equala-function"></a><span data-ttu-id="7183e-102">Equala (funzione)</span><span class="sxs-lookup"><span data-stu-id="7183e-102">EqualA function</span></span>

<span data-ttu-id="7183e-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="7183e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="7183e-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7183e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7183e-105">Date due matrici dello stesso tipo e un predicato definito per coppie di elementi delle matrici, verifica se le matrici sono uguali.</span><span class="sxs-lookup"><span data-stu-id="7183e-105">Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.</span></span>

```qsharp
function EqualA<'T> (equal : (('T, 'T) -> Bool), array1 : 'T[], array2 : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="7183e-106">Input</span><span class="sxs-lookup"><span data-stu-id="7183e-106">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="7183e-107">uguale a: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7183e-107">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7183e-108">Funzione dalla tupla `('T, 'T)` a `Bool` utilizzata per verificare se due elementi delle matrici sono uguali.</span><span class="sxs-lookup"><span data-stu-id="7183e-108">A function from tuple `('T, 'T)` to `Bool` that is used to check whether two elements of arrays are equal.</span></span>


### <a name="array1--t"></a><span data-ttu-id="7183e-109">Matrice1:' t []</span><span class="sxs-lookup"><span data-stu-id="7183e-109">array1 : 'T[]</span></span>

<span data-ttu-id="7183e-110">Prima matrice da confrontare.</span><span class="sxs-lookup"><span data-stu-id="7183e-110">The first array to be compared.</span></span>


### <a name="array2--t"></a><span data-ttu-id="7183e-111">Matrice2:' t []</span><span class="sxs-lookup"><span data-stu-id="7183e-111">array2 : 'T[]</span></span>

<span data-ttu-id="7183e-112">Seconda matrice da confrontare.</span><span class="sxs-lookup"><span data-stu-id="7183e-112">The second array to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="7183e-113">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7183e-113">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7183e-114">Valore `true` se e solo se `array1` e `array2` sono uguali.</span><span class="sxs-lookup"><span data-stu-id="7183e-114">The value `true` if and only if `array1` and `array2` are equal.</span></span>
<span data-ttu-id="7183e-115">Ovvero, se entrambe le matrici hanno la stessa lunghezza e tutti gli elementi sono uguali a quanto definito da `equal` .</span><span class="sxs-lookup"><span data-stu-id="7183e-115">That is, if both arrays have the same length, and all elements are equal as defined by `equal`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7183e-116">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="7183e-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7183e-117">T</span><span class="sxs-lookup"><span data-stu-id="7183e-117">'T</span></span>

<span data-ttu-id="7183e-118">Tipo di elementi di ogni matrice.</span><span class="sxs-lookup"><span data-stu-id="7183e-118">The type of each array's elements.</span></span>

## <a name="example"></a><span data-ttu-id="7183e-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="7183e-119">Example</span></span>

<span data-ttu-id="7183e-120">Il codice seguente controlla se coppie di matrici diverse sono uguali:</span><span class="sxs-lookup"><span data-stu-id="7183e-120">The following code checks whether different pairs of arrays are equal:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function EqualADemo() : Unit {
    let equalArrays = EqualA(EqualI, [2, 3, 4], [2, 3, 4]);
    let differentLength = EqualA(EqualD, [2.0, 3.0, 4.0], [2.0, 3.0]);
    let differentElements = EqualA(EqualR, [One, Zero], [One, One]);
    Message($"Equal arrays are {equalArrays ? "equal" | "not equal"}");
    Message($"Arrays of different length are {differentLength ? "equal" | "not equal"}");
    Message($"Arrays of the same length with different elements are {differentElements ? "equal" | "not equal"}");
}
```

## <a name="remarks"></a><span data-ttu-id="7183e-121">Commenti</span><span class="sxs-lookup"><span data-stu-id="7183e-121">Remarks</span></span>

<span data-ttu-id="7183e-122">Questa funzione è definita per i tipi generici; ad esempio, ogni volta che sono presenti due matrici `'T[]` e una funzione `equal: ('T, 'T) -> Bool` , questa funzione restituisce un `Bool` valore che indica se le matrici sono uguali.</span><span class="sxs-lookup"><span data-stu-id="7183e-122">This function is defined for generic types; i.e., whenever we have two arrays `'T[]` and a function `equal: ('T, 'T) -> Bool`, this function returns a `Bool` value that indicates whether the arrays are equal.</span></span>
<span data-ttu-id="7183e-123">Affinché due matrici siano considerate uguali, devono avere la stessa lunghezza e gli elementi nelle stesse posizioni nelle matrici devono essere uguali.</span><span class="sxs-lookup"><span data-stu-id="7183e-123">For two arrays to be considered equal, they have to have equal length and the elements in the same positions in the arrays have to be equal.</span></span>
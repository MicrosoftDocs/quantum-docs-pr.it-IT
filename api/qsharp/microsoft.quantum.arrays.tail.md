---
uid: Microsoft.Quantum.Arrays.Tail
title: Tail - funzione
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 7a1eb2afefd662f90e58798b56bc83b34ac2abfd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718818"
---
# <a name="tail-function"></a><span data-ttu-id="0b1df-102">Tail - funzione</span><span class="sxs-lookup"><span data-stu-id="0b1df-102">Tail function</span></span>

<span data-ttu-id="0b1df-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0b1df-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0b1df-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0b1df-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0b1df-105">Restituisce l'ultimo elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="0b1df-105">Returns the last element of the array.</span></span>

```qsharp
function Tail<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="0b1df-106">Input</span><span class="sxs-lookup"><span data-stu-id="0b1df-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="0b1df-107">array:' A []</span><span class="sxs-lookup"><span data-stu-id="0b1df-107">array : 'A[]</span></span>

<span data-ttu-id="0b1df-108">Matrice di cui viene utilizzato l'ultimo elemento.</span><span class="sxs-lookup"><span data-stu-id="0b1df-108">Array of which the last element is taken.</span></span> <span data-ttu-id="0b1df-109">La matrice deve avere una lunghezza almeno pari a 1.</span><span class="sxs-lookup"><span data-stu-id="0b1df-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="0b1df-110">Output:' A</span><span class="sxs-lookup"><span data-stu-id="0b1df-110">Output : 'A</span></span>

<span data-ttu-id="0b1df-111">Ultimo elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="0b1df-111">The last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0b1df-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="0b1df-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="0b1df-113">' A</span><span class="sxs-lookup"><span data-stu-id="0b1df-113">'A</span></span>

<span data-ttu-id="0b1df-114">Tipo degli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="0b1df-114">The type of the array elements.</span></span>
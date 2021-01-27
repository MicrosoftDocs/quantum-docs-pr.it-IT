---
uid: Microsoft.Quantum.Arithmetic.IdenticalPointPosFactFxP
title: IdenticalPointPosFactFxP (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalPointPosFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit. I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.
ms.openlocfilehash: 7212f918e1d0ee86b12b85caa6e0c27bc2cebe58
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846608"
---
# <a name="identicalpointposfactfxp-function"></a><span data-ttu-id="43fed-102">IdenticalPointPosFactFxP (funzione)</span><span class="sxs-lookup"><span data-stu-id="43fed-102">IdenticalPointPosFactFxP function</span></span>

<span data-ttu-id="43fed-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="43fed-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="43fed-104">Pacchetto: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="43fed-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="43fed-105">Dichiarare che tutti i numeri a virgola fissa nella matrice fornita hanno posizioni di punti identiche quando si esegue il conteggio dal bit meno significativo.</span><span class="sxs-lookup"><span data-stu-id="43fed-105">Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit.</span></span> <span data-ttu-id="43fed-106">Ovvero, il numero di bit meno punti deve essere costante per tutti i numeri a virgola fissa nella matrice.</span><span class="sxs-lookup"><span data-stu-id="43fed-106">I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.</span></span>

```qsharp
function IdenticalPointPosFactFxP (fixedPoints : Microsoft.Quantum.Arithmetic.FixedPoint[]) : Unit
```


## <a name="input"></a><span data-ttu-id="43fed-107">Input</span><span class="sxs-lookup"><span data-stu-id="43fed-107">Input</span></span>

### <a name="fixedpoints--fixedpoint"></a><span data-ttu-id="43fed-108">fixedPoints: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span><span class="sxs-lookup"><span data-stu-id="43fed-108">fixedPoints : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span></span>

<span data-ttu-id="43fed-109">Matrice di numeri a virgola fissa di Quantum di cui verrà verificata la compatibilità (usando le asserzioni).</span><span class="sxs-lookup"><span data-stu-id="43fed-109">Array of quantum fixed-point numbers that will be checked for compatibility (using assertions).</span></span>



## <a name="output--unit"></a><span data-ttu-id="43fed-110">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="43fed-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


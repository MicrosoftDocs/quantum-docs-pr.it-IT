---
uid: Microsoft.Quantum.Arithmetic.IdenticalPointPosFactFxP
title: IdenticalPointPosFactFxP (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalPointPosFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit. I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.
ms.openlocfilehash: 0b285ce980ca1abbc3eb20838389a6f49835e742
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721119"
---
# <a name="identicalpointposfactfxp-function"></a><span data-ttu-id="84541-102">IdenticalPointPosFactFxP (funzione)</span><span class="sxs-lookup"><span data-stu-id="84541-102">IdenticalPointPosFactFxP function</span></span>

<span data-ttu-id="84541-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="84541-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="84541-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="84541-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="84541-105">Dichiarare che tutti i numeri a virgola fissa nella matrice fornita hanno posizioni di punti identiche quando si esegue il conteggio dal bit meno significativo.</span><span class="sxs-lookup"><span data-stu-id="84541-105">Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit.</span></span> <span data-ttu-id="84541-106">Ovvero, il numero di bit meno punti deve essere costante per tutti i numeri a virgola fissa nella matrice.</span><span class="sxs-lookup"><span data-stu-id="84541-106">I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.</span></span>

```qsharp
function IdenticalPointPosFactFxP (fixedPoints : Microsoft.Quantum.Arithmetic.FixedPoint[]) : Unit
```


## <a name="input"></a><span data-ttu-id="84541-107">Input</span><span class="sxs-lookup"><span data-stu-id="84541-107">Input</span></span>

### <a name="fixedpoints--fixedpoint"></a><span data-ttu-id="84541-108">fixedPoints: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span><span class="sxs-lookup"><span data-stu-id="84541-108">fixedPoints : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span></span>

<span data-ttu-id="84541-109">Matrice di numeri a virgola fissa di Quantum di cui verrà verificata la compatibilità (usando le asserzioni).</span><span class="sxs-lookup"><span data-stu-id="84541-109">Array of quantum fixed-point numbers that will be checked for compatibility (using assertions).</span></span>



## <a name="output--unit"></a><span data-ttu-id="84541-110">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="84541-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


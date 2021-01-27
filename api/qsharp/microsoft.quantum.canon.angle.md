---
uid: Microsoft.Quantum.Canon.Angle
title: Angle (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: 0528f21b2d9c98b6497e28741964e6497d4d0fb9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842048"
---
# <a name="angle-function"></a><span data-ttu-id="ac8b1-102">Angle (funzione)</span><span class="sxs-lookup"><span data-stu-id="ac8b1-102">Angle function</span></span>

<span data-ttu-id="ac8b1-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ac8b1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ac8b1-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ac8b1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ac8b1-105">Restituisce 1, se `index` ha un numero dispari di 1s e-1, se `index` ha un numero pari di 1s.</span><span class="sxs-lookup"><span data-stu-id="ac8b1-105">Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.</span></span>

```qsharp
function Angle (index : Int) : Int
```


## <a name="description"></a><span data-ttu-id="ac8b1-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ac8b1-106">Description</span></span>

<span data-ttu-id="ac8b1-107">Il valore corrisponde al segno del coefficiente dello spettro di Rademacher-Walsh della variabile n e della funzione per una determinata assegnazione che decide l'angolo della rotazione.</span><span class="sxs-lookup"><span data-stu-id="ac8b1-107">Value corresponds to the sign of the coefficient of the Rademacher-Walsh spectrum of the n-variable AND function for a given assignment that decides the angle of the rotation.</span></span>

## <a name="input"></a><span data-ttu-id="ac8b1-108">Input</span><span class="sxs-lookup"><span data-stu-id="ac8b1-108">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="ac8b1-109">Indice: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ac8b1-109">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ac8b1-110">Assegnazione di input come Integer (da 0 a 2 ^ n-1)</span><span class="sxs-lookup"><span data-stu-id="ac8b1-110">Input assignment as integer (from 0 to 2^n - 1)</span></span>



## <a name="output--int"></a><span data-ttu-id="ac8b1-111">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ac8b1-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>


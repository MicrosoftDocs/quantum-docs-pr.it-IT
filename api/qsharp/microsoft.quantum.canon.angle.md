---
uid: Microsoft.Quantum.Canon.Angle
title: Angle (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: da3ecdaf1b2c88180bd2a660fac0b6e87b2cafa1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718491"
---
# <a name="angle-function"></a><span data-ttu-id="387b7-102">Angle (funzione)</span><span class="sxs-lookup"><span data-stu-id="387b7-102">Angle function</span></span>

<span data-ttu-id="387b7-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="387b7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="387b7-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="387b7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="387b7-105">Restituisce 1, se `index` ha un numero dispari di 1s e-1, se `index` ha un numero pari di 1s.</span><span class="sxs-lookup"><span data-stu-id="387b7-105">Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.</span></span>

```qsharp
function Angle (index : Int) : Int
```


## <a name="description"></a><span data-ttu-id="387b7-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="387b7-106">Description</span></span>

<span data-ttu-id="387b7-107">Il valore corrisponde al segno del coefficiente dello spettro di Rademacher-Walsh della variabile n e della funzione per una determinata assegnazione che decide l'angolo della rotazione.</span><span class="sxs-lookup"><span data-stu-id="387b7-107">Value corresponds to the sign of the coefficient of the Rademacher-Walsh spectrum of the n-variable AND function for a given assignment that decides the angle of the rotation.</span></span>

## <a name="input"></a><span data-ttu-id="387b7-108">Input</span><span class="sxs-lookup"><span data-stu-id="387b7-108">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="387b7-109">Indice: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="387b7-109">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="387b7-110">Assegnazione di input come Integer (da 0 a 2 ^ n-1)</span><span class="sxs-lookup"><span data-stu-id="387b7-110">Input assignment as integer (from 0 to 2^n - 1)</span></span>



## <a name="output--int"></a><span data-ttu-id="387b7-111">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="387b7-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>


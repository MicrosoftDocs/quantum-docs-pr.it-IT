---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: NearEqualityFactD (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: d632a7a12c9ebbebfbc7939f2b8a24de8ae1ba2a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827904"
---
# <a name="nearequalityfactd-function"></a><span data-ttu-id="cdfb7-102">NearEqualityFactD (funzione)</span><span class="sxs-lookup"><span data-stu-id="cdfb7-102">NearEqualityFactD function</span></span>

<span data-ttu-id="cdfb7-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="cdfb7-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="cdfb7-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cdfb7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cdfb7-105">Dichiara che un valore a virgola mobile classico ha il valore previsto fino a una piccola tolleranza di 1E-10.</span><span class="sxs-lookup"><span data-stu-id="cdfb7-105">Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.</span></span>

```qsharp
function NearEqualityFactD (actual : Double, expected : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="cdfb7-106">Input</span><span class="sxs-lookup"><span data-stu-id="cdfb7-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="cdfb7-107">effettivo: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cdfb7-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cdfb7-108">Numero da verificare.</span><span class="sxs-lookup"><span data-stu-id="cdfb7-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="cdfb7-109">previsto: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cdfb7-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cdfb7-110">Valore previsto.</span><span class="sxs-lookup"><span data-stu-id="cdfb7-110">The expected value.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cdfb7-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cdfb7-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="cdfb7-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="cdfb7-112">Remarks</span></span>

<span data-ttu-id="cdfb7-113">Equivale a con la <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> tolleranza hardcoded di $10 ^ {-10} $.</span><span class="sxs-lookup"><span data-stu-id="cdfb7-113">This is equivalent to <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> with hardcoded tolerance of $10^{-10}$.</span></span>
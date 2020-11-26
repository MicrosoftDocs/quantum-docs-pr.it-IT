---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: NearEqualityFactD (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 5acfe5043342fd88276910a9fd0347f7d2f6960f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201513"
---
# <a name="nearequalityfactd-function"></a><span data-ttu-id="b1c40-102">NearEqualityFactD (funzione)</span><span class="sxs-lookup"><span data-stu-id="b1c40-102">NearEqualityFactD function</span></span>

<span data-ttu-id="b1c40-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="b1c40-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="b1c40-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b1c40-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b1c40-105">Dichiara che un valore a virgola mobile classico ha il valore previsto fino a una piccola tolleranza di 1E-10.</span><span class="sxs-lookup"><span data-stu-id="b1c40-105">Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.</span></span>

```qsharp
function NearEqualityFactD (actual : Double, expected : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="b1c40-106">Input</span><span class="sxs-lookup"><span data-stu-id="b1c40-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="b1c40-107">effettivo: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b1c40-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b1c40-108">Numero da verificare.</span><span class="sxs-lookup"><span data-stu-id="b1c40-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="b1c40-109">previsto: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b1c40-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b1c40-110">Valore previsto.</span><span class="sxs-lookup"><span data-stu-id="b1c40-110">The expected value.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b1c40-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b1c40-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b1c40-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="b1c40-112">Remarks</span></span>

<span data-ttu-id="b1c40-113">Equivale a con la <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> tolleranza hardcoded di $10 ^ {-10} $.</span><span class="sxs-lookup"><span data-stu-id="b1c40-113">This is equivalent to <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> with hardcoded tolerance of $10^{-10}$.</span></span>
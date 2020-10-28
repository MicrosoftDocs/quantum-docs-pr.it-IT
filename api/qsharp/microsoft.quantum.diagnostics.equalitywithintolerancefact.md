---
uid: Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact
title: EqualityWithinToleranceFact (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityWithinToleranceFact
qsharp.summary: Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.
ms.openlocfilehash: de15a32d5b38c5ab8c681d2c052669a48cf676cc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712746"
---
# <a name="equalitywithintolerancefact-function"></a><span data-ttu-id="27904-102">EqualityWithinToleranceFact (funzione)</span><span class="sxs-lookup"><span data-stu-id="27904-102">EqualityWithinToleranceFact function</span></span>

<span data-ttu-id="27904-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="27904-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="27904-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="27904-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="27904-105">Rappresenta l'attestazione che un valore a virgola mobile classico ha il valore previsto fino a una tolleranza assoluta specificata.</span><span class="sxs-lookup"><span data-stu-id="27904-105">Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.</span></span>

```qsharp
function EqualityWithinToleranceFact (actual : Double, expected : Double, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="27904-106">Input</span><span class="sxs-lookup"><span data-stu-id="27904-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="27904-107">effettivo: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="27904-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="27904-108">Numero da verificare.</span><span class="sxs-lookup"><span data-stu-id="27904-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="27904-109">previsto: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="27904-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="27904-110">Valore previsto.</span><span class="sxs-lookup"><span data-stu-id="27904-110">The expected value.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="27904-111">tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="27904-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="27904-112">Tolleranza assoluta sulla differenza tra il valore effettivo e quello previsto.</span><span class="sxs-lookup"><span data-stu-id="27904-112">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="27904-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="27904-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


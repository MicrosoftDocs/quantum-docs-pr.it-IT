---
uid: Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact
title: EqualityWithinToleranceFact (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityWithinToleranceFact
qsharp.summary: Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.
ms.openlocfilehash: ab7e43d951bf741926b15f27f94d176e88609d4a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98828759"
---
# <a name="equalitywithintolerancefact-function"></a><span data-ttu-id="5cad1-102">EqualityWithinToleranceFact (funzione)</span><span class="sxs-lookup"><span data-stu-id="5cad1-102">EqualityWithinToleranceFact function</span></span>

<span data-ttu-id="5cad1-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="5cad1-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="5cad1-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5cad1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5cad1-105">Rappresenta l'attestazione che un valore a virgola mobile classico ha il valore previsto fino a una tolleranza assoluta specificata.</span><span class="sxs-lookup"><span data-stu-id="5cad1-105">Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.</span></span>

```qsharp
function EqualityWithinToleranceFact (actual : Double, expected : Double, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="5cad1-106">Input</span><span class="sxs-lookup"><span data-stu-id="5cad1-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="5cad1-107">effettivo: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5cad1-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5cad1-108">Numero da verificare.</span><span class="sxs-lookup"><span data-stu-id="5cad1-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="5cad1-109">previsto: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5cad1-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5cad1-110">Valore previsto.</span><span class="sxs-lookup"><span data-stu-id="5cad1-110">The expected value.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="5cad1-111">tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5cad1-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5cad1-112">Tolleranza assoluta sulla differenza tra il valore effettivo e quello previsto.</span><span class="sxs-lookup"><span data-stu-id="5cad1-112">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5cad1-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5cad1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


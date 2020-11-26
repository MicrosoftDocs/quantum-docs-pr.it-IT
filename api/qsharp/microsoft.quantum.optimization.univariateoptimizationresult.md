---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: Tipo definito dall'utente UnivariateOptimizationResult
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: 0bcdbda5586181f965297cb2a398d766f9c6fabb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194033"
---
# <a name="univariateoptimizationresult-user-defined-type"></a><span data-ttu-id="804e4-102">Tipo definito dall'utente UnivariateOptimizationResult</span><span class="sxs-lookup"><span data-stu-id="804e4-102">UnivariateOptimizationResult user defined type</span></span>

<span data-ttu-id="804e4-103">Spazio dei nomi: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="804e4-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="804e4-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="804e4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="804e4-105">Rappresenta il risultato dell'ottimizzazione di una funzione univariata.</span><span class="sxs-lookup"><span data-stu-id="804e4-105">Represents the result of optimizing a univariate function.</span></span>

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a><span data-ttu-id="804e4-106">Elementi denominati</span><span class="sxs-lookup"><span data-stu-id="804e4-106">Named Items</span></span>

### <a name="coordinate--double"></a><span data-ttu-id="804e4-107">Coordinata: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="804e4-107">Coordinate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="804e4-108">Input in corrispondenza del quale è stato trovato un risultato ottimale.</span><span class="sxs-lookup"><span data-stu-id="804e4-108">Input at which an optimum was found.</span></span>
### <a name="value--double"></a><span data-ttu-id="804e4-109">Valore: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="804e4-109">Value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="804e4-110">Valore restituito dalla funzione al suo Optimum.</span><span class="sxs-lookup"><span data-stu-id="804e4-110">Value returned by the function at its optimum.</span></span>
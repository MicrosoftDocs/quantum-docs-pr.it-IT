---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: Tipo definito dall'utente UnivariateOptimizationResult
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: c8aa91bbdc9e9e9bb4d110b470ff2041f9460a38
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724325"
---
# <a name="univariateoptimizationresult-user-defined-type"></a><span data-ttu-id="a9188-102">Tipo definito dall'utente UnivariateOptimizationResult</span><span class="sxs-lookup"><span data-stu-id="a9188-102">UnivariateOptimizationResult user defined type</span></span>

<span data-ttu-id="a9188-103">Spazio dei nomi: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="a9188-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="a9188-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a9188-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a9188-105">Rappresenta il risultato dell'ottimizzazione di una funzione univariata.</span><span class="sxs-lookup"><span data-stu-id="a9188-105">Represents the result of optimizing a univariate function.</span></span>

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a><span data-ttu-id="a9188-106">Elementi denominati</span><span class="sxs-lookup"><span data-stu-id="a9188-106">Named Items</span></span>

### <a name="coordinate--double"></a><span data-ttu-id="a9188-107">Coordinata: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a9188-107">Coordinate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a9188-108">Input in corrispondenza del quale è stato trovato un risultato ottimale.</span><span class="sxs-lookup"><span data-stu-id="a9188-108">Input at which an optimum was found.</span></span>
### <a name="value--double"></a><span data-ttu-id="a9188-109">Valore: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a9188-109">Value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a9188-110">Valore restituito dalla funzione al suo Optimum.</span><span class="sxs-lookup"><span data-stu-id="a9188-110">Value returned by the function at its optimum.</span></span>
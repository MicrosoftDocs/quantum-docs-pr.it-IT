---
uid: Microsoft.Quantum.Optimization.LocalUnivariateMinimum
title: LocalUnivariateMinimum (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: LocalUnivariateMinimum
qsharp.summary: Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.
ms.openlocfilehash: 3b09af88bbed20a392768d005e5e9567b3bb7022
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711021"
---
# <a name="localunivariateminimum-function"></a><span data-ttu-id="fe56c-102">LocalUnivariateMinimum (funzione)</span><span class="sxs-lookup"><span data-stu-id="fe56c-102">LocalUnivariateMinimum function</span></span>

<span data-ttu-id="fe56c-103">Spazio dei nomi: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="fe56c-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="fe56c-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fe56c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fe56c-105">Restituisce il valore minimo locale per una funzione univariata su un intervallo delimitato, usando una ricerca con intervallo dorato.</span><span class="sxs-lookup"><span data-stu-id="fe56c-105">Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.</span></span>

```qsharp
function LocalUnivariateMinimum (fn : (Double -> Double), bounds : (Double, Double), tolerance : Double) : Microsoft.Quantum.Optimization.UnivariateOptimizationResult
```


## <a name="input"></a><span data-ttu-id="fe56c-106">Input</span><span class="sxs-lookup"><span data-stu-id="fe56c-106">Input</span></span>

### <a name="fn--double---double"></a><span data-ttu-id="fe56c-107">FN: [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fe56c-107">fn : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fe56c-108">Funzione univariata da ridurre a icona.</span><span class="sxs-lookup"><span data-stu-id="fe56c-108">The univariate function to be minimized.</span></span>


### <a name="bounds--doubledouble"></a><span data-ttu-id="fe56c-109">limiti: ([Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))</span><span class="sxs-lookup"><span data-stu-id="fe56c-109">bounds : ([Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))</span></span>

<span data-ttu-id="fe56c-110">Intervallo nel quale deve essere trovato il valore minimo locale.</span><span class="sxs-lookup"><span data-stu-id="fe56c-110">The interval in which the local minimum is to be found.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="fe56c-111">tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fe56c-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fe56c-112">Accuratezza nell'input della funzione da tollerare.</span><span class="sxs-lookup"><span data-stu-id="fe56c-112">The accuracy in the function input to be tolerated.</span></span>
<span data-ttu-id="fe56c-113">La ricerca di Optima locale continuerà fino a quando l'intervallo non sarà più piccolo in larghezza rispetto a questa tolleranza.</span><span class="sxs-lookup"><span data-stu-id="fe56c-113">The search for local optima will continue until the interval is smaller in width than this tolerance.</span></span>



## <a name="output--univariateoptimizationresult"></a><span data-ttu-id="fe56c-114">Output: [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span><span class="sxs-lookup"><span data-stu-id="fe56c-114">Output : [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span></span>

<span data-ttu-id="fe56c-115">Optima locale della funzione specificata, che si trova all'interno dei limiti specificati.</span><span class="sxs-lookup"><span data-stu-id="fe56c-115">A local optima of the given function, located within the given bounds.</span></span>
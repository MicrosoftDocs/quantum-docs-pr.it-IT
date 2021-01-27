---
uid: Microsoft.Quantum.Optimization.LocalUnivariateMinimum
title: LocalUnivariateMinimum (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: LocalUnivariateMinimum
qsharp.summary: Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.
ms.openlocfilehash: c2d094a6d0e0c7cecb249cd517995e11dff3d3b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854601"
---
# <a name="localunivariateminimum-function"></a><span data-ttu-id="ec9eb-102">LocalUnivariateMinimum (funzione)</span><span class="sxs-lookup"><span data-stu-id="ec9eb-102">LocalUnivariateMinimum function</span></span>

<span data-ttu-id="ec9eb-103">Spazio dei nomi: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="ec9eb-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="ec9eb-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ec9eb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ec9eb-105">Restituisce il valore minimo locale per una funzione univariata su un intervallo delimitato, usando una ricerca con intervallo dorato.</span><span class="sxs-lookup"><span data-stu-id="ec9eb-105">Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.</span></span>

```qsharp
function LocalUnivariateMinimum (fn : (Double -> Double), bounds : (Double, Double), tolerance : Double) : Microsoft.Quantum.Optimization.UnivariateOptimizationResult
```


## <a name="input"></a><span data-ttu-id="ec9eb-106">Input</span><span class="sxs-lookup"><span data-stu-id="ec9eb-106">Input</span></span>

### <a name="fn--double---double"></a><span data-ttu-id="ec9eb-107">FN: [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ec9eb-107">fn : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ec9eb-108">Funzione univariata da ridurre a icona.</span><span class="sxs-lookup"><span data-stu-id="ec9eb-108">The univariate function to be minimized.</span></span>


### <a name="bounds--doubledouble"></a><span data-ttu-id="ec9eb-109">limiti: ([Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))</span><span class="sxs-lookup"><span data-stu-id="ec9eb-109">bounds : ([Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))</span></span>

<span data-ttu-id="ec9eb-110">Intervallo nel quale deve essere trovato il valore minimo locale.</span><span class="sxs-lookup"><span data-stu-id="ec9eb-110">The interval in which the local minimum is to be found.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="ec9eb-111">tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ec9eb-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ec9eb-112">Accuratezza nell'input della funzione da tollerare.</span><span class="sxs-lookup"><span data-stu-id="ec9eb-112">The accuracy in the function input to be tolerated.</span></span>
<span data-ttu-id="ec9eb-113">La ricerca di Optima locale continuerà fino a quando l'intervallo non sarà più piccolo in larghezza rispetto a questa tolleranza.</span><span class="sxs-lookup"><span data-stu-id="ec9eb-113">The search for local optima will continue until the interval is smaller in width than this tolerance.</span></span>



## <a name="output--univariateoptimizationresult"></a><span data-ttu-id="ec9eb-114">Output: [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span><span class="sxs-lookup"><span data-stu-id="ec9eb-114">Output : [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span></span>

<span data-ttu-id="ec9eb-115">Optima locale della funzione specificata, che si trova all'interno dei limiti specificati.</span><span class="sxs-lookup"><span data-stu-id="ec9eb-115">A local optima of the given function, located within the given bounds.</span></span>
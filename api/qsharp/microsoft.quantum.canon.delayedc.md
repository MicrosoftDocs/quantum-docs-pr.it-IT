---
uid: Microsoft.Quantum.Canon.DelayedC
title: DelayedC (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 7cfd77b0bb2d91c5a1c4bb5bc84e052421d733a9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716215"
---
# <a name="delayedc-function"></a><span data-ttu-id="45c76-102">DelayedC (funzione)</span><span class="sxs-lookup"><span data-stu-id="45c76-102">DelayedC function</span></span>

<span data-ttu-id="45c76-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="45c76-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="45c76-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="45c76-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="45c76-105">Restituisce un'operazione che applica l'operazione specificata con l'argomento specificato.</span><span class="sxs-lookup"><span data-stu-id="45c76-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="45c76-106">Input</span><span class="sxs-lookup"><span data-stu-id="45c76-106">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="45c76-107">op:' t => CTL [unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="45c76-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="45c76-108">Operazione da applicare in seguito all'applicazione del valore restituito</span><span class="sxs-lookup"><span data-stu-id="45c76-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="45c76-109">ARG:' t</span><span class="sxs-lookup"><span data-stu-id="45c76-109">arg : 'T</span></span>

<span data-ttu-id="45c76-110">Input a cui `op` viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="45c76-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit-ctl"></a><span data-ttu-id="45c76-111">Output: [Unit](xref:microsoft.quantum.lang-ref.unit) => [unità](xref:microsoft.quantum.lang-ref.unit) di unità CTL</span><span class="sxs-lookup"><span data-stu-id="45c76-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="45c76-112">Nuova operazione applicata con l' `op` input `arg`</span><span class="sxs-lookup"><span data-stu-id="45c76-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="45c76-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="45c76-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="45c76-114">T</span><span class="sxs-lookup"><span data-stu-id="45c76-114">'T</span></span>

<span data-ttu-id="45c76-115">Tipo di input dell'operazione da ritardare.</span><span class="sxs-lookup"><span data-stu-id="45c76-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="45c76-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45c76-116">See Also</span></span>

- [<span data-ttu-id="45c76-117">Microsoft. Quantum. Canon. Delayed</span><span class="sxs-lookup"><span data-stu-id="45c76-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="45c76-118">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="45c76-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
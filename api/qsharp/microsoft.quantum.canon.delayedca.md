---
uid: Microsoft.Quantum.Canon.DelayedCA
title: DelayedCA (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedCA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: c44e3448c471f2a20f995d4546ee54f3affb726e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840542"
---
# <a name="delayedca-function"></a><span data-ttu-id="40389-102">DelayedCA (funzione)</span><span class="sxs-lookup"><span data-stu-id="40389-102">DelayedCA function</span></span>

<span data-ttu-id="40389-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="40389-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="40389-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="40389-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="40389-105">Restituisce un'operazione che applica l'operazione specificata con l'argomento specificato.</span><span class="sxs-lookup"><span data-stu-id="40389-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T) : (Unit => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="40389-106">Input</span><span class="sxs-lookup"><span data-stu-id="40389-106">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="40389-107">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="40389-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="40389-108">Operazione da applicare in seguito all'applicazione del valore restituito</span><span class="sxs-lookup"><span data-stu-id="40389-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="40389-109">ARG:' t</span><span class="sxs-lookup"><span data-stu-id="40389-109">arg : 'T</span></span>

<span data-ttu-id="40389-110">Input a cui `op` viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="40389-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit--is-adj--ctl"></a><span data-ttu-id="40389-111">Output: [](xref:microsoft.quantum.lang-ref.unit) => [unità](xref:microsoft.quantum.lang-ref.unit) unità è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="40389-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="40389-112">Nuova operazione applicata con l' `op` input `arg`</span><span class="sxs-lookup"><span data-stu-id="40389-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="40389-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="40389-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="40389-114">T</span><span class="sxs-lookup"><span data-stu-id="40389-114">'T</span></span>

<span data-ttu-id="40389-115">Tipo di input dell'operazione da ritardare.</span><span class="sxs-lookup"><span data-stu-id="40389-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="40389-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40389-116">See Also</span></span>

- [<span data-ttu-id="40389-117">Microsoft. Quantum. Canon. Delayed</span><span class="sxs-lookup"><span data-stu-id="40389-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="40389-118">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="40389-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
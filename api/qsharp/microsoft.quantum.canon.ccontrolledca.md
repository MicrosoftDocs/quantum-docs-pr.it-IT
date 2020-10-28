---
uid: Microsoft.Quantum.Canon.CControlledCA
title: CControlledCA (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledCA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 20a8c9ccf931261f7bc6e347ccc144c92f0d0545
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716568"
---
# <a name="ccontrolledca-function"></a><span data-ttu-id="5d83c-102">CControlledCA (funzione)</span><span class="sxs-lookup"><span data-stu-id="5d83c-102">CControlledCA function</span></span>

<span data-ttu-id="5d83c-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5d83c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5d83c-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5d83c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5d83c-105">Data un'operazione operativa, restituisce una nuova operazione che applica l'op se un bit del controllo classico è true.</span><span class="sxs-lookup"><span data-stu-id="5d83c-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="5d83c-106">Se `false` , non viene eseguita alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="5d83c-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="5d83c-107">Il modificatore `CA` indica che l'operazione è controllabile e adjointable.</span><span class="sxs-lookup"><span data-stu-id="5d83c-107">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
function CControlledCA<'T> (op : ('T => Unit is Ctl + Adj)) : ((Bool, 'T) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="5d83c-108">Input</span><span class="sxs-lookup"><span data-stu-id="5d83c-108">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="5d83c-109">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit) CTL + ADJ</span><span class="sxs-lookup"><span data-stu-id="5d83c-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="5d83c-110">Operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="5d83c-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit-ctl--adj"></a><span data-ttu-id="5d83c-111">Output: ([bool](xref:microsoft.quantum.lang-ref.bool),' t) => [unità](xref:microsoft.quantum.lang-ref.unit) CTL + ADJ</span><span class="sxs-lookup"><span data-stu-id="5d83c-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="5d83c-112">Una nuova operazione che è op se il bit del controllo classico è true.</span><span class="sxs-lookup"><span data-stu-id="5d83c-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5d83c-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="5d83c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5d83c-114">T</span><span class="sxs-lookup"><span data-stu-id="5d83c-114">'T</span></span>

<span data-ttu-id="5d83c-115">Tipo di input dell'operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="5d83c-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="5d83c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d83c-116">See Also</span></span>

- [<span data-ttu-id="5d83c-117">Microsoft. Quantum. Canon. CControlled</span><span class="sxs-lookup"><span data-stu-id="5d83c-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)
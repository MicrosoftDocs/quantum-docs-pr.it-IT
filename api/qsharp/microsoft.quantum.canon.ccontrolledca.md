---
uid: Microsoft.Quantum.Canon.CControlledCA
title: CControlledCA (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledCA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: cc1a783dfbf97afae50f4b42e66cba2b2a2ec833
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207429"
---
# <a name="ccontrolledca-function"></a><span data-ttu-id="1eee7-102">CControlledCA (funzione)</span><span class="sxs-lookup"><span data-stu-id="1eee7-102">CControlledCA function</span></span>

<span data-ttu-id="1eee7-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1eee7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1eee7-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1eee7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1eee7-105">Data un'operazione operativa, restituisce una nuova operazione che applica l'op se un bit del controllo classico è true.</span><span class="sxs-lookup"><span data-stu-id="1eee7-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="1eee7-106">Se `false` , non viene eseguita alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="1eee7-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="1eee7-107">Il modificatore `CA` indica che l'operazione è controllabile e adjointable.</span><span class="sxs-lookup"><span data-stu-id="1eee7-107">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
function CControlledCA<'T> (op : ('T => Unit is Ctl + Adj)) : ((Bool, 'T) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="1eee7-108">Input</span><span class="sxs-lookup"><span data-stu-id="1eee7-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="1eee7-109">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="1eee7-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="1eee7-110">Operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="1eee7-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit--is-adj--ctl"></a><span data-ttu-id="1eee7-111">Output: ([bool](xref:microsoft.quantum.lang-ref.bool),' t) => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="1eee7-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="1eee7-112">Una nuova operazione che è op se il bit del controllo classico è true.</span><span class="sxs-lookup"><span data-stu-id="1eee7-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1eee7-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="1eee7-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1eee7-114">T</span><span class="sxs-lookup"><span data-stu-id="1eee7-114">'T</span></span>

<span data-ttu-id="1eee7-115">Tipo di input dell'operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="1eee7-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="1eee7-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1eee7-116">See Also</span></span>

- [<span data-ttu-id="1eee7-117">Microsoft. Quantum. Canon. CControlled</span><span class="sxs-lookup"><span data-stu-id="1eee7-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)
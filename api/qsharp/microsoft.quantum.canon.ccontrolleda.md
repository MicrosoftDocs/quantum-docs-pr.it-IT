---
uid: Microsoft.Quantum.Canon.CControlledA
title: CControlledA (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 30b5e3408fa6e5a79b2f3d63cccc11899c0405ef
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716582"
---
# <a name="ccontrolleda-function"></a><span data-ttu-id="7dd43-102">CControlledA (funzione)</span><span class="sxs-lookup"><span data-stu-id="7dd43-102">CControlledA function</span></span>

<span data-ttu-id="7dd43-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7dd43-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7dd43-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7dd43-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7dd43-105">Data un'operazione operativa, restituisce una nuova operazione che applica l'op se un bit del controllo classico è true.</span><span class="sxs-lookup"><span data-stu-id="7dd43-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="7dd43-106">Se `false` , non viene eseguita alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="7dd43-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="7dd43-107">Il modificatore `A` indica che l'operazione è adjointable.</span><span class="sxs-lookup"><span data-stu-id="7dd43-107">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
function CControlledA<'T> (op : ('T => Unit is Adj)) : ((Bool, 'T) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="7dd43-108">Input</span><span class="sxs-lookup"><span data-stu-id="7dd43-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="7dd43-109">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="7dd43-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="7dd43-110">Operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="7dd43-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit-adj"></a><span data-ttu-id="7dd43-111">Output: ([bool](xref:microsoft.quantum.lang-ref.bool),' t) => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="7dd43-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="7dd43-112">Una nuova operazione che è op se il bit del controllo classico è true.</span><span class="sxs-lookup"><span data-stu-id="7dd43-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7dd43-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="7dd43-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7dd43-114">T</span><span class="sxs-lookup"><span data-stu-id="7dd43-114">'T</span></span>

<span data-ttu-id="7dd43-115">Tipo di input dell'operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="7dd43-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="7dd43-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7dd43-116">See Also</span></span>

- [<span data-ttu-id="7dd43-117">Microsoft. Quantum. Canon. CControlled</span><span class="sxs-lookup"><span data-stu-id="7dd43-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)
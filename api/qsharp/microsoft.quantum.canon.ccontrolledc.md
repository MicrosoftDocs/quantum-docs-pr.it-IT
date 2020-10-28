---
uid: Microsoft.Quantum.Canon.CControlledC
title: CControlledC (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledC
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: e5975455385e182236d7e2864e26ca00795a40c6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716579"
---
# <a name="ccontrolledc-function"></a><span data-ttu-id="0f4fd-102">CControlledC (funzione)</span><span class="sxs-lookup"><span data-stu-id="0f4fd-102">CControlledC function</span></span>

<span data-ttu-id="0f4fd-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0f4fd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0f4fd-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0f4fd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0f4fd-105">Data un'operazione operativa, restituisce una nuova operazione che applica l'op se un bit del controllo classico è true.</span><span class="sxs-lookup"><span data-stu-id="0f4fd-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="0f4fd-106">Se `false` , non viene eseguita alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="0f4fd-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="0f4fd-107">Il modificatore `C` indica che l'operazione è controllabile.</span><span class="sxs-lookup"><span data-stu-id="0f4fd-107">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
function CControlledC<'T> (op : ('T => Unit is Ctl)) : ((Bool, 'T) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="0f4fd-108">Input</span><span class="sxs-lookup"><span data-stu-id="0f4fd-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="0f4fd-109">op:' t => CTL [unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0f4fd-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="0f4fd-110">Operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="0f4fd-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit-ctl"></a><span data-ttu-id="0f4fd-111">Output: ([bool](xref:microsoft.quantum.lang-ref.bool),' t) => [unità](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="0f4fd-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="0f4fd-112">Una nuova operazione che è op se il bit del controllo classico è true.</span><span class="sxs-lookup"><span data-stu-id="0f4fd-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0f4fd-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="0f4fd-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0f4fd-114">T</span><span class="sxs-lookup"><span data-stu-id="0f4fd-114">'T</span></span>

<span data-ttu-id="0f4fd-115">Tipo di input dell'operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="0f4fd-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="0f4fd-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f4fd-116">See Also</span></span>

- [<span data-ttu-id="0f4fd-117">Microsoft. Quantum. Canon. CControlled</span><span class="sxs-lookup"><span data-stu-id="0f4fd-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)
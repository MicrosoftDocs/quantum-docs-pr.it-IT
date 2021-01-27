---
uid: Microsoft.Quantum.Logical.Conditioned
title: Funzione conditioned
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: ea3b8eba960acceb6540978c6fccd9f796b0f67d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817295"
---
# <a name="conditioned-function"></a><span data-ttu-id="c4499-102">Funzione conditioned</span><span class="sxs-lookup"><span data-stu-id="c4499-102">Conditioned function</span></span>

<span data-ttu-id="c4499-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c4499-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c4499-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c4499-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c4499-105">Restituisce uno di due valori, a seconda del valore di una condizione booleana.</span><span class="sxs-lookup"><span data-stu-id="c4499-105">Returns one of two values, depending on the value of a Boolean condition.</span></span>

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a><span data-ttu-id="c4499-106">Input</span><span class="sxs-lookup"><span data-stu-id="c4499-106">Input</span></span>

### <a name="condition--bool"></a><span data-ttu-id="c4499-107">condizione: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c4499-107">condition : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c4499-108">Condizione utilizzata per controllare quale input viene restituito.</span><span class="sxs-lookup"><span data-stu-id="c4499-108">A condition used to control which input is returned.</span></span>


### <a name="iftrue--t"></a><span data-ttu-id="c4499-109">ifTrue: t</span><span class="sxs-lookup"><span data-stu-id="c4499-109">ifTrue : 'T</span></span>

<span data-ttu-id="c4499-110">Valore da restituire quando `condition` è `true` .</span><span class="sxs-lookup"><span data-stu-id="c4499-110">The value to be returned when `condition` is `true`.</span></span>


### <a name="iffalse--t"></a><span data-ttu-id="c4499-111">ifFalse: t</span><span class="sxs-lookup"><span data-stu-id="c4499-111">ifFalse : 'T</span></span>

<span data-ttu-id="c4499-112">Valore da restituire quando `condition` è `false` .</span><span class="sxs-lookup"><span data-stu-id="c4499-112">The value to be returned when `condition` is `false`.</span></span>



## <a name="output--t"></a><span data-ttu-id="c4499-113">Output:' t</span><span class="sxs-lookup"><span data-stu-id="c4499-113">Output : 'T</span></span>

<span data-ttu-id="c4499-114">`ifTrue` Se `condition` è `true` e `ifFalse` in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="c4499-114">`ifTrue` if `condition` is `true`, and `ifFalse` otherwise.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c4499-115">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="c4499-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c4499-116">T</span><span class="sxs-lookup"><span data-stu-id="c4499-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="c4499-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="c4499-117">Remarks</span></span>

<span data-ttu-id="c4499-118">A differenza dell' `?|` operatore, questa funzione non è a corto circuito, in modo che entrambi gli input siano valutati completamente.</span><span class="sxs-lookup"><span data-stu-id="c4499-118">Unlike the `?|` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="c4499-119">Fino a un comportamento di corto circuito, gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="c4499-119">Up to short-circuiting behavior, the following are equivalent:</span></span>

```qsharp
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```
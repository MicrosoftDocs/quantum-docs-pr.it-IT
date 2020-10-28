---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: 90e9f0c922a77fbb6d6faf8945d4f5d1c8ff33b7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713513"
---
# <a name="functionasoperation-function"></a><span data-ttu-id="2d292-102">FunctionAsOperation (funzione)</span><span class="sxs-lookup"><span data-stu-id="2d292-102">FunctionAsOperation function</span></span>

<span data-ttu-id="2d292-103">Spazio dei nomi: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="2d292-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="2d292-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2d292-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2d292-105">Converte le funzioni in operazioni.</span><span class="sxs-lookup"><span data-stu-id="2d292-105">Converts functions to operations.</span></span>

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a><span data-ttu-id="2d292-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2d292-106">Description</span></span>

<span data-ttu-id="2d292-107">Data una funzione, restituisce un'operazione che chiama tale funzione e che non esegue altre operazioni.</span><span class="sxs-lookup"><span data-stu-id="2d292-107">Given a function, returns an operation which calls that function, and which does nothing else.</span></span>

## <a name="input"></a><span data-ttu-id="2d292-108">Input</span><span class="sxs-lookup"><span data-stu-id="2d292-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="2d292-109">FN: output ' input->'</span><span class="sxs-lookup"><span data-stu-id="2d292-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="2d292-110">Funzione da convertire in un'operazione.</span><span class="sxs-lookup"><span data-stu-id="2d292-110">A function to be converted to an operation.</span></span>



## <a name="output--input--output"></a><span data-ttu-id="2d292-111">Output: output ' input =>'</span><span class="sxs-lookup"><span data-stu-id="2d292-111">Output : 'Input => 'Output</span></span> 

<span data-ttu-id="2d292-112">Operazione `op` analoga `op(input)` a `fn(input)` per tutti `input` .</span><span class="sxs-lookup"><span data-stu-id="2d292-112">An operation `op` such that `op(input)` is identical to `fn(input)` for all `input`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2d292-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="2d292-113">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="2d292-114">' Input</span><span class="sxs-lookup"><span data-stu-id="2d292-114">'Input</span></span>

<span data-ttu-id="2d292-115">Tipo di input della funzione da convertire.</span><span class="sxs-lookup"><span data-stu-id="2d292-115">Input type of the function to be converted.</span></span>
### <a name="output"></a><span data-ttu-id="2d292-116">' Output</span><span class="sxs-lookup"><span data-stu-id="2d292-116">'Output</span></span>

<span data-ttu-id="2d292-117">Tipo di output della funzione da convertire.</span><span class="sxs-lookup"><span data-stu-id="2d292-117">Output type of the function to be converted.</span></span>

## <a name="remarks"></a><span data-ttu-id="2d292-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="2d292-118">Remarks</span></span>

<span data-ttu-id="2d292-119">Questo è particolarmente utile per passare funzioni a funzioni o operazioni che prevedono un'operazione come input.</span><span class="sxs-lookup"><span data-stu-id="2d292-119">This is mainly useful for passing functions to functions or operations which expect an operation as input.</span></span>
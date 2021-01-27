---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: cf4f8c97bf38b3a64eb952d0a502bc21c29c579c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833830"
---
# <a name="functionasoperation-function"></a><span data-ttu-id="84d73-102">FunctionAsOperation (funzione)</span><span class="sxs-lookup"><span data-stu-id="84d73-102">FunctionAsOperation function</span></span>

<span data-ttu-id="84d73-103">Spazio dei nomi: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="84d73-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="84d73-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="84d73-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="84d73-105">Converte le funzioni in operazioni.</span><span class="sxs-lookup"><span data-stu-id="84d73-105">Converts functions to operations.</span></span>

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a><span data-ttu-id="84d73-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84d73-106">Description</span></span>

<span data-ttu-id="84d73-107">Data una funzione, restituisce un'operazione che chiama tale funzione e che non esegue altre operazioni.</span><span class="sxs-lookup"><span data-stu-id="84d73-107">Given a function, returns an operation which calls that function, and which does nothing else.</span></span>

## <a name="input"></a><span data-ttu-id="84d73-108">Input</span><span class="sxs-lookup"><span data-stu-id="84d73-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="84d73-109">FN: output ' input->'</span><span class="sxs-lookup"><span data-stu-id="84d73-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="84d73-110">Funzione da convertire in un'operazione.</span><span class="sxs-lookup"><span data-stu-id="84d73-110">A function to be converted to an operation.</span></span>



## <a name="output--input--output"></a><span data-ttu-id="84d73-111">Output: output ' input =>'</span><span class="sxs-lookup"><span data-stu-id="84d73-111">Output : 'Input => 'Output</span></span> 

<span data-ttu-id="84d73-112">Operazione `op` analoga `op(input)` a `fn(input)` per tutti `input` .</span><span class="sxs-lookup"><span data-stu-id="84d73-112">An operation `op` such that `op(input)` is identical to `fn(input)` for all `input`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="84d73-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="84d73-113">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="84d73-114">' Input</span><span class="sxs-lookup"><span data-stu-id="84d73-114">'Input</span></span>

<span data-ttu-id="84d73-115">Tipo di input della funzione da convertire.</span><span class="sxs-lookup"><span data-stu-id="84d73-115">Input type of the function to be converted.</span></span>
### <a name="output"></a><span data-ttu-id="84d73-116">' Output</span><span class="sxs-lookup"><span data-stu-id="84d73-116">'Output</span></span>

<span data-ttu-id="84d73-117">Tipo di output della funzione da convertire.</span><span class="sxs-lookup"><span data-stu-id="84d73-117">Output type of the function to be converted.</span></span>

## <a name="remarks"></a><span data-ttu-id="84d73-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="84d73-118">Remarks</span></span>

<span data-ttu-id="84d73-119">Questo è particolarmente utile per passare funzioni a funzioni o operazioni che prevedono un'operazione come input.</span><span class="sxs-lookup"><span data-stu-id="84d73-119">This is mainly useful for passing functions to functions or operations which expect an operation as input.</span></span>
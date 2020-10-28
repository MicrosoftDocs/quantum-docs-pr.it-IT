---
uid: Microsoft.Quantum.Convert.Call
title: Operazione di chiamata
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 8630f846b4b9823ce1c1dfd61dc8ca81e468517d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713530"
---
# <a name="call-operation"></a><span data-ttu-id="29a03-102">Operazione di chiamata</span><span class="sxs-lookup"><span data-stu-id="29a03-102">Call operation</span></span>

<span data-ttu-id="29a03-103">Spazio dei nomi: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="29a03-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="29a03-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="29a03-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="29a03-105">Chiama una funzione con un input specificato.</span><span class="sxs-lookup"><span data-stu-id="29a03-105">Calls a function with a given input.</span></span>

```qsharp
operation Call<'Input, 'Output> (fn : ('Input -> 'Output), input : 'Input) : 'Output
```


## <a name="description"></a><span data-ttu-id="29a03-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="29a03-106">Description</span></span>

<span data-ttu-id="29a03-107">Data una funzione e un input per tale funzione, chiama la funzione e ne restituisce l'output.</span><span class="sxs-lookup"><span data-stu-id="29a03-107">Given a function and an input to that function, calls the function and returns its output.</span></span>

## <a name="input"></a><span data-ttu-id="29a03-108">Input</span><span class="sxs-lookup"><span data-stu-id="29a03-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="29a03-109">FN: output ' input->'</span><span class="sxs-lookup"><span data-stu-id="29a03-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="29a03-110">Funzione da chiamare.</span><span class="sxs-lookup"><span data-stu-id="29a03-110">A function to be called.</span></span>


### <a name="input--input"></a><span data-ttu-id="29a03-111">input:' input</span><span class="sxs-lookup"><span data-stu-id="29a03-111">input : 'Input</span></span>

<span data-ttu-id="29a03-112">Input da passare alla funzione.</span><span class="sxs-lookup"><span data-stu-id="29a03-112">The input to be passed to the function.</span></span>



## <a name="output--output"></a><span data-ttu-id="29a03-113">Output:' output</span><span class="sxs-lookup"><span data-stu-id="29a03-113">Output : 'Output</span></span>

<span data-ttu-id="29a03-114">Risultato della chiamata a `fn`.</span><span class="sxs-lookup"><span data-stu-id="29a03-114">The result of calling `fn`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="29a03-115">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="29a03-115">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="29a03-116">' Input</span><span class="sxs-lookup"><span data-stu-id="29a03-116">'Input</span></span>


### <a name="output"></a><span data-ttu-id="29a03-117">' Output</span><span class="sxs-lookup"><span data-stu-id="29a03-117">'Output</span></span>



## <a name="remarks"></a><span data-ttu-id="29a03-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="29a03-118">Remarks</span></span>

<span data-ttu-id="29a03-119">Questa operazione è particolarmente utile per forzare la chiamata di una funzione in una posizione specifica all'interno di un'operazione o per chiamare una funzione in cui è prevista un'operazione.</span><span class="sxs-lookup"><span data-stu-id="29a03-119">This operation is mainly useful for forcing a function to be called at a specific place within an operation, or for calling a function where an operation is expected.</span></span>
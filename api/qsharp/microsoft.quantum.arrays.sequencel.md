---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Sequencel (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5ce63575e703341fce42c0be393765c342bbd89
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718878"
---
# <a name="sequencel-function"></a><span data-ttu-id="dfec9-102">Sequencel (funzione)</span><span class="sxs-lookup"><span data-stu-id="dfec9-102">SequenceL function</span></span>

<span data-ttu-id="dfec9-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="dfec9-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="dfec9-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dfec9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dfec9-105">Ottiene una matrice di numeri interi in un intervallo specificato.</span><span class="sxs-lookup"><span data-stu-id="dfec9-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a><span data-ttu-id="dfec9-106">Input</span><span class="sxs-lookup"><span data-stu-id="dfec9-106">Input</span></span>

### <a name="from--bigint"></a><span data-ttu-id="dfec9-107">da: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="dfec9-107">from : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="dfec9-108">Indice di inizio inclusivo dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="dfec9-108">An inclusive start index of the interval.</span></span>


### <a name="to--bigint"></a><span data-ttu-id="dfec9-109">a: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="dfec9-109">to : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="dfec9-110">Indice finale inclusivo dell'intervallo non più piccolo di `from` .</span><span class="sxs-lookup"><span data-stu-id="dfec9-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="dfec9-111">Output: [bigint](xref:microsoft.quantum.lang-ref.bigint)[]</span><span class="sxs-lookup"><span data-stu-id="dfec9-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span></span>

<span data-ttu-id="dfec9-112">Matrice contenente la sequenza di numeri,,... `from` `from + 1` , `to` .</span><span class="sxs-lookup"><span data-stu-id="dfec9-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>

## <a name="remarks"></a><span data-ttu-id="dfec9-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="dfec9-113">Remarks</span></span>

<span data-ttu-id="dfec9-114">La differenza tra `from` e `to` deve rientrare in un `Int` valore.</span><span class="sxs-lookup"><span data-stu-id="dfec9-114">The difference between `from` and `to` must fit into an `Int` value.</span></span>
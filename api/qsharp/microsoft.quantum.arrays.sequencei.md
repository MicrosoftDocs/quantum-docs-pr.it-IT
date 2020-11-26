---
uid: Microsoft.Quantum.Arrays.SequenceI
title: Sequencei (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 5f03e5f2baff8077c1fa3fb5f1f079528ef0e215
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220298"
---
# <a name="sequencei-function"></a><span data-ttu-id="b3139-102">Sequencei (funzione)</span><span class="sxs-lookup"><span data-stu-id="b3139-102">SequenceI function</span></span>

<span data-ttu-id="b3139-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b3139-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b3139-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b3139-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b3139-105">Ottiene una matrice di numeri interi in un intervallo specificato.</span><span class="sxs-lookup"><span data-stu-id="b3139-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceI (from : Int, to : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="b3139-106">Input</span><span class="sxs-lookup"><span data-stu-id="b3139-106">Input</span></span>

### <a name="from--int"></a><span data-ttu-id="b3139-107">da: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b3139-107">from : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b3139-108">Indice di inizio inclusivo dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="b3139-108">An inclusive start index of the interval.</span></span>


### <a name="to--int"></a><span data-ttu-id="b3139-109">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b3139-109">to : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b3139-110">Indice finale inclusivo dell'intervallo non più piccolo di `from` .</span><span class="sxs-lookup"><span data-stu-id="b3139-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--int"></a><span data-ttu-id="b3139-111">Output: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b3139-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="b3139-112">Matrice contenente la sequenza di numeri,,... `from` `from + 1` , `to` .</span><span class="sxs-lookup"><span data-stu-id="b3139-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>
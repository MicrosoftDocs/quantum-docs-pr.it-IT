---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: b15586c57180b00064721afc990436320824cba2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206885"
---
# <a name="graycode-function"></a><span data-ttu-id="e3aea-102">GrayCode (funzione)</span><span class="sxs-lookup"><span data-stu-id="e3aea-102">GrayCode function</span></span>

<span data-ttu-id="e3aea-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e3aea-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e3aea-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e3aea-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e3aea-105">Crea sequenze di codice grigio</span><span class="sxs-lookup"><span data-stu-id="e3aea-105">Creates Gray code sequences</span></span>

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="e3aea-106">Input</span><span class="sxs-lookup"><span data-stu-id="e3aea-106">Input</span></span>

### <a name="n--int"></a><span data-ttu-id="e3aea-107">n: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e3aea-107">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e3aea-108">Numero di bit</span><span class="sxs-lookup"><span data-stu-id="e3aea-108">Number of bits</span></span>



## <a name="output--intint"></a><span data-ttu-id="e3aea-109">Output: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="e3aea-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="e3aea-110">Matrice di Tuple.</span><span class="sxs-lookup"><span data-stu-id="e3aea-110">Array of tuples.</span></span> <span data-ttu-id="e3aea-111">Il primo valore in tupla è il valore in GrayCode Sequence second value in Tuple è position to change in Current Value per ottenere quello successivo.</span><span class="sxs-lookup"><span data-stu-id="e3aea-111">First value in tuple is value in GrayCode sequence Second value in tuple is position to change in current value to get next one.</span></span>
---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: fc673ae21a952788b5beb74c1bad94ee9fe54480
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716162"
---
# <a name="graycode-function"></a><span data-ttu-id="36277-102">GrayCode (funzione)</span><span class="sxs-lookup"><span data-stu-id="36277-102">GrayCode function</span></span>

<span data-ttu-id="36277-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="36277-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="36277-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="36277-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="36277-105">Crea sequenze di codice grigio</span><span class="sxs-lookup"><span data-stu-id="36277-105">Creates Gray code sequences</span></span>

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="36277-106">Input</span><span class="sxs-lookup"><span data-stu-id="36277-106">Input</span></span>

### <a name="n--int"></a><span data-ttu-id="36277-107">n: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="36277-107">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="36277-108">Numero di bit</span><span class="sxs-lookup"><span data-stu-id="36277-108">Number of bits</span></span>



## <a name="output--intint"></a><span data-ttu-id="36277-109">Output: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="36277-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="36277-110">Matrice di Tuple.</span><span class="sxs-lookup"><span data-stu-id="36277-110">Array of tuples.</span></span> <span data-ttu-id="36277-111">Il primo valore in tupla è il valore in GrayCode Sequence second value in Tuple è position to change in Current Value per ottenere quello successivo.</span><span class="sxs-lookup"><span data-stu-id="36277-111">First value in tuple is value in GrayCode sequence Second value in tuple is position to change in current value to get next one.</span></span>
---
uid: Microsoft.Quantum.Synthesis.Encoded
title: Funzione codificata
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 6b9d21969ee90f3928b65a1c97a5b0f15157e381
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725207"
---
# <a name="encoded-function"></a><span data-ttu-id="c2b02-102">Funzione codificata</span><span class="sxs-lookup"><span data-stu-id="c2b02-102">Encoded function</span></span>

<span data-ttu-id="c2b02-103">Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="c2b02-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="c2b02-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c2b02-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c2b02-105">Codifica della tabella di verità nella {1,-1} codifica</span><span class="sxs-lookup"><span data-stu-id="c2b02-105">Encode truth table in {1,-1} coding</span></span>

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="c2b02-106">Input</span><span class="sxs-lookup"><span data-stu-id="c2b02-106">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="c2b02-107">tabella: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="c2b02-107">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="c2b02-108">Tabella di verità come matrice di valori di verità</span><span class="sxs-lookup"><span data-stu-id="c2b02-108">Truth table as array of truth values</span></span>



## <a name="output--int"></a><span data-ttu-id="c2b02-109">Output: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c2b02-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c2b02-110">Tabella di verità come matrice di {1,-1} numeri interi</span><span class="sxs-lookup"><span data-stu-id="c2b02-110">Truth table as array of {1,-1} integers</span></span>
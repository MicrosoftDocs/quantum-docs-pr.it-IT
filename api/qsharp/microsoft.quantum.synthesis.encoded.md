---
uid: Microsoft.Quantum.Synthesis.Encoded
title: Funzione codificata
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 44f6b247e6bfab7b55c46146cb63f8b6d219955b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855488"
---
# <a name="encoded-function"></a><span data-ttu-id="76960-102">Funzione codificata</span><span class="sxs-lookup"><span data-stu-id="76960-102">Encoded function</span></span>

<span data-ttu-id="76960-103">Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="76960-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="76960-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="76960-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="76960-105">Codifica della tabella di verità nella {1,-1} codifica</span><span class="sxs-lookup"><span data-stu-id="76960-105">Encode truth table in {1,-1} coding</span></span>

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="76960-106">Input</span><span class="sxs-lookup"><span data-stu-id="76960-106">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="76960-107">tabella: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="76960-107">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="76960-108">Tabella di verità come matrice di valori di verità</span><span class="sxs-lookup"><span data-stu-id="76960-108">Truth table as array of truth values</span></span>



## <a name="output--int"></a><span data-ttu-id="76960-109">Output: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="76960-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="76960-110">Tabella di verità come matrice di {1,-1} numeri interi</span><span class="sxs-lookup"><span data-stu-id="76960-110">Truth table as array of {1,-1} integers</span></span>

## <a name="example"></a><span data-ttu-id="76960-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="76960-111">Example</span></span>

```qsharp
Encoded([false, false, false, true]); // [1, 1, 1, -1]
```
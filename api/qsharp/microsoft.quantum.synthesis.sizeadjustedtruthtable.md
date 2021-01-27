---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: SizeAdjustedTruthTable (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: 8d69aa119c25a0f64743fec36c00ecdef2450c44
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855327"
---
# <a name="sizeadjustedtruthtable-function"></a><span data-ttu-id="142e6-102">SizeAdjustedTruthTable (funzione)</span><span class="sxs-lookup"><span data-stu-id="142e6-102">SizeAdjustedTruthTable function</span></span>

<span data-ttu-id="142e6-103">Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="142e6-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="142e6-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="142e6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="142e6-105">Regola la tabella di verità da una matrice di valori booleani in base al numero di variabili</span><span class="sxs-lookup"><span data-stu-id="142e6-105">Adjusts truth table from array of Booleans according to number of variables</span></span>

<span data-ttu-id="142e6-106">Viene restituita una nuova matrice di lunghezza `2^numVars` , che può richiedere l'estensione delle `table` dimensioni con le `false` voci o il troncamento degli `2^numVars` elementi.</span><span class="sxs-lookup"><span data-stu-id="142e6-106">A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.</span></span>

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="142e6-107">Input</span><span class="sxs-lookup"><span data-stu-id="142e6-107">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="142e6-108">tabella: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="142e6-108">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="142e6-109">Tabella di verità come matrice di valori di verità</span><span class="sxs-lookup"><span data-stu-id="142e6-109">Truth table as array of truth values</span></span>


### <a name="numvars--int"></a><span data-ttu-id="142e6-110">numVars: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="142e6-110">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="142e6-111">Numero di variabili</span><span class="sxs-lookup"><span data-stu-id="142e6-111">Number of variables</span></span>



## <a name="output--bool"></a><span data-ttu-id="142e6-112">Output: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="142e6-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="142e6-113">Ridimensionamento della tabella di verità</span><span class="sxs-lookup"><span data-stu-id="142e6-113">Size adjusted truth table</span></span>
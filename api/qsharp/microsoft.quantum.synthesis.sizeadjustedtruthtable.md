---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: SizeAdjustedTruthTable (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: c53ac3f2c46bca955847fc7b380337e3910390ac
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202924"
---
# <a name="sizeadjustedtruthtable-function"></a><span data-ttu-id="4b34e-102">SizeAdjustedTruthTable (funzione)</span><span class="sxs-lookup"><span data-stu-id="4b34e-102">SizeAdjustedTruthTable function</span></span>

<span data-ttu-id="4b34e-103">Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="4b34e-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="4b34e-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4b34e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4b34e-105">Regola la tabella di verità da una matrice di valori booleani in base al numero di variabili</span><span class="sxs-lookup"><span data-stu-id="4b34e-105">Adjusts truth table from array of Booleans according to number of variables</span></span>

<span data-ttu-id="4b34e-106">Viene restituita una nuova matrice di lunghezza `2^numVars` , che può richiedere l'estensione delle `table` dimensioni con le `false` voci o il troncamento degli `2^numVars` elementi.</span><span class="sxs-lookup"><span data-stu-id="4b34e-106">A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.</span></span>

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="4b34e-107">Input</span><span class="sxs-lookup"><span data-stu-id="4b34e-107">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="4b34e-108">tabella: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="4b34e-108">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="4b34e-109">Tabella di verità come matrice di valori di verità</span><span class="sxs-lookup"><span data-stu-id="4b34e-109">Truth table as array of truth values</span></span>


### <a name="numvars--int"></a><span data-ttu-id="4b34e-110">numVars: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4b34e-110">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4b34e-111">Numero di variabili</span><span class="sxs-lookup"><span data-stu-id="4b34e-111">Number of variables</span></span>



## <a name="output--bool"></a><span data-ttu-id="4b34e-112">Output: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="4b34e-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="4b34e-113">Ridimensionamento della tabella di verità</span><span class="sxs-lookup"><span data-stu-id="4b34e-113">Size adjusted truth table</span></span>
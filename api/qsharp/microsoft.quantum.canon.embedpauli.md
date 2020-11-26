---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: EmbedPauli (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: e9042ca9eac4b8791057037dc5698eb14deadd31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207038"
---
# <a name="embedpauli-function"></a><span data-ttu-id="496d3-102">EmbedPauli (funzione)</span><span class="sxs-lookup"><span data-stu-id="496d3-102">EmbedPauli function</span></span>

<span data-ttu-id="496d3-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="496d3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="496d3-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="496d3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="496d3-105">Dato un operatore Pauli Single-qubit e l'indice di un qubit, restituisce un operatore Pauli a più qubit con l'operatore Single-qubit specificato in corrispondenza di tale indice e `PauliI` in corrispondenza di ogni altro indice.</span><span class="sxs-lookup"><span data-stu-id="496d3-105">Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.</span></span>

```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="496d3-106">Input</span><span class="sxs-lookup"><span data-stu-id="496d3-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="496d3-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="496d3-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="496d3-108">Operatore Pauli Single-qubit da inserire nella posizione specificata.</span><span class="sxs-lookup"><span data-stu-id="496d3-108">A single-qubit Pauli operator to be placed at the given location.</span></span>


### <a name="location--int"></a><span data-ttu-id="496d3-109">Località: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="496d3-109">location : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="496d3-110">Indice in modo che `output[location] == pauli` , dove `output` è l'output di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="496d3-110">An index such that `output[location] == pauli`, where `output` is the output of this function.</span></span>


### <a name="n--int"></a><span data-ttu-id="496d3-111">n: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="496d3-111">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="496d3-112">Lunghezza della matrice da restituire.</span><span class="sxs-lookup"><span data-stu-id="496d3-112">Length of the array to be returned.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="496d3-113">Output: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="496d3-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>


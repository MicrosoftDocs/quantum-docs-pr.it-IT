---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: PauliArrayAsInt (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: f8ec468dd0f0cfd0d868dfc79ff715b3b4fc2f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713373"
---
# <a name="pauliarrayasint-function"></a><span data-ttu-id="c69fb-102">PauliArrayAsInt (funzione)</span><span class="sxs-lookup"><span data-stu-id="c69fb-102">PauliArrayAsInt function</span></span>

<span data-ttu-id="c69fb-103">Spazio dei nomi: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="c69fb-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="c69fb-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c69fb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c69fb-105">Codifica un operatore Pauli multiqubit rappresentato come una matrice di operatori Single-qubit Pauli in un intero.</span><span class="sxs-lookup"><span data-stu-id="c69fb-105">Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.</span></span>

```qsharp
function PauliArrayAsInt (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="c69fb-106">Input</span><span class="sxs-lookup"><span data-stu-id="c69fb-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="c69fb-107">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="c69fb-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="c69fb-108">Una matrice di al massimo 31 operatori di Pauli a qubit singola.</span><span class="sxs-lookup"><span data-stu-id="c69fb-108">An array of at most 31 single-qubit Pauli operators.</span></span>



## <a name="output--int"></a><span data-ttu-id="c69fb-109">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c69fb-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c69fb-110">Intero che identifica in modo univoco `paulis` , come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="c69fb-110">An integer uniquely identifying `paulis`, as described below.</span></span>

## <a name="remarks"></a><span data-ttu-id="c69fb-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="c69fb-111">Remarks</span></span>

<span data-ttu-id="c69fb-112">Ogni operatore di Pauli può essere codificato usando due bit: $ $ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.</span><span class="sxs-lookup"><span data-stu-id="c69fb-112">Each Pauli operator can be encoded using two bits: $$ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.</span></span>
<span data-ttu-id="c69fb-113">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="c69fb-113">\end{align} $$</span></span>

<span data-ttu-id="c69fb-114">Data una matrice di operatori Pauli `[P0, ..., Pn]` , questa funzione restituisce un integer con espansione binaria formata concatenando i mapping di ogni operatore Pauli nell'ordine big-endian `bits(Pn) ... bits(P0)` .</span><span class="sxs-lookup"><span data-stu-id="c69fb-114">Given an array of Pauli operators `[P0, ..., Pn]`, this function returns an integer with binary expansion formed by concatenating the mappings of each Pauli operator in big-endian order `bits(Pn) ... bits(P0)`.</span></span>
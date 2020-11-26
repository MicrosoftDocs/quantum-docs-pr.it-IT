---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: BoolArrayAsPauli (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: 8e7088ec3918165d7b2afb1056a8319c6fb17796
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214280"
---
# <a name="boolarrayaspauli-function"></a><span data-ttu-id="57397-102">BoolArrayAsPauli (funzione)</span><span class="sxs-lookup"><span data-stu-id="57397-102">BoolArrayAsPauli function</span></span>

<span data-ttu-id="57397-103">Spazio dei nomi: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="57397-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="57397-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="57397-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="57397-105">Data una stringa di bit, restituisce un operatore Pauli multiqubit rappresentato come una matrice di operatori Pauli a qubit singolo.</span><span class="sxs-lookup"><span data-stu-id="57397-105">Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>

```qsharp
function BoolArrayAsPauli (pauli : Pauli, bitApply : Bool, bits : Bool[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="57397-106">Input</span><span class="sxs-lookup"><span data-stu-id="57397-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="57397-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="57397-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="57397-108">Operatore Pauli da applicare a qubits dove `bitsApply == bits[idx]` .</span><span class="sxs-lookup"><span data-stu-id="57397-108">Pauli operator to apply to qubits where `bitsApply == bits[idx]`.</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="57397-109">in una delle seguenti operazioni: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="57397-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="57397-110">applicare Pauli se bit è questo valore.</span><span class="sxs-lookup"><span data-stu-id="57397-110">apply Pauli if bit is this value.</span></span>


### <a name="bits--bool"></a><span data-ttu-id="57397-111">BITS: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="57397-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="57397-112">Matrice booleana.</span><span class="sxs-lookup"><span data-stu-id="57397-112">Boolean array.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="57397-113">Output: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="57397-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="57397-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="57397-114">Remarks</span></span>

<span data-ttu-id="57397-115">La matrice booleana e il registro Quantum devono essere di uguale lunghezza.</span><span class="sxs-lookup"><span data-stu-id="57397-115">The Boolean array and the quantum register must be of equal length.</span></span>
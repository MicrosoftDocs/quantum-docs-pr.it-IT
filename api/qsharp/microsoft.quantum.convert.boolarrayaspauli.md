---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: BoolArrayAsPauli (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: c5ef71322dae248fc2c6b1db3adf891de7d72488
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713600"
---
# <a name="boolarrayaspauli-function"></a><span data-ttu-id="ba30f-102">BoolArrayAsPauli (funzione)</span><span class="sxs-lookup"><span data-stu-id="ba30f-102">BoolArrayAsPauli function</span></span>

<span data-ttu-id="ba30f-103">Spazio dei nomi: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="ba30f-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="ba30f-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ba30f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ba30f-105">Data una stringa di bit, restituisce un operatore Pauli multiqubit rappresentato come una matrice di operatori Pauli a qubit singolo.</span><span class="sxs-lookup"><span data-stu-id="ba30f-105">Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>

```qsharp
function BoolArrayAsPauli (pauli : Pauli, bitApply : Bool, bits : Bool[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="ba30f-106">Input</span><span class="sxs-lookup"><span data-stu-id="ba30f-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="ba30f-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="ba30f-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="ba30f-108">Operatore Pauli da applicare a qubits dove `bitsApply == bits[idx]` .</span><span class="sxs-lookup"><span data-stu-id="ba30f-108">Pauli operator to apply to qubits where `bitsApply == bits[idx]`.</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="ba30f-109">in una delle seguenti operazioni: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ba30f-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ba30f-110">applicare Pauli se bit è questo valore.</span><span class="sxs-lookup"><span data-stu-id="ba30f-110">apply Pauli if bit is this value.</span></span>


### <a name="bits--bool"></a><span data-ttu-id="ba30f-111">BITS: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="ba30f-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="ba30f-112">Matrice booleana.</span><span class="sxs-lookup"><span data-stu-id="ba30f-112">Boolean array.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="ba30f-113">Output: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="ba30f-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="ba30f-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="ba30f-114">Remarks</span></span>

<span data-ttu-id="ba30f-115">La matrice booleana e il registro Quantum devono essere di uguale lunghezza.</span><span class="sxs-lookup"><span data-stu-id="ba30f-115">The Boolean array and the quantum register must be of equal length.</span></span>
---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: Operazione ApplyXorInPlace
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: b7fc20ac421d5cff9baa3fe05450c1564f123505
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210114"
---
# <a name="applyxorinplace-operation"></a><span data-ttu-id="d9f3c-102">Operazione ApplyXorInPlace</span><span class="sxs-lookup"><span data-stu-id="d9f3c-102">ApplyXorInPlace operation</span></span>

<span data-ttu-id="d9f3c-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d9f3c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d9f3c-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d9f3c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d9f3c-105">Applica un'operazione XOR bit per bit tra un intero classico e un Integer rappresentato da un registro di qubits.</span><span class="sxs-lookup"><span data-stu-id="d9f3c-105">Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.</span></span>

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="d9f3c-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d9f3c-106">Description</span></span>

<span data-ttu-id="d9f3c-107">Applica `X` le operazioni a qubits in un registro Little-Endian basato su 1 bit in un intero.</span><span class="sxs-lookup"><span data-stu-id="d9f3c-107">Applies `X` operations to qubits in a little-endian register based on 1 bits in an integer.</span></span>

<span data-ttu-id="d9f3c-108">È possibile denotare `value` un oggetto e lasciare che y sia un Unsigned Integer codificato in `target` , quindi `InPlaceXorLE` esegue un'operazione fornita dalla mappa seguente: $ \ket{y}\rightarrow \ket{y\oplus a} $, dove $ \oplus $ è l'operatore OR esclusivo bit per bit.</span><span class="sxs-lookup"><span data-stu-id="d9f3c-108">Let us denote `value` by a and let y be an unsigned integer encoded in `target`, then `InPlaceXorLE` performs an operation given by the following map: $\ket{y}\rightarrow \ket{y\oplus a}$ , where $\oplus$ is the bitwise exclusive OR operator.</span></span>

## <a name="input"></a><span data-ttu-id="d9f3c-109">Input</span><span class="sxs-lookup"><span data-stu-id="d9f3c-109">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="d9f3c-110">valore: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d9f3c-110">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d9f3c-111">Integer considerato non negativo.</span><span class="sxs-lookup"><span data-stu-id="d9f3c-111">An integer which is assumed to be non-negative.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="d9f3c-112">destinazione: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d9f3c-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d9f3c-113">Registro Quantum usato per archiviare la `value` codifica little-endian.</span><span class="sxs-lookup"><span data-stu-id="d9f3c-113">A quantum register which is used to store `value` in little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d9f3c-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d9f3c-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


---
uid: Microsoft.Quantum.Arithmetic.CompareUsingRippleCarry
title: Operazione CompareUsingRippleCarry
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareUsingRippleCarry
qsharp.summary: This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.
ms.openlocfilehash: ce2be140ecfed21dea6212651249b4a11d2542c8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843279"
---
# <a name="compareusingripplecarry-operation"></a><span data-ttu-id="58cf1-102">Operazione CompareUsingRippleCarry</span><span class="sxs-lookup"><span data-stu-id="58cf1-102">CompareUsingRippleCarry operation</span></span>

<span data-ttu-id="58cf1-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="58cf1-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="58cf1-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="58cf1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="58cf1-105">Questa operazione verifica se un valore Integer rappresentato da un registro di qubits è maggiore di un altro numero intero, applicando un XOR del risultato in un qubit di output.</span><span class="sxs-lookup"><span data-stu-id="58cf1-105">This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.</span></span>

```qsharp
operation CompareUsingRippleCarry (x : Microsoft.Quantum.Arithmetic.LittleEndian, y : Microsoft.Quantum.Arithmetic.LittleEndian, output : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="58cf1-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58cf1-106">Description</span></span>

<span data-ttu-id="58cf1-107">Dato due integer `x` e `y` archiviati in registri di qubit di dimensioni uguali, questa operazione Controlla se soddisfano `x > y` .</span><span class="sxs-lookup"><span data-stu-id="58cf1-107">Given two integers `x` and `y` stored in equal-size qubit registers, this operation checks if they satisfy `x > y`.</span></span> <span data-ttu-id="58cf1-108">Se true, 1 è XORed in un qubit di output.</span><span class="sxs-lookup"><span data-stu-id="58cf1-108">If true, 1 is XORed into an output qubit.</span></span> <span data-ttu-id="58cf1-109">In caso contrario, 0 è XORed in un qubit di output.</span><span class="sxs-lookup"><span data-stu-id="58cf1-109">Otherwise, 0 is XORed into an output qubit.</span></span>
<span data-ttu-id="58cf1-110">In altre parole, questa operazione può essere rappresentata dall'unità $ $ \begin{align} U\ket {x} \ KET {y} \ KET {z} = \ket{x}\ket{y}\ket{z\oplus (x>y)}.</span><span class="sxs-lookup"><span data-stu-id="58cf1-110">In other words, this operation can be represented by the unitary $$ \begin{align} U\ket{x}\ket{y}\ket{z} = \ket{x}\ket{y}\ket{z\oplus (x>y)}.</span></span>
<span data-ttu-id="58cf1-111">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="58cf1-111">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="58cf1-112">Input</span><span class="sxs-lookup"><span data-stu-id="58cf1-112">Input</span></span>

### <a name="x--littleendian"></a><span data-ttu-id="58cf1-113">x: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="58cf1-113">x : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="58cf1-114">Primo numero da confrontare archiviato nel `LittleEndian` formato in un registro qubit.</span><span class="sxs-lookup"><span data-stu-id="58cf1-114">First number to be compared stored in `LittleEndian` format in a qubit register.</span></span>


### <a name="y--littleendian"></a><span data-ttu-id="58cf1-115">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="58cf1-115">y : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="58cf1-116">Secondo numero da confrontare archiviato nel `LittleEndian` formato in un registro qubit.</span><span class="sxs-lookup"><span data-stu-id="58cf1-116">Second number to be compared stored in `LittleEndian` format in a qubit register.</span></span>


### <a name="output--qubit"></a><span data-ttu-id="58cf1-117">output: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="58cf1-117">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="58cf1-118">Qubit che archivia il risultato del confronto $x>y $.</span><span class="sxs-lookup"><span data-stu-id="58cf1-118">Qubit that stores the result of the comparison $x>y$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="58cf1-119">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="58cf1-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="58cf1-120">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="58cf1-120">References</span></span>

- <span data-ttu-id="58cf1-121">Una nuova Ripple quantistica, il circuito di addizione Steven A. Cuccaro, Thomas G. Draper, Samuel A. kutin, David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184</span><span class="sxs-lookup"><span data-stu-id="58cf1-121">A new quantum ripple-carry addition circuit Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184</span></span>
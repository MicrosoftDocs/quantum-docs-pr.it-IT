---
uid: Microsoft.Quantum.Arithmetic.CompareUsingRippleCarry
title: Operazione CompareUsingRippleCarry
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareUsingRippleCarry
qsharp.summary: This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.
ms.openlocfilehash: 842e7ded1e38f4f6e01e79d2758e30afb85dd349
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721275"
---
# <a name="compareusingripplecarry-operation"></a><span data-ttu-id="419bf-102">Operazione CompareUsingRippleCarry</span><span class="sxs-lookup"><span data-stu-id="419bf-102">CompareUsingRippleCarry operation</span></span>

<span data-ttu-id="419bf-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="419bf-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="419bf-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="419bf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="419bf-105">Questa operazione verifica se un valore Integer rappresentato da un registro di qubits è maggiore di un altro numero intero, applicando un XOR del risultato in un qubit di output.</span><span class="sxs-lookup"><span data-stu-id="419bf-105">This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.</span></span>

```qsharp
operation CompareUsingRippleCarry (x : Microsoft.Quantum.Arithmetic.LittleEndian, y : Microsoft.Quantum.Arithmetic.LittleEndian, output : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="419bf-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="419bf-106">Description</span></span>

<span data-ttu-id="419bf-107">Dato due integer `x` e `y` archiviati in registri di qubit di dimensioni uguali, questa operazione Controlla se soddisfano `x > y` .</span><span class="sxs-lookup"><span data-stu-id="419bf-107">Given two integers `x` and `y` stored in equal-size qubit registers, this operation checks if they satisfy `x > y`.</span></span> <span data-ttu-id="419bf-108">Se true, 1 è XORed in un qubit di output.</span><span class="sxs-lookup"><span data-stu-id="419bf-108">If true, 1 is XORed into an output qubit.</span></span> <span data-ttu-id="419bf-109">In caso contrario, 0 è XORed in un qubit di output.</span><span class="sxs-lookup"><span data-stu-id="419bf-109">Otherwise, 0 is XORed into an output qubit.</span></span>
<span data-ttu-id="419bf-110">In altre parole, questa operazione può essere rappresentata dall'unità $ $ \begin{align} U\ket {x} \ KET {y} \ KET {z} = \ket{x}\ket{y}\ket{z\oplus (x>y)}.</span><span class="sxs-lookup"><span data-stu-id="419bf-110">In other words, this operation can be represented by the unitary $$ \begin{align} U\ket{x}\ket{y}\ket{z} = \ket{x}\ket{y}\ket{z\oplus (x>y)}.</span></span>
<span data-ttu-id="419bf-111">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="419bf-111">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="419bf-112">Input</span><span class="sxs-lookup"><span data-stu-id="419bf-112">Input</span></span>

### <a name="x--littleendian"></a><span data-ttu-id="419bf-113">x: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="419bf-113">x : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="419bf-114">Primo numero da confrontare archiviato nel `LittleEndian` formato in un registro qubit.</span><span class="sxs-lookup"><span data-stu-id="419bf-114">First number to be compared stored in `LittleEndian` format in a qubit register.</span></span>


### <a name="y--littleendian"></a><span data-ttu-id="419bf-115">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="419bf-115">y : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="419bf-116">Secondo numero da confrontare archiviato nel `LittleEndian` formato in un registro qubit.</span><span class="sxs-lookup"><span data-stu-id="419bf-116">Second number to be compared stored in `LittleEndian` format in a qubit register.</span></span>


### <a name="output--qubit"></a><span data-ttu-id="419bf-117">output: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="419bf-117">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="419bf-118">Qubit che archivia il risultato del confronto $x>y $.</span><span class="sxs-lookup"><span data-stu-id="419bf-118">Qubit that stores the result of the comparison $x>y$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="419bf-119">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="419bf-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="419bf-120">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="419bf-120">References</span></span>

- <span data-ttu-id="419bf-121">Una nuova Ripple quantistica, il circuito di addizione Steven A. Cuccaro, Thomas G. Draper, Samuel A. kutin, David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184</span><span class="sxs-lookup"><span data-stu-id="419bf-121">A new quantum ripple-carry addition circuit Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184</span></span>
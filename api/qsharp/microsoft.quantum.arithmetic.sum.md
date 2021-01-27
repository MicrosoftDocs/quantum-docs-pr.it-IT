---
uid: Microsoft.Quantum.Arithmetic.Sum
title: Operazione per la determinazione della somma
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Sum
qsharp.summary: Implements a reversible sum gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.
ms.openlocfilehash: e659c77a876e10df75f28ca1798fb0335e1bfb22
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847761"
---
# <a name="sum-operation"></a><span data-ttu-id="dd9e9-102">Operazione per la determinazione della somma</span><span class="sxs-lookup"><span data-stu-id="dd9e9-102">Sum operation</span></span>

<span data-ttu-id="dd9e9-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="dd9e9-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="dd9e9-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dd9e9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dd9e9-105">Implementa un controllo Sum reversibile.</span><span class="sxs-lookup"><span data-stu-id="dd9e9-105">Implements a reversible sum gate.</span></span> <span data-ttu-id="dd9e9-106">Dato un bit di trasporto codificato in qubit `carryIn` e due bit summand codificati in `summand1` e `summand2` , calcola l'XOR bit per bit di `carryIn` `summand1` e `summand2` nel qubit `summand2` .</span><span class="sxs-lookup"><span data-stu-id="dd9e9-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.</span></span>

```qsharp
operation Sum (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="dd9e9-107">Input</span><span class="sxs-lookup"><span data-stu-id="dd9e9-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="dd9e9-108">carryin: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="dd9e9-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="dd9e9-109">Eseguire il qubit.</span><span class="sxs-lookup"><span data-stu-id="dd9e9-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="dd9e9-110">sommando1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="dd9e9-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="dd9e9-111">Primo summand qubit.</span><span class="sxs-lookup"><span data-stu-id="dd9e9-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="dd9e9-112">sommando2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="dd9e9-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="dd9e9-113">Il secondo summand qubit, viene sostituito con il bit più basso della somma di `summand1` e `summand2` .</span><span class="sxs-lookup"><span data-stu-id="dd9e9-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dd9e9-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dd9e9-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="dd9e9-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="dd9e9-115">Remarks</span></span>

<span data-ttu-id="dd9e9-116">A differenza dell' `Carry` operazione, questo non calcola il bit di trascinamento.</span><span class="sxs-lookup"><span data-stu-id="dd9e9-116">In contrast to the `Carry` operation, this does not compute the carry-out bit.</span></span>
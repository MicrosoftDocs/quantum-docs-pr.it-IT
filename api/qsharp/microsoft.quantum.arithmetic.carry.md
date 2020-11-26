---
uid: Microsoft.Quantum.Arithmetic.Carry
title: Operazione Carry
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Carry
qsharp.summary: Implements a reversible carry gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.
ms.openlocfilehash: 53f8d2a8ba89a912e3d4c08452208a899b2b85de
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223596"
---
# <a name="carry-operation"></a><span data-ttu-id="31679-102">Operazione Carry</span><span class="sxs-lookup"><span data-stu-id="31679-102">Carry operation</span></span>

<span data-ttu-id="31679-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="31679-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="31679-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="31679-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="31679-105">Implementa un controllo di porta reversibile.</span><span class="sxs-lookup"><span data-stu-id="31679-105">Implements a reversible carry gate.</span></span> <span data-ttu-id="31679-106">Dato un bit di trasporto codificato in qubit `carryIn` e due bit summand codificati in `summand1` e `summand2` , calcola l'operatore XOR bit per bit di e `carryIn` `summand1` `summand2` in qubit `summand2` e il riporto è XORed a qubit `carryOut` .</span><span class="sxs-lookup"><span data-stu-id="31679-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.</span></span>

```qsharp
operation Carry (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit, carryOut : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="31679-107">Input</span><span class="sxs-lookup"><span data-stu-id="31679-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="31679-108">carryin: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="31679-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="31679-109">Eseguire il qubit.</span><span class="sxs-lookup"><span data-stu-id="31679-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="31679-110">sommando1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="31679-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="31679-111">Primo summand qubit.</span><span class="sxs-lookup"><span data-stu-id="31679-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="31679-112">sommando2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="31679-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="31679-113">Il secondo summand qubit, viene sostituito con il bit più basso della somma di `summand1` e `summand2` .</span><span class="sxs-lookup"><span data-stu-id="31679-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>


### <a name="carryout--qubit"></a><span data-ttu-id="31679-114">esecuzione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="31679-114">carryOut : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="31679-115">Il qubit di esecuzione, sarà XORed con il bit più alto della somma.</span><span class="sxs-lookup"><span data-stu-id="31679-115">Carry-out qubit, will be xored with the higher bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="31679-116">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="31679-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


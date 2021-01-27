---
uid: Microsoft.Quantum.Arithmetic.Carry
title: Operazione Carry
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Carry
qsharp.summary: Implements a reversible carry gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.
ms.openlocfilehash: dfb08a9a9c805c0b611ab993c9b1eb949810a7da
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843347"
---
# <a name="carry-operation"></a><span data-ttu-id="e8953-102">Operazione Carry</span><span class="sxs-lookup"><span data-stu-id="e8953-102">Carry operation</span></span>

<span data-ttu-id="e8953-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e8953-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e8953-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e8953-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e8953-105">Implementa un controllo di porta reversibile.</span><span class="sxs-lookup"><span data-stu-id="e8953-105">Implements a reversible carry gate.</span></span> <span data-ttu-id="e8953-106">Dato un bit di trasporto codificato in qubit `carryIn` e due bit summand codificati in `summand1` e `summand2` , calcola l'operatore XOR bit per bit di e `carryIn` `summand1` `summand2` in qubit `summand2` e il riporto è XORed a qubit `carryOut` .</span><span class="sxs-lookup"><span data-stu-id="e8953-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.</span></span>

```qsharp
operation Carry (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit, carryOut : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e8953-107">Input</span><span class="sxs-lookup"><span data-stu-id="e8953-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="e8953-108">carryin: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e8953-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e8953-109">Eseguire il qubit.</span><span class="sxs-lookup"><span data-stu-id="e8953-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="e8953-110">sommando1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e8953-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e8953-111">Primo summand qubit.</span><span class="sxs-lookup"><span data-stu-id="e8953-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="e8953-112">sommando2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e8953-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e8953-113">Il secondo summand qubit, viene sostituito con il bit più basso della somma di `summand1` e `summand2` .</span><span class="sxs-lookup"><span data-stu-id="e8953-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>


### <a name="carryout--qubit"></a><span data-ttu-id="e8953-114">esecuzione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e8953-114">carryOut : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e8953-115">Il qubit di esecuzione, sarà XORed con il bit più alto della somma.</span><span class="sxs-lookup"><span data-stu-id="e8953-115">Carry-out qubit, will be xored with the higher bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e8953-116">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e8953-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


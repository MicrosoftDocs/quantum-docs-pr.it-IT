---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger
title: Operazione MultiplyAndAddPhaseByModularInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddPhaseByModularInteger
qsharp.summary: The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.
ms.openlocfilehash: b1214acc2cafc3fede9fcb6663a435c0b1d2cf4a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843071"
---
# <a name="multiplyandaddphasebymodularinteger-operation"></a><span data-ttu-id="1489f-102">Operazione MultiplyAndAddPhaseByModularInteger</span><span class="sxs-lookup"><span data-stu-id="1489f-102">MultiplyAndAddPhaseByModularInteger operation</span></span>

<span data-ttu-id="1489f-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="1489f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="1489f-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1489f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1489f-105">Analogamente a MultiplyAndAddByModularInteger, ma presuppone che summand Codifichi numeri interi in base a QFT.</span><span class="sxs-lookup"><span data-stu-id="1489f-105">The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.</span></span>

```qsharp
operation MultiplyAndAddPhaseByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, phaseSummand : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="1489f-106">Input</span><span class="sxs-lookup"><span data-stu-id="1489f-106">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="1489f-107">constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1489f-107">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1489f-108">Integer $a $ da aggiungere a ogni etichetta di stato di base.</span><span class="sxs-lookup"><span data-stu-id="1489f-108">An integer $a$ to be added to each basis state label.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="1489f-109">modulo: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1489f-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1489f-110">Il modulo $N $ quali addizioni e moltiplicazioni vengono prese in relazione a.</span><span class="sxs-lookup"><span data-stu-id="1489f-110">The modulus $N$ which addition and multiplication is taken with respect to.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="1489f-111">moltiplicatore: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1489f-111">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="1489f-112">Registro Quantum che rappresenta un Unsigned Integer il cui valore deve essere aggiunto a ogni etichetta dello stato di base di `summand` .</span><span class="sxs-lookup"><span data-stu-id="1489f-112">A quantum register representing an unsigned integer whose value is to be added to each basis state label of `summand`.</span></span>


### <a name="phasesummand--phaselittleendian"></a><span data-ttu-id="1489f-113">phaseSummand: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1489f-113">phaseSummand : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="1489f-114">Registro Quantum che rappresenta un Unsigned Integer da usare come destinazione per questa operazione.</span><span class="sxs-lookup"><span data-stu-id="1489f-114">A quantum register representing an unsigned integer to use as the target for this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1489f-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1489f-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="1489f-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="1489f-116">Remarks</span></span>

<span data-ttu-id="1489f-117">Presuppone che `phaseSummand` il bit più alto sia impostato su 0.</span><span class="sxs-lookup"><span data-stu-id="1489f-117">Assumes that `phaseSummand` has the highest bit set to 0.</span></span>
<span data-ttu-id="1489f-118">Presuppone inoltre che il valore di `phaseSummand` sia minore di $N $.</span><span class="sxs-lookup"><span data-stu-id="1489f-118">Also assumes that the value of `phaseSummand` is less than $N$.</span></span>

## <a name="see-also"></a><span data-ttu-id="1489f-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1489f-119">See Also</span></span>

- [<span data-ttu-id="1489f-120">Microsoft. Quantum. aritmetic. MultiplyAndAddByModularInteger</span><span class="sxs-lookup"><span data-stu-id="1489f-120">Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger)
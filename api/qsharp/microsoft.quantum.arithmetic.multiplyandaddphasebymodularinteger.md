---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger
title: Operazione MultiplyAndAddPhaseByModularInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddPhaseByModularInteger
qsharp.summary: The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.
ms.openlocfilehash: be7df50f040697329c2fe8bbc319c8cebb8b2687
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719802"
---
# <a name="multiplyandaddphasebymodularinteger-operation"></a><span data-ttu-id="b6301-102">Operazione MultiplyAndAddPhaseByModularInteger</span><span class="sxs-lookup"><span data-stu-id="b6301-102">MultiplyAndAddPhaseByModularInteger operation</span></span>

<span data-ttu-id="b6301-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b6301-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b6301-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b6301-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b6301-105">Analogamente a MultiplyAndAddByModularInteger, ma presuppone che summand Codifichi numeri interi in base a QFT.</span><span class="sxs-lookup"><span data-stu-id="b6301-105">The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.</span></span>

```qsharp
operation MultiplyAndAddPhaseByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, phaseSummand : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="b6301-106">Input</span><span class="sxs-lookup"><span data-stu-id="b6301-106">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="b6301-107">constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b6301-107">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b6301-108">Integer $a $ da aggiungere a ogni etichetta di stato di base.</span><span class="sxs-lookup"><span data-stu-id="b6301-108">An integer $a$ to be added to each basis state label.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="b6301-109">modulo: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b6301-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b6301-110">Il modulo $N $ quali addizioni e moltiplicazioni vengono prese in relazione a.</span><span class="sxs-lookup"><span data-stu-id="b6301-110">The modulus $N$ which addition and multiplication is taken with respect to.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="b6301-111">moltiplicatore: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b6301-111">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b6301-112">Registro Quantum che rappresenta un Unsigned Integer il cui valore deve essere aggiunto a ogni etichetta dello stato di base di `summand` .</span><span class="sxs-lookup"><span data-stu-id="b6301-112">A quantum register representing an unsigned integer whose value is to be added to each basis state label of `summand`.</span></span>


### <a name="phasesummand--phaselittleendian"></a><span data-ttu-id="b6301-113">phaseSummand: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b6301-113">phaseSummand : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="b6301-114">Registro Quantum che rappresenta un Unsigned Integer da usare come destinazione per questa operazione.</span><span class="sxs-lookup"><span data-stu-id="b6301-114">A quantum register representing an unsigned integer to use as the target for this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b6301-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b6301-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b6301-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="b6301-116">Remarks</span></span>

<span data-ttu-id="b6301-117">Presuppone che `phaseSummand` il bit più alto sia impostato su 0.</span><span class="sxs-lookup"><span data-stu-id="b6301-117">Assumes that `phaseSummand` has the highest bit set to 0.</span></span>
<span data-ttu-id="b6301-118">Presuppone inoltre che il valore di `phaseSummand` sia minore di $N $.</span><span class="sxs-lookup"><span data-stu-id="b6301-118">Also assumes that the value of `phaseSummand` is less than $N$.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6301-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6301-119">See Also</span></span>

- [<span data-ttu-id="b6301-120">Microsoft. Quantum. aritmetic. MultiplyAndAddByModularInteger</span><span class="sxs-lookup"><span data-stu-id="b6301-120">Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger)
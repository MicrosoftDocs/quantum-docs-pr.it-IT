---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderD
title: Operazione RippleCarryAdderD
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderD
qsharp.summary: Reversible, in-place ripple-carry addition of two integers. Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.
ms.openlocfilehash: c4466feebb8ff6afcdcb5bf385ec10e807c00537
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719586"
---
# <a name="ripplecarryadderd-operation"></a><span data-ttu-id="97864-102">Operazione RippleCarryAdderD</span><span class="sxs-lookup"><span data-stu-id="97864-102">RippleCarryAdderD operation</span></span>

<span data-ttu-id="97864-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="97864-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="97864-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="97864-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="97864-105">Ripple sul posto reversibile: porta l'aggiunta di due numeri interi.</span><span class="sxs-lookup"><span data-stu-id="97864-105">Reversible, in-place ripple-carry addition of two integers.</span></span>
<span data-ttu-id="97864-106">Dati due $n interi a $ bit codificati nei registri LittleEndian `xs` e e `ys` un qubit Carry, l'operazione calcola la somma dei due numeri interi in cui i $n bit meno significativi del risultato sono contenuti in `ys` e il bit di esecuzione è XORed a qubit `carry` .</span><span class="sxs-lookup"><span data-stu-id="97864-106">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.</span></span>

```qsharp
operation RippleCarryAdderD (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="97864-107">Input</span><span class="sxs-lookup"><span data-stu-id="97864-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="97864-108">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="97864-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="97864-109">LittleEndian qubit registra la codifica del primo Integer summand.</span><span class="sxs-lookup"><span data-stu-id="97864-109">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="97864-110">Ys: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="97864-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="97864-111">Il registro LittleEndian qubit che codifica il secondo valore integer summand, viene modificato in modo da mantenere i bit $n $ meno significativi della somma.</span><span class="sxs-lookup"><span data-stu-id="97864-111">LittleEndian qubit register encoding the second integer summand, is modified to hold the $n$ least significant bits of the sum.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="97864-112">porta: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="97864-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="97864-113">Carry qubit, is XORed con il bit più significativo della somma.</span><span class="sxs-lookup"><span data-stu-id="97864-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="97864-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="97864-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="97864-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="97864-115">Remarks</span></span>

<span data-ttu-id="97864-116">L'operazione controllata specificata si avvale della simmetria e dell'annullamento reciproco delle operazioni per migliorare l'implementazione predefinita che aggiunge un controllo a ogni operazione.</span><span class="sxs-lookup"><span data-stu-id="97864-116">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="97864-117">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="97864-117">References</span></span>

- <span data-ttu-id="97864-118">Thomas G. Draper: "aggiunta in un computer quantistico", 2000.</span><span class="sxs-lookup"><span data-stu-id="97864-118">Thomas G. Draper: "Addition on a Quantum Computer", 2000.</span></span>
  https://arxiv.org/abs/quant-ph/0008033
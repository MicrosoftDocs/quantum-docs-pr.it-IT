---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderNoCarryTTK
title: Operazione RippleCarryAdderNoCarryTTK
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderNoCarryTTK
qsharp.summary: Reversible, in-place ripple-carry addition of two integers without carry out.
ms.openlocfilehash: a539d85a4800c2f4452a1c6fe2c4f88a6296c3e1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221998"
---
# <a name="ripplecarryaddernocarryttk-operation"></a><span data-ttu-id="ddf69-102">Operazione RippleCarryAdderNoCarryTTK</span><span class="sxs-lookup"><span data-stu-id="ddf69-102">RippleCarryAdderNoCarryTTK operation</span></span>

<span data-ttu-id="ddf69-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ddf69-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ddf69-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ddf69-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ddf69-105">Ripple sul posto reversibile: porta l'aggiunta di due numeri interi senza eseguire l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ddf69-105">Reversible, in-place ripple-carry addition of two integers without carry out.</span></span>

```qsharp
operation RippleCarryAdderNoCarryTTK (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="ddf69-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ddf69-106">Description</span></span>

<span data-ttu-id="ddf69-107">Dato che due interi $n $ bit codificati nei registri LittleEndian `xs` e `ys` , l'operazione calcola la somma dei due valori interi modulo $2 ^ n $, dove $n $ è la dimensione in bit degli input `xs` e `ys` .</span><span class="sxs-lookup"><span data-stu-id="ddf69-107">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, the operation computes the sum of the two integers modulo $2^n$, where $n$ is the bit size of the inputs `xs` and `ys`.</span></span> <span data-ttu-id="ddf69-108">Non calcola il bit di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ddf69-108">It does not compute the carry out bit.</span></span>

## <a name="input"></a><span data-ttu-id="ddf69-109">Input</span><span class="sxs-lookup"><span data-stu-id="ddf69-109">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="ddf69-110">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ddf69-110">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ddf69-111">LittleEndian qubit registra la codifica del primo Integer summand.</span><span class="sxs-lookup"><span data-stu-id="ddf69-111">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="ddf69-112">Ys: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ddf69-112">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ddf69-113">Il registro LittleEndian qubit che codifica il secondo valore integer summand, viene modificato in modo da mantenere i bit $n $ meno significativi della somma.</span><span class="sxs-lookup"><span data-stu-id="ddf69-113">LittleEndian qubit register encoding the second integer summand, is modified to hold the $n$ least significant bits of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ddf69-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ddf69-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ddf69-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="ddf69-115">Remarks</span></span>

<span data-ttu-id="ddf69-116">Questa operazione ha la stessa funzionalità di RippleCarryAdderTTK, ma non restituisce il bit di riporto.</span><span class="sxs-lookup"><span data-stu-id="ddf69-116">This operation has the same functionality as RippleCarryAdderTTK but does not return the carry bit.</span></span>

## <a name="references"></a><span data-ttu-id="ddf69-117">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="ddf69-117">References</span></span>

- <span data-ttu-id="ddf69-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum addition Circuits and unbounded fan-out", Quantum Information and Computing, vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="ddf69-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530
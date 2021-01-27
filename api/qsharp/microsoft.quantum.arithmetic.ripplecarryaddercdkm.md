---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderCDKM
title: Operazione RippleCarryAdderCDKM
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderCDKM
qsharp.summary: Reversible, in-place ripple-carry addition of two integers.
ms.openlocfilehash: df9b62b649af532a4202aacc3e8dd4613eb8665d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846354"
---
# <a name="ripplecarryaddercdkm-operation"></a><span data-ttu-id="e0a32-102">Operazione RippleCarryAdderCDKM</span><span class="sxs-lookup"><span data-stu-id="e0a32-102">RippleCarryAdderCDKM operation</span></span>

<span data-ttu-id="e0a32-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e0a32-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e0a32-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e0a32-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e0a32-105">Ripple sul posto reversibile: porta l'aggiunta di due numeri interi.</span><span class="sxs-lookup"><span data-stu-id="e0a32-105">Reversible, in-place ripple-carry addition of two integers.</span></span>

```qsharp
operation RippleCarryAdderCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="e0a32-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e0a32-106">Description</span></span>

<span data-ttu-id="e0a32-107">Dati due $n interi a $ bit codificati nei registri LittleEndian `xs` e e `ys` un qubit Carry, l'operazione calcola la somma dei due numeri interi in cui i $n bit meno significativi del risultato sono contenuti in `ys` e il bit di esecuzione è XORed a qubit `carry` .</span><span class="sxs-lookup"><span data-stu-id="e0a32-107">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.</span></span>

## <a name="input"></a><span data-ttu-id="e0a32-108">Input</span><span class="sxs-lookup"><span data-stu-id="e0a32-108">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="e0a32-109">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e0a32-109">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e0a32-110">LittleEndian qubit registra la codifica del primo Integer summand.</span><span class="sxs-lookup"><span data-stu-id="e0a32-110">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="e0a32-111">Ys: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e0a32-111">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e0a32-112">LittleEndian qubit registro codifica il secondo Integer summand, viene modificato in modo da mantenere i bit meno significativi della somma.</span><span class="sxs-lookup"><span data-stu-id="e0a32-112">LittleEndian qubit register encoding the second integer summand, is modified to hold the n least significant bits of the sum.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="e0a32-113">porta: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e0a32-113">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e0a32-114">Carry qubit, is XORed con il bit più significativo della somma.</span><span class="sxs-lookup"><span data-stu-id="e0a32-114">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e0a32-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e0a32-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e0a32-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="e0a32-116">Remarks</span></span>

<span data-ttu-id="e0a32-117">Questa operazione ha la stessa funzionalità di RippleCarryAdderD, ma usa solo un qubit ausiliario invece di $n $.</span><span class="sxs-lookup"><span data-stu-id="e0a32-117">This operation has the same functionality as RippleCarryAdderD, but only uses one auxiliary qubit instead of $n$.</span></span>

## <a name="references"></a><span data-ttu-id="e0a32-118">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="e0a32-118">References</span></span>

- <span data-ttu-id="e0a32-119">Steven A. Cuccaro, Thomas G. Draper, Samuel A. kutin, David Petrie Moulton: "A New Quantum Ripple-Carry additional Circuit", 2004.</span><span class="sxs-lookup"><span data-stu-id="e0a32-119">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1
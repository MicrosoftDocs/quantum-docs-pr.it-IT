---
uid: Microsoft.Quantum.Arithmetic.GreaterThan
title: Operazione GreaterThan
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: GreaterThan
qsharp.summary: Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.
ms.openlocfilehash: 553efb0fc83f24235cb4a77933bd1d547bbd1fed
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846641"
---
# <a name="greaterthan-operation"></a><span data-ttu-id="0c5ce-102">Operazione GreaterThan</span><span class="sxs-lookup"><span data-stu-id="0c5ce-102">GreaterThan operation</span></span>

<span data-ttu-id="0c5ce-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="0c5ce-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="0c5ce-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0c5ce-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0c5ce-105">Applica un confronto maggiore di tra due numeri interi codificati in registri qubit, capovolgendo un qubit di destinazione in base al risultato del confronto.</span><span class="sxs-lookup"><span data-stu-id="0c5ce-105">Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.</span></span>

```qsharp
operation GreaterThan (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="0c5ce-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0c5ce-106">Description</span></span>

<span data-ttu-id="0c5ce-107">Esegue un confronto rigoroso tra due numeri interi $x $ e $y $, codificati in qubit registra XS e YS.</span><span class="sxs-lookup"><span data-stu-id="0c5ce-107">Carries out a strictly greater than comparison of two integers $x$ and $y$, encoded in qubit registers xs and ys.</span></span> <span data-ttu-id="0c5ce-108">Se $x > y $, il risultato qubit verrà capovolto, in caso contrario il risultato qubit manterrà il proprio stato.</span><span class="sxs-lookup"><span data-stu-id="0c5ce-108">If $x > y$, then the result qubit will be flipped, otherwise the result qubit will retain its state.</span></span>

## <a name="input"></a><span data-ttu-id="0c5ce-109">Input</span><span class="sxs-lookup"><span data-stu-id="0c5ce-109">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="0c5ce-110">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0c5ce-110">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0c5ce-111">LittleEndian qubit registra la codifica del primo Integer $x $.</span><span class="sxs-lookup"><span data-stu-id="0c5ce-111">LittleEndian qubit register encoding the first integer $x$.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="0c5ce-112">Ys: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0c5ce-112">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0c5ce-113">LittleEndian qubit-registrazione che codifica il secondo Integer $y $.</span><span class="sxs-lookup"><span data-stu-id="0c5ce-113">LittleEndian qubit register encoding the second integer $y$.</span></span>


### <a name="result--qubit"></a><span data-ttu-id="0c5ce-114">risultato: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0c5ce-114">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0c5ce-115">Singolo qubit che verrà capovolto se $x > y $.</span><span class="sxs-lookup"><span data-stu-id="0c5ce-115">Single qubit that will be flipped if $x > y$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0c5ce-116">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0c5ce-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0c5ce-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="0c5ce-117">Remarks</span></span>

<span data-ttu-id="0c5ce-118">Usa il trucco che $x-y = (x ' + y)' $, dove ' denota il complemento a uno.</span><span class="sxs-lookup"><span data-stu-id="0c5ce-118">Uses the trick that $x - y = (x'+y)'$, where ' denotes the one's complement.</span></span>

## <a name="references"></a><span data-ttu-id="0c5ce-119">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="0c5ce-119">References</span></span>

- <span data-ttu-id="0c5ce-120">Steven A. Cuccaro, Thomas G. Draper, Samuel A. kutin, David Petrie Moulton: "A New Quantum Ripple-Carry additional Circuit", 2004.</span><span class="sxs-lookup"><span data-stu-id="0c5ce-120">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1

- <span data-ttu-id="0c5ce-121">Thomas haener, Martin Roetteler, Krysta M. Svore: "factoring using 2n + 2 qubits with Toffoli Modular based Moltiplication", 2016 https://arxiv.org/abs/1611.07995</span><span class="sxs-lookup"><span data-stu-id="0c5ce-121">Thomas Haener, Martin Roetteler, Krysta M. Svore: "Factoring using 2n+2 qubits with Toffoli based modular multiplication", 2016 https://arxiv.org/abs/1611.07995</span></span>
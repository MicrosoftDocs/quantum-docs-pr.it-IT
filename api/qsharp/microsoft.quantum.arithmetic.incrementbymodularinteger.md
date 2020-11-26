---
uid: Microsoft.Quantum.Arithmetic.IncrementByModularInteger
title: Operazione IncrementByModularInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 8a02d22facce8f58180752b6d063ac55d75ca537
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222950"
---
# <a name="incrementbymodularinteger-operation"></a><span data-ttu-id="75a25-102">Operazione IncrementByModularInteger</span><span class="sxs-lookup"><span data-stu-id="75a25-102">IncrementByModularInteger operation</span></span>

<span data-ttu-id="75a25-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="75a25-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="75a25-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="75a25-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="75a25-105">Esegue un incremento modulare di un registro qubit da una costante Integer.</span><span class="sxs-lookup"><span data-stu-id="75a25-105">Performs a modular increment of a qubit register by an integer constant.</span></span>

```qsharp
operation IncrementByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="75a25-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="75a25-106">Description</span></span>

<span data-ttu-id="75a25-107">È ora indicata `increment` da $a $, `modulus` da $N $ e Integer codificati in `target` da $y $.</span><span class="sxs-lookup"><span data-stu-id="75a25-107">Let us denote `increment` by $a$, `modulus` by $N$ and integer encoded in `target` by $y$.</span></span>
<span data-ttu-id="75a25-108">L'operazione esegue quindi la trasformazione seguente: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} integer sono codificati in formato little-endian.</span><span class="sxs-lookup"><span data-stu-id="75a25-108">Then the operation performs the following transformation: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} Integers are encoded in little-endian format.</span></span>

## <a name="input"></a><span data-ttu-id="75a25-109">Input</span><span class="sxs-lookup"><span data-stu-id="75a25-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="75a25-110">incremento: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="75a25-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="75a25-111">Incremento Integer $a $ da aggiungere a $y $.</span><span class="sxs-lookup"><span data-stu-id="75a25-111">Integer increment $a$ to be added to $y$.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="75a25-112">modulo: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="75a25-112">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="75a25-113">Integer $N $ che mods $y + a $.</span><span class="sxs-lookup"><span data-stu-id="75a25-113">Integer $N$ that mods $y + a$.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="75a25-114">destinazione: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="75a25-114">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="75a25-115">Integer $y $ nel `LittleEndian` formato `increment` a cui $a $ viene aggiunto.</span><span class="sxs-lookup"><span data-stu-id="75a25-115">Integer $y$ in `LittleEndian` format that `increment` $a$ is added to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="75a25-116">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="75a25-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="75a25-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="75a25-117">Remarks</span></span>

<span data-ttu-id="75a25-118">Presuppone che il valore iniziale di target sia minore di $N $ e che l'incremento $a $ sia minore di $N $.</span><span class="sxs-lookup"><span data-stu-id="75a25-118">Assumes that the initial value of target is less than $N$ and that the increment $a$ is less than $N$.</span></span>
<span data-ttu-id="75a25-119">Si noti che <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> implementa la stessa operazione in `PhaseLittleEndian` base a.</span><span class="sxs-lookup"><span data-stu-id="75a25-119">Note that <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> implements the same operation in the `PhaseLittleEndian` basis.</span></span>

## <a name="see-also"></a><span data-ttu-id="75a25-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75a25-120">See Also</span></span>

- [<span data-ttu-id="75a25-121">Microsoft. Quantum. aritmetic. IncrementPhaseByModularInteger</span><span class="sxs-lookup"><span data-stu-id="75a25-121">Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger)
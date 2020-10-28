---
uid: Microsoft.Quantum.Arithmetic.IncrementByModularInteger
title: Operazione IncrementByModularInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 271033b32b0de6cf600dca82126dab19c2bb4f5d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721098"
---
# <a name="incrementbymodularinteger-operation"></a><span data-ttu-id="af8d2-102">Operazione IncrementByModularInteger</span><span class="sxs-lookup"><span data-stu-id="af8d2-102">IncrementByModularInteger operation</span></span>

<span data-ttu-id="af8d2-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="af8d2-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="af8d2-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="af8d2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="af8d2-105">Esegue un incremento modulare di un registro qubit da una costante Integer.</span><span class="sxs-lookup"><span data-stu-id="af8d2-105">Performs a modular increment of a qubit register by an integer constant.</span></span>

```qsharp
operation IncrementByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="af8d2-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="af8d2-106">Description</span></span>

<span data-ttu-id="af8d2-107">È ora indicata `increment` da $a $, `modulus` da $N $ e Integer codificati in `target` da $y $.</span><span class="sxs-lookup"><span data-stu-id="af8d2-107">Let us denote `increment` by $a$, `modulus` by $N$ and integer encoded in `target` by $y$.</span></span>
<span data-ttu-id="af8d2-108">L'operazione esegue quindi la trasformazione seguente: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} integer sono codificati in formato little-endian.</span><span class="sxs-lookup"><span data-stu-id="af8d2-108">Then the operation performs the following transformation: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} Integers are encoded in little-endian format.</span></span>

## <a name="input"></a><span data-ttu-id="af8d2-109">Input</span><span class="sxs-lookup"><span data-stu-id="af8d2-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="af8d2-110">incremento: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="af8d2-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="af8d2-111">Incremento Integer $a $ da aggiungere a $y $.</span><span class="sxs-lookup"><span data-stu-id="af8d2-111">Integer increment $a$ to be added to $y$.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="af8d2-112">modulo: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="af8d2-112">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="af8d2-113">Integer $N $ che mods $y + a $.</span><span class="sxs-lookup"><span data-stu-id="af8d2-113">Integer $N$ that mods $y + a$.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="af8d2-114">destinazione: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="af8d2-114">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="af8d2-115">Integer $y $ nel `LittleEndian` formato `increment` a cui $a $ viene aggiunto.</span><span class="sxs-lookup"><span data-stu-id="af8d2-115">Integer $y$ in `LittleEndian` format that `increment` $a$ is added to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="af8d2-116">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="af8d2-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="af8d2-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="af8d2-117">Remarks</span></span>

<span data-ttu-id="af8d2-118">Presuppone che il valore iniziale di target sia minore di $N $ e che l'incremento $a $ sia minore di $N $.</span><span class="sxs-lookup"><span data-stu-id="af8d2-118">Assumes that the initial value of target is less than $N$ and that the increment $a$ is less than $N$.</span></span>
<span data-ttu-id="af8d2-119">Si noti che <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> implementa la stessa operazione in `PhaseLittleEndian` base a.</span><span class="sxs-lookup"><span data-stu-id="af8d2-119">Note that <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> implements the same operation in the `PhaseLittleEndian` basis.</span></span>

## <a name="see-also"></a><span data-ttu-id="af8d2-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af8d2-120">See Also</span></span>

- [<span data-ttu-id="af8d2-121">Microsoft. Quantum. aritmetic. IncrementPhaseByModularInteger</span><span class="sxs-lookup"><span data-stu-id="af8d2-121">Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger)
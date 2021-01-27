---
uid: Microsoft.Quantum.Simulation.BlockEncodingByLCU
title: BlockEncodingByLCU (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncoding`.

  This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: 1d7890e96513817c127ef768f49c0b915ea22fa1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858151"
---
# <a name="blockencodingbylcu-function"></a><span data-ttu-id="20da2-102">BlockEncodingByLCU (funzione)</span><span class="sxs-lookup"><span data-stu-id="20da2-102">BlockEncodingByLCU function</span></span>

<span data-ttu-id="20da2-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="20da2-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="20da2-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="20da2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="20da2-105">Codifica un operatore di interesse in un oggetto `BlockEncoding` .</span><span class="sxs-lookup"><span data-stu-id="20da2-105">Encodes an operator of interest into a `BlockEncoding`.</span></span>

<span data-ttu-id="20da2-106">Questo costrutto un `BlockEncoding` $U unitario = P\cdot V\cdot P ^ \dagger $ che codifica un operatore $H = \ Sum_ {j} | \ alpha_j | U_j $ di interesse che è una combinazione lineare di unitaries.</span><span class="sxs-lookup"><span data-stu-id="20da2-106">This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries.</span></span> <span data-ttu-id="20da2-107">In genere, $P $ è un Unity di preparazione dello stato in modo che $P \ket {0} \_ a = \ sum_j \sqrt{\ alpha_j/ \| \vec\alpha \| \_ 2} \ket{j} \_ a $ e $V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $.</span><span class="sxs-lookup"><span data-stu-id="20da2-107">Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.</span></span>

```qsharp
function BlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl)) : (('T, 'S) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="20da2-108">Input</span><span class="sxs-lookup"><span data-stu-id="20da2-108">Input</span></span>

### <a name="statepreparation--t--unit--is-adj--ctl"></a><span data-ttu-id="20da2-109">statePreparation:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="20da2-109">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="20da2-110">Unitario $P $ che prepara uno stato di destinazione.</span><span class="sxs-lookup"><span data-stu-id="20da2-110">A unitary $P$ that prepares some target state.</span></span>


### <a name="selector--ts--unit--is-adj--ctl"></a><span data-ttu-id="20da2-111">selettore: (t, s) => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="20da2-111">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="20da2-112">Un Unity $V $ che codifica il componente unitaries di $H $.</span><span class="sxs-lookup"><span data-stu-id="20da2-112">A unitary $V$ that encodes the component unitaries of $H$.</span></span>



## <a name="output--ts--unit--is-adj--ctl"></a><span data-ttu-id="20da2-113">Output: (' t,') => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="20da2-113">Output : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="20da2-114">Un Unity $U $ agisce congiuntamente sui registri `a` e `s` tale codifica a blocchi $H $ e soddisfa $U ^ \Dagger = U $.</span><span class="sxs-lookup"><span data-stu-id="20da2-114">A unitary $U$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U^\dagger = U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="20da2-115">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="20da2-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="20da2-116">T</span><span class="sxs-lookup"><span data-stu-id="20da2-116">'T</span></span>


### <a name="s"></a><span data-ttu-id="20da2-117">Gli</span><span class="sxs-lookup"><span data-stu-id="20da2-117">'S</span></span>



## <a name="remarks"></a><span data-ttu-id="20da2-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="20da2-118">Remarks</span></span>

<span data-ttu-id="20da2-119">Questa `BlockEncoding` implementazione fornisce le proprietà di un oggetto `BlockEncodingReflection` .</span><span class="sxs-lookup"><span data-stu-id="20da2-119">This `BlockEncoding` implementation gives it the properties of a `BlockEncodingReflection`.</span></span>

## <a name="see-also"></a><span data-ttu-id="20da2-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20da2-120">See Also</span></span>

- [<span data-ttu-id="20da2-121">Microsoft. Quantum. Simulation. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="20da2-121">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="20da2-122">Microsoft. Quantum. Simulation. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="20da2-122">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)
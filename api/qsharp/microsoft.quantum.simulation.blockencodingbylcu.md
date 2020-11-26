---
uid: Microsoft.Quantum.Simulation.BlockEncodingByLCU
title: BlockEncodingByLCU (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncoding`.

  This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: 254ace01750f94e6c871de9b62f1342000bc84ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229546"
---
# <a name="blockencodingbylcu-function"></a><span data-ttu-id="04e0c-102">BlockEncodingByLCU (funzione)</span><span class="sxs-lookup"><span data-stu-id="04e0c-102">BlockEncodingByLCU function</span></span>

<span data-ttu-id="04e0c-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="04e0c-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="04e0c-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="04e0c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="04e0c-105">Codifica un operatore di interesse in un oggetto `BlockEncoding` .</span><span class="sxs-lookup"><span data-stu-id="04e0c-105">Encodes an operator of interest into a `BlockEncoding`.</span></span>

<span data-ttu-id="04e0c-106">Questo costrutto un `BlockEncoding` $U unitario = P\cdot V\cdot P ^ \dagger $ che codifica un operatore $H = \ Sum_ {j} | \ alpha_j | U_j $ di interesse che è una combinazione lineare di unitaries.</span><span class="sxs-lookup"><span data-stu-id="04e0c-106">This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries.</span></span> <span data-ttu-id="04e0c-107">In genere, $P $ è un Unity di preparazione dello stato in modo che $P \ket {0} \_ a = \ sum_j \sqrt{\ alpha_j/ \| \vec\alpha \| \_ 2} \ket{j} \_ a $ e $V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $.</span><span class="sxs-lookup"><span data-stu-id="04e0c-107">Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.</span></span>

```qsharp
function BlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl)) : (('T, 'S) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="04e0c-108">Input</span><span class="sxs-lookup"><span data-stu-id="04e0c-108">Input</span></span>

### <a name="statepreparation--t--unit--is-adj--ctl"></a><span data-ttu-id="04e0c-109">statePreparation:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="04e0c-109">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="04e0c-110">Unitario $P $ che prepara uno stato di destinazione.</span><span class="sxs-lookup"><span data-stu-id="04e0c-110">A unitary $P$ that prepares some target state.</span></span>


### <a name="selector--ts--unit--is-adj--ctl"></a><span data-ttu-id="04e0c-111">selettore: (t, s) => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="04e0c-111">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="04e0c-112">Un Unity $V $ che codifica il componente unitaries di $H $.</span><span class="sxs-lookup"><span data-stu-id="04e0c-112">A unitary $V$ that encodes the component unitaries of $H$.</span></span>



## <a name="output--ts--unit--is-adj--ctl"></a><span data-ttu-id="04e0c-113">Output: (' t,') => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="04e0c-113">Output : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="04e0c-114">Un Unity $U $ agisce congiuntamente sui registri `a` e `s` tale codifica a blocchi $H $ e soddisfa $U ^ \Dagger = U $.</span><span class="sxs-lookup"><span data-stu-id="04e0c-114">A unitary $U$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U^\dagger = U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="04e0c-115">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="04e0c-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="04e0c-116">T</span><span class="sxs-lookup"><span data-stu-id="04e0c-116">'T</span></span>


### <a name="s"></a><span data-ttu-id="04e0c-117">Gli</span><span class="sxs-lookup"><span data-stu-id="04e0c-117">'S</span></span>



## <a name="remarks"></a><span data-ttu-id="04e0c-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="04e0c-118">Remarks</span></span>

<span data-ttu-id="04e0c-119">Questa `BlockEncoding` implementazione fornisce le proprietà di un oggetto `BlockEncodingReflection` .</span><span class="sxs-lookup"><span data-stu-id="04e0c-119">This `BlockEncoding` implementation gives it the properties of a `BlockEncodingReflection`.</span></span>

## <a name="see-also"></a><span data-ttu-id="04e0c-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04e0c-120">See Also</span></span>

- [<span data-ttu-id="04e0c-121">Microsoft. Quantum. Simulation. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="04e0c-121">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="04e0c-122">Microsoft. Quantum. Simulation. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="04e0c-122">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)
---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget
title: Operazione ApplyXControlledOnTruthTableWithCleanTarget
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTableWithCleanTarget
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: a54544cd026f26784bb0c41cb12187a8885ed9db
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855541"
---
# <a name="applyxcontrolledontruthtablewithcleantarget-operation"></a><span data-ttu-id="a7c01-102">Operazione ApplyXControlledOnTruthTableWithCleanTarget</span><span class="sxs-lookup"><span data-stu-id="a7c01-102">ApplyXControlledOnTruthTableWithCleanTarget operation</span></span>

<span data-ttu-id="a7c01-103">Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="a7c01-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="a7c01-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a7c01-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a7c01-105">Applica l' @"microsoft.quantum.intrinsic.x" operazione su `target` , se la funzione booleana `func` restituisce true per l'assegnazione classica in `controlRegister` .</span><span class="sxs-lookup"><span data-stu-id="a7c01-105">Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.</span></span>

```qsharp
operation ApplyXControlledOnTruthTableWithCleanTarget (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="a7c01-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a7c01-106">Description</span></span>

<span data-ttu-id="a7c01-107">Questa operazione implementa un caso speciale di @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" , in cui il qubit di destinazione è noto come nello stato $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="a7c01-107">This operation implements a special case of @"microsoft.quantum.synthesis.applyxcontrolledontruthtable", in which the target qubit is known to be in the $\ket{0}$ state.</span></span>

<span data-ttu-id="a7c01-108">L'implementazione utilizza le attività di controllo @"microsoft.quantum.intrinsic.cnot" e @"microsoft.quantum.intrinsic.r1" .</span><span class="sxs-lookup"><span data-stu-id="a7c01-108">The implementation makes use of @"microsoft.quantum.intrinsic.cnot" and @"microsoft.quantum.intrinsic.r1" gates.</span></span>  <span data-ttu-id="a7c01-109">L'implementazione dell'operazione contigua è ottimizzata e utilizza l'incalcolo basato sulla misurazione.</span><span class="sxs-lookup"><span data-stu-id="a7c01-109">The implementation of the adjoint operation is optimized and uses measurement-based uncomputation.</span></span>

## <a name="input"></a><span data-ttu-id="a7c01-110">Input</span><span class="sxs-lookup"><span data-stu-id="a7c01-110">Input</span></span>

### <a name="func--bigint"></a><span data-ttu-id="a7c01-111">Func: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a7c01-111">func : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a7c01-112">Tabella di verità booleana rappresentata come valore Big Integer</span><span class="sxs-lookup"><span data-stu-id="a7c01-112">Boolean truth table represented as big integer</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="a7c01-113">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a7c01-113">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a7c01-114">Registro dei qubits di controllo</span><span class="sxs-lookup"><span data-stu-id="a7c01-114">Register of control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="a7c01-115">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a7c01-115">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a7c01-116">Qubit di destinazione (deve essere nello stato $ \ket {0} $)</span><span class="sxs-lookup"><span data-stu-id="a7c01-116">Target qubit (must be in $\ket{0}$ state)</span></span>



## <a name="output--unit"></a><span data-ttu-id="a7c01-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a7c01-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="a7c01-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7c01-118">See Also</span></span>

- [<span data-ttu-id="a7c01-119">Microsoft. Quantum. Synthesis. ApplyXControlledOnTruthTable</span><span class="sxs-lookup"><span data-stu-id="a7c01-119">Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable)
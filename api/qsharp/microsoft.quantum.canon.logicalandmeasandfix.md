---
uid: Microsoft.Quantum.Canon.LogicalANDMeasAndFix
title: Operazione LogicalANDMeasAndFix
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: LogicalANDMeasAndFix
qsharp.summary: Computes the logical AND of multiple qubits.
ms.openlocfilehash: 86e4b9a8c6ed5f4f56db0ceefc8051d34e911c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715924"
---
# <a name="logicalandmeasandfix-operation"></a><span data-ttu-id="6a4b7-102">Operazione LogicalANDMeasAndFix</span><span class="sxs-lookup"><span data-stu-id="6a4b7-102">LogicalANDMeasAndFix operation</span></span>

<span data-ttu-id="6a4b7-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6a4b7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6a4b7-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6a4b7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6a4b7-105">Calcola l'operatore AND logico di più qubits.</span><span class="sxs-lookup"><span data-stu-id="6a4b7-105">Computes the logical AND of multiple qubits.</span></span>

```qsharp
operation LogicalANDMeasAndFix (ctrlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="6a4b7-106">Input</span><span class="sxs-lookup"><span data-stu-id="6a4b7-106">Input</span></span>

### <a name="ctrlregister--qubit"></a><span data-ttu-id="6a4b7-107">ctrlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6a4b7-107">ctrlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6a4b7-108">Input di qubits per l'input multiplo e il controllo.</span><span class="sxs-lookup"><span data-stu-id="6a4b7-108">Qubits input to the multiple-input AND gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="6a4b7-109">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6a4b7-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="6a4b7-110">Qubit in cui viene scritto l'output di e.</span><span class="sxs-lookup"><span data-stu-id="6a4b7-110">Qubit on which output of AND is written to.</span></span> <span data-ttu-id="6a4b7-111">Si presuppone che si avvii sempre nello stato $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="6a4b7-111">This is assumed to always start in the $\ket{0}$ state.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6a4b7-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6a4b7-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6a4b7-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="6a4b7-113">Remarks</span></span>

<span data-ttu-id="6a4b7-114">Quando `ctrlRegister` ha esattamente $2 $ qubits, equivale all' `CCNOT` operazione ma alla fase con una fase $e ^ {i \ PI/2} $ su $ \ket {001} $ e $-e ^ {i \ PI/2} $ su $ \ket {101} $ e $ \ket {011} $.</span><span class="sxs-lookup"><span data-stu-id="6a4b7-114">When `ctrlRegister` has exactly $2$ qubits, this is equivalent to the `CCNOT` operation but phase with a phase $e^{i\Pi/2}$ on $\ket{001}$ and $-e^{i\Pi/2}$ on $\ket{101}$ and $\ket{011}$.</span></span>
<span data-ttu-id="6a4b7-115">Il contiguo è anche l'approccio di misura e correzione che è l'inverso dell'operazione originale solo in casi speciali (vedere i riferimenti), ma usa un numero inferiore di T-Gates.</span><span class="sxs-lookup"><span data-stu-id="6a4b7-115">The Adjoint is also measure-and-fixup approach that is the inverse of the original operation only in special cases (see references), but uses fewer T-gates.</span></span>

## <a name="references"></a><span data-ttu-id="6a4b7-116">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="6a4b7-116">References</span></span>

- [<span data-ttu-id="6a4b7-117">*Craig Gidney* , 1709,06648</span><span class="sxs-lookup"><span data-stu-id="6a4b7-117"> *Craig Gidney* , 1709.06648</span></span>](https://arxiv.org/abs/1709.06648)
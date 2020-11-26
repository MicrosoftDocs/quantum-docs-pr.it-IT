---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: Operazione MeasureIdentity
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: 4a169355d0669c67f0eb14c80e8554b2f24b035a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216116"
---
# <a name="measureidentity-operation"></a><span data-ttu-id="8ad5b-102">Operazione MeasureIdentity</span><span class="sxs-lookup"><span data-stu-id="8ad5b-102">MeasureIdentity operation</span></span>

<span data-ttu-id="8ad5b-103">Spazio dei nomi: [Microsoft. Quantum. characteration](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="8ad5b-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="8ad5b-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8ad5b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8ad5b-105">Misura l'operatore di identità in un registro di qubits.</span><span class="sxs-lookup"><span data-stu-id="8ad5b-105">Measures the identity operator on a register of qubits.</span></span>

```qsharp
operation MeasureIdentity (register : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="8ad5b-106">Input</span><span class="sxs-lookup"><span data-stu-id="8ad5b-106">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="8ad5b-107">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8ad5b-107">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="8ad5b-108">Registro da misurare.</span><span class="sxs-lookup"><span data-stu-id="8ad5b-108">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="8ad5b-109">Output: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="8ad5b-109">Output : __invalid<Result>__</span></span>

<span data-ttu-id="8ad5b-110">Valore del risultato `Zero` .</span><span class="sxs-lookup"><span data-stu-id="8ad5b-110">The result value `Zero`.</span></span>

## <a name="remarks"></a><span data-ttu-id="8ad5b-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="8ad5b-111">Remarks</span></span>

<span data-ttu-id="8ad5b-112">Poiché $ \boldone $ ha solo autovalore $1 $ e non ha un autovalore negativo, questa operazione restituisce sempre `Zero` , corrispondente a autovalore $ + 1 = (-1) ^ 0 $, e non provoca un collasso dello stato di `register` .</span><span class="sxs-lookup"><span data-stu-id="8ad5b-112">Since $\boldone$ has only the eigenvalue $1$, and does not have a negative eigenvalue, this operation always returns `Zero`, corresponding to the eigenvalue $+1 = (-1)^0$, and does not cause a collapse of the state of `register`.</span></span>

<span data-ttu-id="8ad5b-113">Da solo, questa operazione non è utile, ma è utile nel contesto della tomografia dei processi, poiché fornisce informazioni sulla conservazione delle tracce di un processo quantum.</span><span class="sxs-lookup"><span data-stu-id="8ad5b-113">On its own, this operation is not useful, but is helpful in the context of process tomography, as it provides information about the trace preservation of a quantum process.</span></span>
<span data-ttu-id="8ad5b-114">In particolare, un computer di destinazione con misurazione con perdita di dati deve sostituire questa operazione con una misurazione effettiva di $ \boldone $.</span><span class="sxs-lookup"><span data-stu-id="8ad5b-114">In particular, a target machine with lossy measurement should replace this operation by an actual measurement of $\boldone$.</span></span>
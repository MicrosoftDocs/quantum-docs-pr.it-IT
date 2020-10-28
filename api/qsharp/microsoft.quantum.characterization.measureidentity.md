---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: Operazione MeasureIdentity
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: 71a103fddb3a27703318975bea94bc7a22a9ce81
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714969"
---
# <a name="measureidentity-operation"></a><span data-ttu-id="1b27e-102">Operazione MeasureIdentity</span><span class="sxs-lookup"><span data-stu-id="1b27e-102">MeasureIdentity operation</span></span>

<span data-ttu-id="1b27e-103">Spazio dei nomi: [Microsoft. Quantum. characteration](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="1b27e-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="1b27e-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1b27e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1b27e-105">Misura l'operatore di identità in un registro di qubits.</span><span class="sxs-lookup"><span data-stu-id="1b27e-105">Measures the identity operator on a register of qubits.</span></span>

```qsharp
operation MeasureIdentity (register : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="1b27e-106">Input</span><span class="sxs-lookup"><span data-stu-id="1b27e-106">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="1b27e-107">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1b27e-107">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1b27e-108">Registro da misurare.</span><span class="sxs-lookup"><span data-stu-id="1b27e-108">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="1b27e-109">Output: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="1b27e-109">Output : __invalid<Result>__</span></span>

<span data-ttu-id="1b27e-110">Valore del risultato `Zero` .</span><span class="sxs-lookup"><span data-stu-id="1b27e-110">The result value `Zero`.</span></span>

## <a name="remarks"></a><span data-ttu-id="1b27e-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="1b27e-111">Remarks</span></span>

<span data-ttu-id="1b27e-112">Poiché $ \boldone $ ha solo autovalore $1 $ e non ha un autovalore negativo, questa operazione restituisce sempre `Zero` , corrispondente a autovalore $ + 1 = (-1) ^ 0 $, e non provoca un collasso dello stato di `register` .</span><span class="sxs-lookup"><span data-stu-id="1b27e-112">Since $\boldone$ has only the eigenvalue $1$, and does not have a negative eigenvalue, this operation always returns `Zero`, corresponding to the eigenvalue $+1 = (-1)^0$, and does not cause a collapse of the state of `register`.</span></span>

<span data-ttu-id="1b27e-113">Da solo, questa operazione non è utile, ma è utile nel contesto della tomografia dei processi, poiché fornisce informazioni sulla conservazione delle tracce di un processo quantum.</span><span class="sxs-lookup"><span data-stu-id="1b27e-113">On its own, this operation is not useful, but is helpful in the context of process tomography, as it provides information about the trace preservation of a quantum process.</span></span>
<span data-ttu-id="1b27e-114">In particolare, un computer di destinazione con misurazione con perdita di dati deve sostituire questa operazione con una misurazione effettiva di $ \boldone $.</span><span class="sxs-lookup"><span data-stu-id="1b27e-114">In particular, a target machine with lossy measurement should replace this operation by an actual measurement of $\boldone$.</span></span>
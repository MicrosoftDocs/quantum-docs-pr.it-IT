---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledAnd
title: Operazione ApplyMultiplyControlledAnd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.
ms.openlocfilehash: feca28d394e4af31eb4ffe737111d00ede45e27e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717954"
---
# <a name="applymultiplycontrolledand-operation"></a><span data-ttu-id="4ca93-102">Operazione ApplyMultiplyControlledAnd</span><span class="sxs-lookup"><span data-stu-id="4ca93-102">ApplyMultiplyControlledAnd operation</span></span>

<span data-ttu-id="4ca93-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4ca93-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4ca93-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4ca93-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4ca93-105">Implementa un controllo Toffoli a più controlli, supponendo che la destinazione qubit sia inizializzata su 0.</span><span class="sxs-lookup"><span data-stu-id="4ca93-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="4ca93-106">L'operazione contigua presuppone che il qubit di destinazione verrà reimpostato su 0.</span><span class="sxs-lookup"><span data-stu-id="4ca93-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>

```qsharp
operation ApplyMultiplyControlledAnd (controls : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="4ca93-107">Input</span><span class="sxs-lookup"><span data-stu-id="4ca93-107">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="4ca93-108">Controlli: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="4ca93-108">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="4ca93-109">Qubits di controllo</span><span class="sxs-lookup"><span data-stu-id="4ca93-109">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="4ca93-110">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4ca93-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4ca93-111">Qubit di destinazione</span><span class="sxs-lookup"><span data-stu-id="4ca93-111">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="4ca93-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4ca93-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


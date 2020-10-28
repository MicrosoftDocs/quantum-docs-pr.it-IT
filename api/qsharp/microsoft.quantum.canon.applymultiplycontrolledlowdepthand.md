---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledLowDepthAnd
title: Operazione ApplyMultiplyControlledLowDepthAnd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledLowDepthAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.  Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.
ms.openlocfilehash: 6900f9b0f014fba28ae73a70f180f3e4696900cd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717951"
---
# <a name="applymultiplycontrolledlowdepthand-operation"></a><span data-ttu-id="5bc17-102">Operazione ApplyMultiplyControlledLowDepthAnd</span><span class="sxs-lookup"><span data-stu-id="5bc17-102">ApplyMultiplyControlledLowDepthAnd operation</span></span>

<span data-ttu-id="5bc17-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5bc17-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5bc17-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5bc17-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5bc17-105">Implementa un controllo Toffoli a più controlli, supponendo che la destinazione qubit sia inizializzata su 0.</span><span class="sxs-lookup"><span data-stu-id="5bc17-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="5bc17-106">L'operazione contigua presuppone che il qubit di destinazione verrà reimpostato su 0.</span><span class="sxs-lookup"><span data-stu-id="5bc17-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>  <span data-ttu-id="5bc17-107">Richiede una profondità RZ di 1, mentre il numero di qubits Helper è esponenziale nel numero di qubits.</span><span class="sxs-lookup"><span data-stu-id="5bc17-107">Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.</span></span>

```qsharp
operation ApplyMultiplyControlledLowDepthAnd (controls : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="5bc17-108">Input</span><span class="sxs-lookup"><span data-stu-id="5bc17-108">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="5bc17-109">Controlli: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5bc17-109">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5bc17-110">Qubits di controllo</span><span class="sxs-lookup"><span data-stu-id="5bc17-110">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="5bc17-111">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="5bc17-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="5bc17-112">Qubit di destinazione</span><span class="sxs-lookup"><span data-stu-id="5bc17-112">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="5bc17-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5bc17-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


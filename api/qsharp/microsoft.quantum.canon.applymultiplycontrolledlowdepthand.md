---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledLowDepthAnd
title: Operazione ApplyMultiplyControlledLowDepthAnd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledLowDepthAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.  Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.
ms.openlocfilehash: 0ad4b6eabcbbb63751489dd92a13a6673c1ae6b1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841667"
---
# <a name="applymultiplycontrolledlowdepthand-operation"></a><span data-ttu-id="16386-102">Operazione ApplyMultiplyControlledLowDepthAnd</span><span class="sxs-lookup"><span data-stu-id="16386-102">ApplyMultiplyControlledLowDepthAnd operation</span></span>

<span data-ttu-id="16386-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="16386-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="16386-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="16386-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="16386-105">Implementa un controllo Toffoli a più controlli, supponendo che la destinazione qubit sia inizializzata su 0.</span><span class="sxs-lookup"><span data-stu-id="16386-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="16386-106">L'operazione contigua presuppone che il qubit di destinazione verrà reimpostato su 0.</span><span class="sxs-lookup"><span data-stu-id="16386-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>  <span data-ttu-id="16386-107">Richiede una profondità RZ di 1, mentre il numero di qubits Helper è esponenziale nel numero di qubits.</span><span class="sxs-lookup"><span data-stu-id="16386-107">Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.</span></span>

```qsharp
operation ApplyMultiplyControlledLowDepthAnd (controls : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="16386-108">Input</span><span class="sxs-lookup"><span data-stu-id="16386-108">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="16386-109">Controlli: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="16386-109">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="16386-110">Qubits di controllo</span><span class="sxs-lookup"><span data-stu-id="16386-110">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="16386-111">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="16386-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="16386-112">Qubit di destinazione</span><span class="sxs-lookup"><span data-stu-id="16386-112">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="16386-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="16386-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


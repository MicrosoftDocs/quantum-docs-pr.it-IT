---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode
title: Operazione EncodeIntoBitFlipCode
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoBitFlipCode
qsharp.summary: Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: b27759caba3c5dd363dbdf24d6e5de76870173cf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200952"
---
# <a name="encodeintobitflipcode-operation"></a><span data-ttu-id="16c9d-102">Operazione EncodeIntoBitFlipCode</span><span class="sxs-lookup"><span data-stu-id="16c9d-102">EncodeIntoBitFlipCode operation</span></span>

<span data-ttu-id="16c9d-103">Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="16c9d-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="16c9d-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="16c9d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="16c9d-105">Codifica nel codice [3, 1, 3]/⟦ 3, 1, 1 ⟧ bit-flip.</span><span class="sxs-lookup"><span data-stu-id="16c9d-105">Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.</span></span>

```qsharp
operation EncodeIntoBitFlipCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="16c9d-106">Input</span><span class="sxs-lookup"><span data-stu-id="16c9d-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="16c9d-107">physRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="16c9d-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="16c9d-108">Registro di qubits fisico che rappresenta i dati da proteggere.</span><span class="sxs-lookup"><span data-stu-id="16c9d-108">A register of physical qubits representing the data to be protected.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="16c9d-109">auxQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="16c9d-109">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="16c9d-110">Registro di qubits ausiliario inizialmente nello stato $ \ket {00} $ da utilizzare per la codifica dei dati da proteggere.</span><span class="sxs-lookup"><span data-stu-id="16c9d-110">A register of auxiliary qubits initially in the $\ket{00}$ state to be used in encoding the data to be protected.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="16c9d-111">Output: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="16c9d-111">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="16c9d-112">Qubits fisico e ausiliario utilizzati nella codifica, rappresentati come registro logico.</span><span class="sxs-lookup"><span data-stu-id="16c9d-112">The physical and auxiliary qubits used in encoding, represented as a logical register.</span></span>

## <a name="see-also"></a><span data-ttu-id="16c9d-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16c9d-113">See Also</span></span>

- [<span data-ttu-id="16c9d-114">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="16c9d-114">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
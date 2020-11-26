---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: Operazione MeasureAllZ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 6c44ab6a7983697644071f0e3cf106e9825661ee
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227081"
---
# <a name="measureallz-operation"></a><span data-ttu-id="efacd-102">Operazione MeasureAllZ</span><span class="sxs-lookup"><span data-stu-id="efacd-102">MeasureAllZ operation</span></span>

<span data-ttu-id="efacd-103">Spazio dei nomi: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="efacd-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="efacd-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="efacd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="efacd-105">Misura in modo comune un registro di qubits in base a Pauli Z.</span><span class="sxs-lookup"><span data-stu-id="efacd-105">Jointly measures a register of qubits in the Pauli Z basis.</span></span>

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a><span data-ttu-id="efacd-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="efacd-106">Description</span></span>

<span data-ttu-id="efacd-107">Misura un registro di qubits nel $Z \otimes Z \otimes \cdots \otimes Z $, che rappresenta la parità dell'intero registro.</span><span class="sxs-lookup"><span data-stu-id="efacd-107">Measures a register of qubits in the $Z \otimes Z \otimes \cdots \otimes Z$ basis, representing the parity of the entire register.</span></span>

## <a name="input"></a><span data-ttu-id="efacd-108">Input</span><span class="sxs-lookup"><span data-stu-id="efacd-108">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="efacd-109">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="efacd-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="efacd-110">Registro da misurare.</span><span class="sxs-lookup"><span data-stu-id="efacd-110">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="efacd-111">Output: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="efacd-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="efacd-112">Risultato della misurazione $Z \otimes Z \otimes \cdots \otimes Z $.</span><span class="sxs-lookup"><span data-stu-id="efacd-112">The result of measuring $Z \otimes Z \otimes \cdots \otimes Z$.</span></span>
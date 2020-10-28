---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: Operazione MeasureAllZ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 4ac36a77b37f672859e61f3db89a43f4ca1fc93c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711077"
---
# <a name="measureallz-operation"></a><span data-ttu-id="45bfe-102">Operazione MeasureAllZ</span><span class="sxs-lookup"><span data-stu-id="45bfe-102">MeasureAllZ operation</span></span>

<span data-ttu-id="45bfe-103">Spazio dei nomi: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="45bfe-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="45bfe-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="45bfe-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="45bfe-105">Misura in modo comune un registro di qubits in base a Pauli Z.</span><span class="sxs-lookup"><span data-stu-id="45bfe-105">Jointly measures a register of qubits in the Pauli Z basis.</span></span>

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a><span data-ttu-id="45bfe-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="45bfe-106">Description</span></span>

<span data-ttu-id="45bfe-107">Misura un registro di qubits nel $Z \otimes Z \otimes \cdots \otimes Z $, che rappresenta la parità dell'intero registro.</span><span class="sxs-lookup"><span data-stu-id="45bfe-107">Measures a register of qubits in the $Z \otimes Z \otimes \cdots \otimes Z$ basis, representing the parity of the entire register.</span></span>

## <a name="input"></a><span data-ttu-id="45bfe-108">Input</span><span class="sxs-lookup"><span data-stu-id="45bfe-108">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="45bfe-109">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="45bfe-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="45bfe-110">Registro da misurare.</span><span class="sxs-lookup"><span data-stu-id="45bfe-110">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="45bfe-111">Output: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="45bfe-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="45bfe-112">Risultato della misurazione $Z \otimes Z \otimes \cdots \otimes Z $.</span><span class="sxs-lookup"><span data-stu-id="45bfe-112">The result of measuring $Z \otimes Z \otimes \cdots \otimes Z$.</span></span>
---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoFiveQubitCode
title: Operazione EncodeIntoFiveQubitCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoFiveQubitCode
qsharp.summary: Encodes into the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: c9df4c5c98a78cae8b3af4597020d35469454153
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712396"
---
# <a name="encodeintofivequbitcode-operation"></a><span data-ttu-id="06fbd-102">Operazione EncodeIntoFiveQubitCode</span><span class="sxs-lookup"><span data-stu-id="06fbd-102">EncodeIntoFiveQubitCode operation</span></span>

<span data-ttu-id="06fbd-103">Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="06fbd-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="06fbd-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="06fbd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="06fbd-105">Codifica nel codice Quantum ⟧ ⟦ 5, 1, 3.</span><span class="sxs-lookup"><span data-stu-id="06fbd-105">Encodes into the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
operation EncodeIntoFiveQubitCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="06fbd-106">Input</span><span class="sxs-lookup"><span data-stu-id="06fbd-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="06fbd-107">physRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="06fbd-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="06fbd-108">Qubit che rappresenta uno stato non codificato.</span><span class="sxs-lookup"><span data-stu-id="06fbd-108">A qubit representing an unencoded state.</span></span> <span data-ttu-id="06fbd-109">Questa matrice `Qubit[]` è di lunghezza 1.</span><span class="sxs-lookup"><span data-stu-id="06fbd-109">This array `Qubit[]` is of length 1.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="06fbd-110">auxQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="06fbd-110">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="06fbd-111">Registro di qubits ausiliario che verrà usato per rappresentare lo stato codificato.</span><span class="sxs-lookup"><span data-stu-id="06fbd-111">A register of auxiliary qubits that will be used to represent the encoded state.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="06fbd-112">Output: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="06fbd-112">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="06fbd-113">Matrice di qubits fisici di tipo `LogicalRegister` che archivia lo stato codificato.</span><span class="sxs-lookup"><span data-stu-id="06fbd-113">An array of physical qubits of type `LogicalRegister` that store the encoded state.</span></span>

## <a name="see-also"></a><span data-ttu-id="06fbd-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06fbd-114">See Also</span></span>

- [<span data-ttu-id="06fbd-115">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="06fbd-115">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
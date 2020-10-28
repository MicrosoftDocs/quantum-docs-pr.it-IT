---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromFiveQubitCode
title: Operazione DecodeFromFiveQubitCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromFiveQubitCode
qsharp.summary: Decodes the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 421da6296b604f30aefed58730091f64f19c3a61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712466"
---
# <a name="decodefromfivequbitcode-operation"></a><span data-ttu-id="57618-102">Operazione DecodeFromFiveQubitCode</span><span class="sxs-lookup"><span data-stu-id="57618-102">DecodeFromFiveQubitCode operation</span></span>

<span data-ttu-id="57618-103">Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="57618-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="57618-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="57618-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="57618-105">Decodifica il codice Quantum ⟧ ⟦ 5, 1, 3.</span><span class="sxs-lookup"><span data-stu-id="57618-105">Decodes the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
operation DecodeFromFiveQubitCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a><span data-ttu-id="57618-106">Input</span><span class="sxs-lookup"><span data-stu-id="57618-106">Input</span></span>

### <a name="logicalregister--logicalregister"></a><span data-ttu-id="57618-107">logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="57618-107">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="57618-108">Matrice di qubits che rappresenta lo stato logico del codice 5 qubit codificato.</span><span class="sxs-lookup"><span data-stu-id="57618-108">An array of qubits representing the encoded 5-qubit code logical state.</span></span>



## <a name="output--qubitqubit"></a><span data-ttu-id="57618-109">Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span><span class="sxs-lookup"><span data-stu-id="57618-109">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span></span>

<span data-ttu-id="57618-110">Matrice qubit di lunghezza 1 che rappresenta lo stato non codificato nel primo parametro, insieme al qubits ausiliario nel secondo parametro.</span><span class="sxs-lookup"><span data-stu-id="57618-110">A qubit array of length 1 representing the unencoded state in the first parameter, together with auxiliary qubits in the second parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="57618-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57618-111">See Also</span></span>

- [<span data-ttu-id="57618-112">Microsoft. Quantum. ErrorCorrection. FiveQubitCodeEncoder</span><span class="sxs-lookup"><span data-stu-id="57618-112">Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoder)
- [<span data-ttu-id="57618-113">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="57618-113">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
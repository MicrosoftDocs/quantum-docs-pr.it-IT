---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromSteaneCode
title: Operazione DecodeFromSteaneCode
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromSteaneCode
qsharp.summary: An inverse encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 50fc6fb22e8b65ce10aba41e18362ad96236a907
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201139"
---
# <a name="decodefromsteanecode-operation"></a><span data-ttu-id="e9c3d-102">Operazione DecodeFromSteaneCode</span><span class="sxs-lookup"><span data-stu-id="e9c3d-102">DecodeFromSteaneCode operation</span></span>

<span data-ttu-id="e9c3d-103">Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="e9c3d-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="e9c3d-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e9c3d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e9c3d-105">Operazione di codifica inversa che esegue il mapping di un registro quantum non codificato a un registro Quantum codificato nel codice quantico ⟦ 7, 1, 3 ⟧ Steane.</span><span class="sxs-lookup"><span data-stu-id="e9c3d-105">An inverse encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
operation DecodeFromSteaneCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a><span data-ttu-id="e9c3d-106">Input</span><span class="sxs-lookup"><span data-stu-id="e9c3d-106">Input</span></span>

### <a name="logicalregister--logicalregister"></a><span data-ttu-id="e9c3d-107">logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="e9c3d-107">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="e9c3d-108">Matrice di qubits che rappresenta lo stato logico del codice 5 qubit codificato.</span><span class="sxs-lookup"><span data-stu-id="e9c3d-108">An array of qubits representing the encoded 5-qubit code logical state.</span></span>



## <a name="output--qubitqubit"></a><span data-ttu-id="e9c3d-109">Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span><span class="sxs-lookup"><span data-stu-id="e9c3d-109">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span></span>

<span data-ttu-id="e9c3d-110">Matrice qubit di lunghezza 1 che rappresenta lo stato non codificato nel primo parametro, insieme al qubits ausiliario nel secondo parametro.</span><span class="sxs-lookup"><span data-stu-id="e9c3d-110">A qubit array of length 1 representing the unencoded state in the first parameter, together with auxiliary qubits in the second parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="e9c3d-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="e9c3d-111">Remarks</span></span>

<span data-ttu-id="e9c3d-112">Il decodificatore scelto usa la proprietà del codice CSS del codice Steane ⟧ ⟦ 7, 1, 3, ovvero corregge gli errori X e Z separatamente.</span><span class="sxs-lookup"><span data-stu-id="e9c3d-112">The chosen decoder uses the CSS code property of the ⟦7, 1, 3⟧ Steane code, i.e., it corrects X errors and Z errors separately.</span></span> <span data-ttu-id="e9c3d-113">Una proprietà del codice è che la posizione della X, rispettivamente, della correzione Z da applicare è la codifica a 3 bit della sindrome X, rispettivamente, Z quando viene considerato un numero intero.</span><span class="sxs-lookup"><span data-stu-id="e9c3d-113">A property of the code is that the location of the X, respectively, Z correction to be applied is the 3-bit encoding of the X, respectively, Z syndrome when considered an integer.</span></span>

## <a name="references"></a><span data-ttu-id="e9c3d-114">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="e9c3d-114">References</span></span>

- <span data-ttu-id="e9c3d-115">D.</span><span class="sxs-lookup"><span data-stu-id="e9c3d-115">D.</span></span> <span data-ttu-id="e9c3d-116">Gottesman, "codici stabilizzatori e correzione errori Quantum", Ph.D. tesi, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span><span class="sxs-lookup"><span data-stu-id="e9c3d-116">Gottesman, "Stabilizer Codes and Quantum Error Correction," Ph.D. Thesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span></span>

## <a name="see-also"></a><span data-ttu-id="e9c3d-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9c3d-117">See Also</span></span>

- [<span data-ttu-id="e9c3d-118">Microsoft. Quantum. ErrorCorrection. SteaneCodeEncoder</span><span class="sxs-lookup"><span data-stu-id="e9c3d-118">Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder)
- [<span data-ttu-id="e9c3d-119">Microsoft. Quantum. ErrorCorrection. SteaneCodeDecoder</span><span class="sxs-lookup"><span data-stu-id="e9c3d-119">Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)
- [<span data-ttu-id="e9c3d-120">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="e9c3d-120">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
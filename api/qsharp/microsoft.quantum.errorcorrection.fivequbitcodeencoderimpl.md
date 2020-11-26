---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoderImpl
title: Operazione FiveQubitCodeEncoderImpl
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeEncoderImpl
qsharp.summary: Private operation used to implement both the 5 qubit encoder and decoder.
ms.openlocfilehash: f70d2d1352c7b2eebee7a863eba97d78d7351dab
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200850"
---
# <a name="fivequbitcodeencoderimpl-operation"></a><span data-ttu-id="d47c8-102">Operazione FiveQubitCodeEncoderImpl</span><span class="sxs-lookup"><span data-stu-id="d47c8-102">FiveQubitCodeEncoderImpl operation</span></span>

<span data-ttu-id="d47c8-103">Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="d47c8-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="d47c8-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d47c8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d47c8-105">Operazione privata usata per implementare il codificatore e il decodificatore qubit 5.</span><span class="sxs-lookup"><span data-stu-id="d47c8-105">Private operation used to implement both the 5 qubit encoder and decoder.</span></span>

```qsharp
operation FiveQubitCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="d47c8-106">Input</span><span class="sxs-lookup"><span data-stu-id="d47c8-106">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="d47c8-107">dati: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d47c8-107">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d47c8-108">matrice contenente 1 qubit che rappresenta il qubit di input.</span><span class="sxs-lookup"><span data-stu-id="d47c8-108">an array holding 1 qubit which is the input qubit.</span></span>


### <a name="scratch--qubit"></a><span data-ttu-id="d47c8-109">Scratch: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d47c8-109">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d47c8-110">matrice contenente 4 qubits che aggiungono ridondanza.</span><span class="sxs-lookup"><span data-stu-id="d47c8-110">an array holding 4 qubits which add redundancy.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d47c8-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d47c8-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d47c8-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="d47c8-112">Remarks</span></span>

<span data-ttu-id="d47c8-113">Il codificatore particolare scelto è stato tratto dal documento V. Kliuchnikov e D. Maslov, "Optimization of Clifford Circuits," fisico. Rev. inv. Rev. A 88, 052307 (2013); https://arxiv.org/abs/1305.0810, Figura 4b) e richiede un totale di 11 Gate.</span><span class="sxs-lookup"><span data-stu-id="d47c8-113">The particular encoder chosen was taken from the paper V. Kliuchnikov and D. Maslov, "Optimization of Clifford Circuits," Phys. Rev. Phys. Rev. A 88, 052307 (2013); https://arxiv.org/abs/1305.0810, Figure 4b) and requires a total of 11 gates.</span></span>
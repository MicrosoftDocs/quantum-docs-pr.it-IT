---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoderImpl
title: Operazione FiveQubitCodeEncoderImpl
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeEncoderImpl
qsharp.summary: Private operation used to implement both the 5 qubit encoder and decoder.
ms.openlocfilehash: 29b0f47ddffeae3ed4dfda4084304427418e02fd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712337"
---
# <a name="fivequbitcodeencoderimpl-operation"></a><span data-ttu-id="749c3-102">Operazione FiveQubitCodeEncoderImpl</span><span class="sxs-lookup"><span data-stu-id="749c3-102">FiveQubitCodeEncoderImpl operation</span></span>

<span data-ttu-id="749c3-103">Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="749c3-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="749c3-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="749c3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="749c3-105">Operazione privata usata per implementare il codificatore e il decodificatore qubit 5.</span><span class="sxs-lookup"><span data-stu-id="749c3-105">Private operation used to implement both the 5 qubit encoder and decoder.</span></span>

```qsharp
operation FiveQubitCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="749c3-106">Input</span><span class="sxs-lookup"><span data-stu-id="749c3-106">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="749c3-107">dati: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="749c3-107">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="749c3-108">matrice contenente 1 qubit che rappresenta il qubit di input.</span><span class="sxs-lookup"><span data-stu-id="749c3-108">an array holding 1 qubit which is the input qubit.</span></span>


### <a name="scratch--qubit"></a><span data-ttu-id="749c3-109">Scratch: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="749c3-109">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="749c3-110">matrice contenente 4 qubits che aggiungono ridondanza.</span><span class="sxs-lookup"><span data-stu-id="749c3-110">an array holding 4 qubits which add redundancy.</span></span>



## <a name="output--unit"></a><span data-ttu-id="749c3-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="749c3-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="749c3-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="749c3-112">Remarks</span></span>

<span data-ttu-id="749c3-113">Il codificatore particolare scelto è stato tratto dal documento V. Kliuchnikov e D. Maslov, "Optimization of Clifford Circuits," fisico. Rev. inv. Rev. A 88, 052307 (2013); https://arxiv.org/abs/1305.0810, Figura 4b) e richiede un totale di 11 Gate.</span><span class="sxs-lookup"><span data-stu-id="749c3-113">The particular encoder chosen was taken from the paper V. Kliuchnikov and D. Maslov, "Optimization of Clifford Circuits," Phys. Rev. Phys. Rev. A 88, 052307 (2013); https://arxiv.org/abs/1305.0810, Figure 4b) and requires a total of 11 gates.</span></span>
---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoderImpl
title: Operazione SteaneCodeEncoderImpl
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeEncoderImpl
qsharp.summary: Private operation used to implement both the Steane code encoder and decoder.
ms.openlocfilehash: b843422a6007d01de9b57ec659c229b8ab0ad2e6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712186"
---
# <a name="steanecodeencoderimpl-operation"></a><span data-ttu-id="714a8-102">Operazione SteaneCodeEncoderImpl</span><span class="sxs-lookup"><span data-stu-id="714a8-102">SteaneCodeEncoderImpl operation</span></span>

<span data-ttu-id="714a8-103">Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="714a8-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="714a8-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="714a8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="714a8-105">Operazione privata usata per implementare il codificatore di codice Steane e il decodificatore.</span><span class="sxs-lookup"><span data-stu-id="714a8-105">Private operation used to implement both the Steane code encoder and decoder.</span></span>

```qsharp
operation SteaneCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="714a8-106">Input</span><span class="sxs-lookup"><span data-stu-id="714a8-106">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="714a8-107">dati: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="714a8-107">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="714a8-108">matrice contenente 1 qubit che rappresenta il qubit di input.</span><span class="sxs-lookup"><span data-stu-id="714a8-108">an array holding 1 qubit which is the input qubit.</span></span>


### <a name="scratch--qubit"></a><span data-ttu-id="714a8-109">Scratch: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="714a8-109">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="714a8-110">matrice contenente 6 qubits che aggiungono ridondanza.</span><span class="sxs-lookup"><span data-stu-id="714a8-110">an array holding 6 qubits which add redundancy.</span></span>



## <a name="output--unit"></a><span data-ttu-id="714a8-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="714a8-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

---
uid: Microsoft.Quantum.ErrorCorrection.ApplyBitFlipEncoder
title: Operazione ApplyBitFlipEncoder
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: ApplyBitFlipEncoder
qsharp.summary: >-
  Private operation used to implement both the bit flip encoder and decoder.

  Note that this encoder can make use of in-place coherent recovery, in which case it will "cause" the error described by the initial state of `auxQubits`. In particular, if `auxQubits` are initially in the state $\ket{10}$, this will cause an $X_1$ error on the encoded qubit.
ms.openlocfilehash: cc70cc409cb472a747899838d3a9ad2d78f6b5ab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827702"
---
# <a name="applybitflipencoder-operation"></a><span data-ttu-id="bea17-102">Operazione ApplyBitFlipEncoder</span><span class="sxs-lookup"><span data-stu-id="bea17-102">ApplyBitFlipEncoder operation</span></span>

<span data-ttu-id="bea17-103">Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="bea17-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="bea17-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bea17-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bea17-105">Operazione privata usata per implementare il codificatore bit flip e il decodificatore.</span><span class="sxs-lookup"><span data-stu-id="bea17-105">Private operation used to implement both the bit flip encoder and decoder.</span></span>

<span data-ttu-id="bea17-106">Si noti che questo codificatore può utilizzare il ripristino coerente sul posto, nel qual caso verrà "causa" l'errore descritto dallo stato iniziale di `auxQubits` .</span><span class="sxs-lookup"><span data-stu-id="bea17-106">Note that this encoder can make use of in-place coherent recovery, in which case it will "cause" the error described by the initial state of `auxQubits`.</span></span>
<span data-ttu-id="bea17-107">In particolare, se `auxQubits` inizialmente si trova nello stato $ \ket {10} $, verrà generato un errore $X _1 $ sul qubit codificato.</span><span class="sxs-lookup"><span data-stu-id="bea17-107">In particular, if `auxQubits` are initially in the state $\ket{10}$, this will cause an $X_1$ error on the encoded qubit.</span></span>

```qsharp
operation ApplyBitFlipEncoder (coherentRecovery : Bool, data : Qubit[], scratch : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="bea17-108">Input</span><span class="sxs-lookup"><span data-stu-id="bea17-108">Input</span></span>

### <a name="coherentrecovery--bool"></a><span data-ttu-id="bea17-109">coherentRecovery: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="bea17-109">coherentRecovery : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="data--qubit"></a><span data-ttu-id="bea17-110">dati: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="bea17-110">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="scratch--qubit"></a><span data-ttu-id="bea17-111">Scratch: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="bea17-111">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="bea17-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bea17-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="bea17-113">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="bea17-113">References</span></span>

- <span data-ttu-id="bea17-114">DOI: 10.1103/PhysRevA. 85.044302</span><span class="sxs-lookup"><span data-stu-id="bea17-114">doi:10.1103/PhysRevA.85.044302</span></span>
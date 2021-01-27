---
uid: Microsoft.Quantum.Preparation.PrepareIdentity
title: Operazione PrepareIdentity
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareIdentity
qsharp.summary: >-
  Given a register, prepares that register in the maximally mixed state.

  The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.
ms.openlocfilehash: ec7e813110ccd9e6d499fc469fa27249a182b870
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855883"
---
# <a name="prepareidentity-operation"></a><span data-ttu-id="3e7f7-102">Operazione PrepareIdentity</span><span class="sxs-lookup"><span data-stu-id="3e7f7-102">PrepareIdentity operation</span></span>

<span data-ttu-id="3e7f7-103">Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="3e7f7-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="3e7f7-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3e7f7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3e7f7-105">Dato un registro, prepara il registro nello stato massimo misto.</span><span class="sxs-lookup"><span data-stu-id="3e7f7-105">Given a register, prepares that register in the maximally mixed state.</span></span>

<span data-ttu-id="3e7f7-106">Il registro viene preparato nello stato $ \boldone/2 ^ N $ applicando il canale depolarizzato completo a ogni qubit, dove $N $ è la lunghezza del registro.</span><span class="sxs-lookup"><span data-stu-id="3e7f7-106">The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.</span></span>

```qsharp
operation PrepareIdentity (register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="3e7f7-107">Input</span><span class="sxs-lookup"><span data-stu-id="3e7f7-107">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="3e7f7-108">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3e7f7-108">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3e7f7-109">Un registro il cui stato deve essere depolarizzato nel modo descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="3e7f7-109">A register whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3e7f7-110">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3e7f7-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="3e7f7-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e7f7-111">See Also</span></span>

- [<span data-ttu-id="3e7f7-112">Microsoft. Quantum. preping. PrepareSingleQubitIdentity</span><span class="sxs-lookup"><span data-stu-id="3e7f7-112">Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity</span></span>](xref:Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity)
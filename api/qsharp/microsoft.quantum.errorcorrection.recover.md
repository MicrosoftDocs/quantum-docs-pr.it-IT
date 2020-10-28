---
uid: Microsoft.Quantum.ErrorCorrection.Recover
title: Operazione di ripristino
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: Recover
qsharp.summary: Performs a single round of error correction by a quantum code described by a `QECC` type.
ms.openlocfilehash: a659399f51794a4edc1d2ff43da84e46797103fb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712211"
---
# <a name="recover-operation"></a><span data-ttu-id="939ef-102">Operazione di ripristino</span><span class="sxs-lookup"><span data-stu-id="939ef-102">Recover operation</span></span>

<span data-ttu-id="939ef-103">Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="939ef-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="939ef-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="939ef-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="939ef-105">Esegue un singolo ciclo di correzione degli errori in base a un codice quantico descritto da un `QECC` tipo.</span><span class="sxs-lookup"><span data-stu-id="939ef-105">Performs a single round of error correction by a quantum code described by a `QECC` type.</span></span>

```qsharp
operation Recover (code : Microsoft.Quantum.ErrorCorrection.QECC, fn : Microsoft.Quantum.ErrorCorrection.RecoveryFn, logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : Unit
```


## <a name="input"></a><span data-ttu-id="939ef-106">Input</span><span class="sxs-lookup"><span data-stu-id="939ef-106">Input</span></span>

### <a name="code--qecc"></a><span data-ttu-id="939ef-107">Codice: [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="939ef-107">code : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="939ef-108">Un codice di correzione degli errori Quantum in pacchetto come `QECC` tipo descrive la codifica e la decodifica dei dati quantistici e come devono essere misurate le sindromi degli errori.</span><span class="sxs-lookup"><span data-stu-id="939ef-108">A quantum error-correcting code packaged as a `QECC` type describes the encoding and decoding of quantum data, and how error syndromes are to be measured.</span></span>


### <a name="fn--recoveryfn"></a><span data-ttu-id="939ef-109">FN: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="939ef-109">fn : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="939ef-110">Oggetto `RecoveryFn` che esegue il mapping di ogni sindrome di errore alle `Pauli[]` operazioni che correggono l'errore rilevato.</span><span class="sxs-lookup"><span data-stu-id="939ef-110">A `RecoveryFn` that maps each error syndrome to the `Pauli[]` operations that correct the detected error.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="939ef-111">logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="939ef-111">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="939ef-112">Matrice di qubits in cui è definito il codice di stabilizzazione.</span><span class="sxs-lookup"><span data-stu-id="939ef-112">An array of qubits where the stabilizer code is defined.</span></span>



## <a name="output--unit"></a><span data-ttu-id="939ef-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="939ef-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="939ef-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="939ef-114">See Also</span></span>

- [<span data-ttu-id="939ef-115">Microsoft. Quantum. ErrorCorrection. QECC</span><span class="sxs-lookup"><span data-stu-id="939ef-115">Microsoft.Quantum.ErrorCorrection.QECC</span></span>](xref:Microsoft.Quantum.ErrorCorrection.QECC)
- [<span data-ttu-id="939ef-116">Microsoft. Quantum. ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="939ef-116">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
- [<span data-ttu-id="939ef-117">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="939ef-117">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
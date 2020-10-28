---
uid: Microsoft.Quantum.ErrorCorrection.RecoverCSS
title: Operazione RecoverCSS
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: RecoverCSS
qsharp.summary: Performs a single round of error correction by a quantum code described by a `CSS` type.
ms.openlocfilehash: 48d3cd3d5f6aea265fac2f50b913ab855a31accf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712200"
---
# <a name="recovercss-operation"></a><span data-ttu-id="3b06f-102">Operazione RecoverCSS</span><span class="sxs-lookup"><span data-stu-id="3b06f-102">RecoverCSS operation</span></span>

<span data-ttu-id="3b06f-103">Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="3b06f-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="3b06f-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3b06f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3b06f-105">Esegue un singolo ciclo di correzione degli errori in base a un codice quantico descritto da un `CSS` tipo.</span><span class="sxs-lookup"><span data-stu-id="3b06f-105">Performs a single round of error correction by a quantum code described by a `CSS` type.</span></span>

```qsharp
operation RecoverCSS (code : Microsoft.Quantum.ErrorCorrection.CSS, fnX : Microsoft.Quantum.ErrorCorrection.RecoveryFn, fnZ : Microsoft.Quantum.ErrorCorrection.RecoveryFn, logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : Unit
```


## <a name="input"></a><span data-ttu-id="3b06f-106">Input</span><span class="sxs-lookup"><span data-stu-id="3b06f-106">Input</span></span>

### <a name="code--css"></a><span data-ttu-id="3b06f-107">Codice: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span><span class="sxs-lookup"><span data-stu-id="3b06f-107">code : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span></span>

<span data-ttu-id="3b06f-108">Un errore CSS Quantum: la correzione del codice in pacchetto come `CSS` tipo descrive la codifica e la decodifica dei dati quantistici e come devono essere misurate le sindromi degli errori.</span><span class="sxs-lookup"><span data-stu-id="3b06f-108">A quantum CSS error-correcting code packaged as a `CSS` type describes the encoding and decoding of quantum data, and how error syndromes are to be measured.</span></span>


### <a name="fnx--recoveryfn"></a><span data-ttu-id="3b06f-109">fnX: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="3b06f-109">fnX : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="3b06f-110">Oggetto `RecoveryFn` che esegue il mapping di ogni sindrome di $X $ Error alle `Pauli[]` operazioni che correggono l'errore rilevato.</span><span class="sxs-lookup"><span data-stu-id="3b06f-110">A `RecoveryFn` that maps each $X$ error syndrome to the `Pauli[]` operations that correct the detected error.</span></span>


### <a name="fnz--recoveryfn"></a><span data-ttu-id="3b06f-111">fnZ: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="3b06f-111">fnZ : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="3b06f-112">Oggetto `RecoveryFn` che esegue il mapping di ogni sindrome di $Z $ Error alle `Pauli[]` operazioni che correggono l'errore rilevato.</span><span class="sxs-lookup"><span data-stu-id="3b06f-112">A `RecoveryFn` that maps each $Z$ error syndrome to the `Pauli[]` operations that correct the detected error.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="3b06f-113">logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="3b06f-113">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="3b06f-114">Matrice di qubits in cui è definito il codice di stabilizzazione.</span><span class="sxs-lookup"><span data-stu-id="3b06f-114">An array of qubits where the stabilizer code is defined.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3b06f-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3b06f-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="3b06f-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b06f-116">See Also</span></span>

- [<span data-ttu-id="3b06f-117">Microsoft. Quantum. ErrorCorrection. CSS</span><span class="sxs-lookup"><span data-stu-id="3b06f-117">Microsoft.Quantum.ErrorCorrection.CSS</span></span>](xref:Microsoft.Quantum.ErrorCorrection.CSS)
- [<span data-ttu-id="3b06f-118">Microsoft. Quantum. ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="3b06f-118">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
- [<span data-ttu-id="3b06f-119">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="3b06f-119">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
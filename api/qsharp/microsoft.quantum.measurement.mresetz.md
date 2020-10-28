---
uid: Microsoft.Quantum.Measurement.MResetZ
title: Operazione MResetZ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 9f084b03504deea9fcf25e4c797c4bde3c97a995
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711052"
---
# <a name="mresetz-operation"></a><span data-ttu-id="67a5e-102">Operazione MResetZ</span><span class="sxs-lookup"><span data-stu-id="67a5e-102">MResetZ operation</span></span>

<span data-ttu-id="67a5e-103">Spazio dei nomi: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="67a5e-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="67a5e-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="67a5e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="67a5e-105">Misura un singolo qubit in base alla Z e lo reimposta su uno stato iniziale fisso dopo la misurazione.</span><span class="sxs-lookup"><span data-stu-id="67a5e-105">Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetZ (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="67a5e-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="67a5e-106">Description</span></span>

<span data-ttu-id="67a5e-107">Esegue una misurazione a qubit singolo in $Z $-base e garantisce che qubit venga restituito a $ \ket {0} $ dopo la misurazione.</span><span class="sxs-lookup"><span data-stu-id="67a5e-107">Performs a single-qubit measurement in the $Z$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="67a5e-108">Input</span><span class="sxs-lookup"><span data-stu-id="67a5e-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="67a5e-109">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="67a5e-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="67a5e-110">Singolo qubit da misurare.</span><span class="sxs-lookup"><span data-stu-id="67a5e-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="67a5e-111">Output: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="67a5e-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="67a5e-112">Risultato della misurazione `target` in Pauli $Z $ base.</span><span class="sxs-lookup"><span data-stu-id="67a5e-112">The result of measuring `target` in the Pauli $Z$ basis.</span></span>
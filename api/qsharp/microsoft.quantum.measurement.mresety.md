---
uid: Microsoft.Quantum.Measurement.MResetY
title: Operazione MResetY
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 48aba7317d0e48d089ec6c4814efdee51bb8e2ed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725011"
---
# <a name="mresety-operation"></a><span data-ttu-id="dd7a3-102">Operazione MResetY</span><span class="sxs-lookup"><span data-stu-id="dd7a3-102">MResetY operation</span></span>

<span data-ttu-id="dd7a3-103">Spazio dei nomi: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="dd7a3-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="dd7a3-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dd7a3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dd7a3-105">Misura un singolo qubit in base Y e lo reimposta su uno stato iniziale fisso dopo la misurazione.</span><span class="sxs-lookup"><span data-stu-id="dd7a3-105">Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetY (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="dd7a3-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd7a3-106">Description</span></span>

<span data-ttu-id="dd7a3-107">Esegue una misurazione a qubit singolo in $Y $-base e garantisce che qubit venga restituito a $ \ket {0} $ dopo la misurazione.</span><span class="sxs-lookup"><span data-stu-id="dd7a3-107">Performs a single-qubit measurement in the $Y$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="dd7a3-108">Input</span><span class="sxs-lookup"><span data-stu-id="dd7a3-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="dd7a3-109">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="dd7a3-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="dd7a3-110">Singolo qubit da misurare.</span><span class="sxs-lookup"><span data-stu-id="dd7a3-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="dd7a3-111">Output: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="dd7a3-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="dd7a3-112">Risultato della misurazione `target` in Pauli $Y $ base.</span><span class="sxs-lookup"><span data-stu-id="dd7a3-112">The result of measuring `target` in the Pauli $Y$ basis.</span></span>
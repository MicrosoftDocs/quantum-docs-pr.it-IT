---
uid: Microsoft.Quantum.Measurement.MResetY
title: Operazione MResetY
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 2e41e76a46b68178a8a22b39131d6ca2a8c50b64
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854645"
---
# <a name="mresety-operation"></a><span data-ttu-id="9e18f-102">Operazione MResetY</span><span class="sxs-lookup"><span data-stu-id="9e18f-102">MResetY operation</span></span>

<span data-ttu-id="9e18f-103">Spazio dei nomi: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="9e18f-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="9e18f-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="9e18f-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="9e18f-105">Misura un singolo qubit in base Y e lo reimposta su uno stato iniziale fisso dopo la misurazione.</span><span class="sxs-lookup"><span data-stu-id="9e18f-105">Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetY (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="9e18f-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9e18f-106">Description</span></span>

<span data-ttu-id="9e18f-107">Esegue una misurazione a qubit singolo in $Y $-base e garantisce che qubit venga restituito a $ \ket {0} $ dopo la misurazione.</span><span class="sxs-lookup"><span data-stu-id="9e18f-107">Performs a single-qubit measurement in the $Y$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="9e18f-108">Input</span><span class="sxs-lookup"><span data-stu-id="9e18f-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="9e18f-109">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9e18f-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9e18f-110">Singolo qubit da misurare.</span><span class="sxs-lookup"><span data-stu-id="9e18f-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="9e18f-111">Output: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="9e18f-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="9e18f-112">Risultato della misurazione `target` in Pauli $Y $ base.</span><span class="sxs-lookup"><span data-stu-id="9e18f-112">The result of measuring `target` in the Pauli $Y$ basis.</span></span>
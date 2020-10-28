---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: Tipo definito dall'utente SyndromeMeasOp
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 1314e16d26c7310bab21caa91cb398d4b6f09b29
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712116"
---
# <a name="syndromemeasop-user-defined-type"></a><span data-ttu-id="245a4-102">Tipo definito dall'utente SyndromeMeasOp</span><span class="sxs-lookup"><span data-stu-id="245a4-102">SyndromeMeasOp user defined type</span></span>

<span data-ttu-id="245a4-103">Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="245a4-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="245a4-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="245a4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="245a4-105">Rappresenta un'operazione utilizzata per misurare la sindrome di un blocco di codice di correzione degli errori.</span><span class="sxs-lookup"><span data-stu-id="245a4-105">Represents an operation that is used to measure the syndrome of an error-correcting code block.</span></span>

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="remarks"></a><span data-ttu-id="245a4-106">Commenti</span><span class="sxs-lookup"><span data-stu-id="245a4-106">Remarks</span></span>

<span data-ttu-id="245a4-107">La firma `(LogicalRegister => Syndrome)` rappresenta un'operazione che agisce congiuntamente sul qubits in `LogicalRegister` e alcuni qubits ausiliari seguito da una misura del qubits ausiliario per estrarre un `Syndrome` valore che rappresenta l'oggetto `Result[]` di queste misurazioni.</span><span class="sxs-lookup"><span data-stu-id="245a4-107">The signature `(LogicalRegister => Syndrome)` represents an operation that acts jointly on the qubits in `LogicalRegister` and some auxiliary qubits followed by a measurements of the auxiliary qubits to extract a `Syndrome` value representing the `Result[]` of these measurements.</span></span>

## <a name="see-also"></a><span data-ttu-id="245a4-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="245a4-108">See Also</span></span>

- [<span data-ttu-id="245a4-109">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="245a4-109">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="245a4-110">Microsoft. Quantum. ErrorCorrection. syndrome</span><span class="sxs-lookup"><span data-stu-id="245a4-110">Microsoft.Quantum.ErrorCorrection.Syndrome</span></span>](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)
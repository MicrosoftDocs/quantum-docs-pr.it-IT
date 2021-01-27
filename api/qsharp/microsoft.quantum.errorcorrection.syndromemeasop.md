---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: Tipo definito dall'utente SyndromeMeasOp
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 36336f9e47e5f360cf5e19ffb6e15b4af88b2580
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850047"
---
# <a name="syndromemeasop-user-defined-type"></a><span data-ttu-id="9da0b-102">Tipo definito dall'utente SyndromeMeasOp</span><span class="sxs-lookup"><span data-stu-id="9da0b-102">SyndromeMeasOp user defined type</span></span>

<span data-ttu-id="9da0b-103">Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="9da0b-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="9da0b-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9da0b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9da0b-105">Rappresenta un'operazione utilizzata per misurare la sindrome di un blocco di codice di correzione degli errori.</span><span class="sxs-lookup"><span data-stu-id="9da0b-105">Represents an operation that is used to measure the syndrome of an error-correcting code block.</span></span>

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="example"></a><span data-ttu-id="9da0b-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="9da0b-106">Example</span></span>

<span data-ttu-id="9da0b-107">Le sindromi delle misure per il codice di Flip bit $S = \langle ZZI, IZZ \rangle $ using Scratch qubits in un modo non a tolleranza di errore:</span><span class="sxs-lookup"><span data-stu-id="9da0b-107">Measure syndromes for the bit-flip code $S = \langle ZZI, IZZ \rangle$ using scratch qubits in a non–fault tolerant manner:</span></span>

```qsharp
    let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
            [PauliZ, PauliZ, PauliI],
            [PauliI, PauliZ, PauliZ]
        ], _, MeasureWithScratch));
```

## <a name="remarks"></a><span data-ttu-id="9da0b-108">Commenti</span><span class="sxs-lookup"><span data-stu-id="9da0b-108">Remarks</span></span>

<span data-ttu-id="9da0b-109">La firma `(LogicalRegister => Syndrome)` rappresenta un'operazione che agisce congiuntamente sul qubits in `LogicalRegister` e alcuni qubits ausiliari seguito da una misura del qubits ausiliario per estrarre un `Syndrome` valore che rappresenta l'oggetto `Result[]` di queste misurazioni.</span><span class="sxs-lookup"><span data-stu-id="9da0b-109">The signature `(LogicalRegister => Syndrome)` represents an operation that acts jointly on the qubits in `LogicalRegister` and some auxiliary qubits followed by a measurements of the auxiliary qubits to extract a `Syndrome` value representing the `Result[]` of these measurements.</span></span>

## <a name="see-also"></a><span data-ttu-id="9da0b-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9da0b-110">See Also</span></span>

- [<span data-ttu-id="9da0b-111">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="9da0b-111">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="9da0b-112">Microsoft. Quantum. ErrorCorrection. syndrome</span><span class="sxs-lookup"><span data-stu-id="9da0b-112">Microsoft.Quantum.ErrorCorrection.Syndrome</span></span>](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)
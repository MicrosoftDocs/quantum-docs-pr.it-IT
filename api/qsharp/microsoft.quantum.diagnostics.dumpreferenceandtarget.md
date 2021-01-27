---
uid: Microsoft.Quantum.Diagnostics.DumpReferenceAndTarget
title: Operazione DumpReferenceAndTarget
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpReferenceAndTarget
qsharp.summary: Uses DumpRegister to provide diagnostics on the state of a reference and target register. Written as separate operation to allow overriding and interpreting as separate registers, rather than as a single combined register.
ms.openlocfilehash: 7f66af8a1f6f9ab83740fbf5dcfaf55776d74eb9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853402"
---
# <a name="dumpreferenceandtarget-operation"></a><span data-ttu-id="776ae-102">Operazione DumpReferenceAndTarget</span><span class="sxs-lookup"><span data-stu-id="776ae-102">DumpReferenceAndTarget operation</span></span>

<span data-ttu-id="776ae-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="776ae-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="776ae-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="776ae-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="776ae-105">USA DumpRegister per fornire la diagnostica sullo stato di un riferimento e di un registro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="776ae-105">Uses DumpRegister to provide diagnostics on the state of a reference and target register.</span></span> <span data-ttu-id="776ae-106">Scritto come operazione separata per consentire l'override e l'interpretazione come registri distinti, anziché come singolo registro combinato.</span><span class="sxs-lookup"><span data-stu-id="776ae-106">Written as separate operation to allow overriding and interpreting as separate registers, rather than as a single combined register.</span></span>

```qsharp
operation DumpReferenceAndTarget (reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="776ae-107">Input</span><span class="sxs-lookup"><span data-stu-id="776ae-107">Input</span></span>

### <a name="reference--qubit"></a><span data-ttu-id="776ae-108">riferimento: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="776ae-108">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="776ae-109">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="776ae-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="776ae-110">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="776ae-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


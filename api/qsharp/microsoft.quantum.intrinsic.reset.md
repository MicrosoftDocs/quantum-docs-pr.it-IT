---
uid: Microsoft.Quantum.Intrinsic.Reset
title: Operazione di reimpostazione
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Reset
qsharp.summary: Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.
ms.openlocfilehash: b4275796b966bfe7f55271f4e92866410a14e830
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818636"
---
# <a name="reset-operation"></a><span data-ttu-id="1017b-102">Operazione di reimpostazione</span><span class="sxs-lookup"><span data-stu-id="1017b-102">Reset operation</span></span>

<span data-ttu-id="1017b-103">Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="1017b-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="1017b-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="1017b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="1017b-105">Dato un singolo qubit, lo misura e garantisce che si trovi nello stato di ⟩ | 0 in modo che possa essere rilasciato in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="1017b-105">Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.</span></span>

```qsharp
operation Reset (target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="1017b-106">Input</span><span class="sxs-lookup"><span data-stu-id="1017b-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="1017b-107">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1017b-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1017b-108">Qubit di cui è necessario reimpostare lo stato su $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="1017b-108">The qubit whose state is to be reset to $\ket{0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1017b-109">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1017b-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


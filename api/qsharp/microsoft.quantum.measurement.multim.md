---
uid: Microsoft.Quantum.Measurement.MultiM
title: Operazione multifunzione
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: c39601f3e8b272b9341f1789b4c8e7230cb4182c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226996"
---
# <a name="multim-operation"></a><span data-ttu-id="f919c-102">Operazione multifunzione</span><span class="sxs-lookup"><span data-stu-id="f919c-102">MultiM operation</span></span>

<span data-ttu-id="f919c-103">Spazio dei nomi: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="f919c-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="f919c-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f919c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f919c-105">Misura ogni qubit in una matrice specificata in base allo standard.</span><span class="sxs-lookup"><span data-stu-id="f919c-105">Measures each qubit in a given array in the standard basis.</span></span>

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="f919c-106">Input</span><span class="sxs-lookup"><span data-stu-id="f919c-106">Input</span></span>

### <a name="targets--qubit"></a><span data-ttu-id="f919c-107">destinazioni: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f919c-107">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f919c-108">Matrice di qubits da misurare.</span><span class="sxs-lookup"><span data-stu-id="f919c-108">An array of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="f919c-109">Output: __non <Result> valido__[]</span><span class="sxs-lookup"><span data-stu-id="f919c-109">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="f919c-110">Matrice di risultati della misurazione.</span><span class="sxs-lookup"><span data-stu-id="f919c-110">An array of measurement results.</span></span>
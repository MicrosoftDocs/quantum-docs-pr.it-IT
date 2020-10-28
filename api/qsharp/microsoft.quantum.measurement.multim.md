---
uid: Microsoft.Quantum.Measurement.MultiM
title: Operazione multifunzione
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: 36de9dbdfc96f6e1698ee4537405f7cb74e44262
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711038"
---
# <a name="multim-operation"></a><span data-ttu-id="e5f87-102">Operazione multifunzione</span><span class="sxs-lookup"><span data-stu-id="e5f87-102">MultiM operation</span></span>

<span data-ttu-id="e5f87-103">Spazio dei nomi: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="e5f87-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="e5f87-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e5f87-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e5f87-105">Misura ogni qubit in una matrice specificata in base allo standard.</span><span class="sxs-lookup"><span data-stu-id="e5f87-105">Measures each qubit in a given array in the standard basis.</span></span>

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="e5f87-106">Input</span><span class="sxs-lookup"><span data-stu-id="e5f87-106">Input</span></span>

### <a name="targets--qubit"></a><span data-ttu-id="e5f87-107">destinazioni: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e5f87-107">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e5f87-108">Matrice di qubits da misurare.</span><span class="sxs-lookup"><span data-stu-id="e5f87-108">An array of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="e5f87-109">Output: __non <Result> valido__ []</span><span class="sxs-lookup"><span data-stu-id="e5f87-109">Output : __invalid<Result>__ []</span></span>

<span data-ttu-id="e5f87-110">Matrice di risultati della misurazione.</span><span class="sxs-lookup"><span data-stu-id="e5f87-110">An array of measurement results.</span></span>
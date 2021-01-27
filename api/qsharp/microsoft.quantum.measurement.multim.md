---
uid: Microsoft.Quantum.Measurement.MultiM
title: Operazione multifunzione
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: b7f4083bde84c204611ea33746ae351a3e27b946
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857006"
---
# <a name="multim-operation"></a><span data-ttu-id="a9e53-102">Operazione multifunzione</span><span class="sxs-lookup"><span data-stu-id="a9e53-102">MultiM operation</span></span>

<span data-ttu-id="a9e53-103">Spazio dei nomi: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="a9e53-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="a9e53-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a9e53-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a9e53-105">Misura ogni qubit in una matrice specificata in base allo standard.</span><span class="sxs-lookup"><span data-stu-id="a9e53-105">Measures each qubit in a given array in the standard basis.</span></span>

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="a9e53-106">Input</span><span class="sxs-lookup"><span data-stu-id="a9e53-106">Input</span></span>

### <a name="targets--qubit"></a><span data-ttu-id="a9e53-107">destinazioni: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a9e53-107">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a9e53-108">Matrice di qubits da misurare.</span><span class="sxs-lookup"><span data-stu-id="a9e53-108">An array of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="a9e53-109">Output: __non <Result> valido__[]</span><span class="sxs-lookup"><span data-stu-id="a9e53-109">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="a9e53-110">Matrice di risultati della misurazione.</span><span class="sxs-lookup"><span data-stu-id="a9e53-110">An array of measurement results.</span></span>
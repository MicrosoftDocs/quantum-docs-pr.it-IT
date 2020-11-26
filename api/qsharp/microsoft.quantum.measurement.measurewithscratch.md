---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: Operazione MeasureWithScratch
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: c42316a811e0e4a81c7f244c093a2be88fe5c733
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227064"
---
# <a name="measurewithscratch-operation"></a><span data-ttu-id="2ba55-102">Operazione MeasureWithScratch</span><span class="sxs-lookup"><span data-stu-id="2ba55-102">MeasureWithScratch operation</span></span>

<span data-ttu-id="2ba55-103">Spazio dei nomi: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="2ba55-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="2ba55-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2ba55-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2ba55-105">Misura l'operatore Pauli specificato usando un qubit di Scratch esplicito per eseguire la misurazione.</span><span class="sxs-lookup"><span data-stu-id="2ba55-105">Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.</span></span>

```qsharp
operation MeasureWithScratch (pauli : Pauli[], target : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="2ba55-106">Input</span><span class="sxs-lookup"><span data-stu-id="2ba55-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="2ba55-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="2ba55-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="2ba55-108">Un operatore Pauli multiqubit specificato come una matrice di operatori Pauli a qubit singolo.</span><span class="sxs-lookup"><span data-stu-id="2ba55-108">A multi-qubit Pauli operator specified as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="2ba55-109">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2ba55-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2ba55-110">Registro qubit da misurare.</span><span class="sxs-lookup"><span data-stu-id="2ba55-110">Qubit register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="2ba55-111">Output: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="2ba55-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="2ba55-112">Risultato della misurazione dell'operatore Pauli specificato nel `target` registro.</span><span class="sxs-lookup"><span data-stu-id="2ba55-112">The result of measuring the given Pauli operator on the `target` register.</span></span>
---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: Operazione MeasureWithScratch
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: 1ee25dbccd5bddde406cf8ed84dff77d96d7804e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720327"
---
# <a name="measurewithscratch-operation"></a><span data-ttu-id="066e2-102">Operazione MeasureWithScratch</span><span class="sxs-lookup"><span data-stu-id="066e2-102">MeasureWithScratch operation</span></span>

<span data-ttu-id="066e2-103">Spazio dei nomi: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="066e2-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="066e2-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="066e2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="066e2-105">Misura l'operatore Pauli specificato usando un qubit di Scratch esplicito per eseguire la misurazione.</span><span class="sxs-lookup"><span data-stu-id="066e2-105">Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.</span></span>

```qsharp
operation MeasureWithScratch (pauli : Pauli[], target : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="066e2-106">Input</span><span class="sxs-lookup"><span data-stu-id="066e2-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="066e2-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="066e2-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="066e2-108">Un operatore Pauli multiqubit specificato come una matrice di operatori Pauli a qubit singolo.</span><span class="sxs-lookup"><span data-stu-id="066e2-108">A multi-qubit Pauli operator specified as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="066e2-109">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="066e2-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="066e2-110">Registro qubit da misurare.</span><span class="sxs-lookup"><span data-stu-id="066e2-110">Qubit register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="066e2-111">Output: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="066e2-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="066e2-112">Risultato della misurazione dell'operatore Pauli specificato nel `target` registro.</span><span class="sxs-lookup"><span data-stu-id="066e2-112">The result of measuring the given Pauli operator on the `target` register.</span></span>
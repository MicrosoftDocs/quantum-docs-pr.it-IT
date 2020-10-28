---
uid: Microsoft.Quantum.Chemistry.JordanWigner.QubitizationOracle
title: QubitizationOracle (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: QubitizationOracle
qsharp.summary: Returns Qubitization operation and the parameters necessary to run it.
ms.openlocfilehash: 326bebfc1cfd839082732898167c20ecf105a266
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713810"
---
# <a name="qubitizationoracle-function"></a><span data-ttu-id="fe670-102">QubitizationOracle (funzione)</span><span class="sxs-lookup"><span data-stu-id="fe670-102">QubitizationOracle function</span></span>

<span data-ttu-id="fe670-103">Spazio dei nomi: [Microsoft. Quantum. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="fe670-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="fe670-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fe670-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fe670-105">Restituisce l'operazione Qubitization e i parametri necessari per eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="fe670-105">Returns Qubitization operation and the parameters necessary to run it.</span></span>

```qsharp
function QubitizationOracle (qSharpData : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData) : (Int, (Double, (Qubit[] => Unit is Adj + Ctl)))
```


## <a name="input"></a><span data-ttu-id="fe670-106">Input</span><span class="sxs-lookup"><span data-stu-id="fe670-106">Input</span></span>

### <a name="qsharpdata--jordanwignerencodingdata"></a><span data-ttu-id="fe670-107">qSharpData: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span><span class="sxs-lookup"><span data-stu-id="fe670-107">qSharpData : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span></span>

<span data-ttu-id="fe670-108">Hamiltoniana descritta dal `JordanWignerEncodingData` formato.</span><span class="sxs-lookup"><span data-stu-id="fe670-108">Hamiltonian described by `JordanWignerEncodingData` format.</span></span>



## <a name="output--intdoublequbit--unit-adj--ctl"></a><span data-ttu-id="fe670-109">Output: ([int](xref:microsoft.quantum.lang-ref.int), ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL))</span><span class="sxs-lookup"><span data-stu-id="fe670-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl))</span></span>

<span data-ttu-id="fe670-110">Tupla in cui: `Int` è il numero di qubits allocato, `Double` è l'unica regola dei coefficienti Hamiltoniana e l'operazione è il percorso quantistico creato da Qubitization.</span><span class="sxs-lookup"><span data-stu-id="fe670-110">A tuple where: `Int` is the number of qubits allocated, `Double` is the one-norm of Hamiltonian coefficients, and the operation is the Quantum walk created by Qubitization.</span></span>
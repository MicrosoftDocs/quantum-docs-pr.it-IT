---
uid: Microsoft.Quantum.Chemistry.JordanWigner.QubitizationOracle
title: QubitizationOracle (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: QubitizationOracle
qsharp.summary: Returns Qubitization operation and the parameters necessary to run it.
ms.openlocfilehash: cf6fe04b3f629c4ca4a7c27d8519a4cb42d07630
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835848"
---
# <a name="qubitizationoracle-function"></a><span data-ttu-id="4b815-102">QubitizationOracle (funzione)</span><span class="sxs-lookup"><span data-stu-id="4b815-102">QubitizationOracle function</span></span>

<span data-ttu-id="4b815-103">Spazio dei nomi: [Microsoft. Quantum. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="4b815-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="4b815-104">Pacchetto: [Microsoft. Quantum. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="4b815-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="4b815-105">Restituisce l'operazione Qubitization e i parametri necessari per eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="4b815-105">Returns Qubitization operation and the parameters necessary to run it.</span></span>

```qsharp
function QubitizationOracle (qSharpData : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData) : (Int, (Double, (Qubit[] => Unit is Adj + Ctl)))
```


## <a name="input"></a><span data-ttu-id="4b815-106">Input</span><span class="sxs-lookup"><span data-stu-id="4b815-106">Input</span></span>

### <a name="qsharpdata--jordanwignerencodingdata"></a><span data-ttu-id="4b815-107">qSharpData: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span><span class="sxs-lookup"><span data-stu-id="4b815-107">qSharpData : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span></span>

<span data-ttu-id="4b815-108">Hamiltoniana descritta dal `JordanWignerEncodingData` formato.</span><span class="sxs-lookup"><span data-stu-id="4b815-108">Hamiltonian described by `JordanWignerEncodingData` format.</span></span>



## <a name="output--intdoublequbit--unit--is-adj--ctl"></a><span data-ttu-id="4b815-109">Output: ([int](xref:microsoft.quantum.lang-ref.int), ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unit](xref:microsoft.quantum.lang-ref.unit)  is ADJ + CTL))</span><span class="sxs-lookup"><span data-stu-id="4b815-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl))</span></span>

<span data-ttu-id="4b815-110">Tupla in cui: `Int` è il numero di qubits allocato, `Double` è l'unica regola dei coefficienti Hamiltoniana e l'operazione è il percorso quantistico creato da Qubitization.</span><span class="sxs-lookup"><span data-stu-id="4b815-110">A tuple where: `Int` is the number of qubits allocated, `Double` is the one-norm of Hamiltonian coefficients, and the operation is the Quantum walk created by Qubitization.</span></span>
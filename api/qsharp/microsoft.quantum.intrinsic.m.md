---
uid: Microsoft.Quantum.Intrinsic.M
title: Operazione M
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: M
qsharp.summary: >-
  Performs a measurement of a single qubit in the Pauli $Z$ basis.

  The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. \end{align}
ms.openlocfilehash: 0037d7f5ad060857c6ca2c863b1d24aca3e338cf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818881"
---
# <a name="m-operation"></a><span data-ttu-id="4d929-102">Operazione M</span><span class="sxs-lookup"><span data-stu-id="4d929-102">M operation</span></span>

<span data-ttu-id="4d929-103">Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="4d929-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="4d929-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="4d929-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="4d929-105">Esegue una misurazione di un singolo qubit in Pauli $Z $ base.</span><span class="sxs-lookup"><span data-stu-id="4d929-105">Performs a measurement of a single qubit in the Pauli $Z$ basis.</span></span>

<span data-ttu-id="4d929-106">Il risultato dell'output viene fornito da Distribution \begin{align} \Pr (\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}.</span><span class="sxs-lookup"><span data-stu-id="4d929-106">The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}.</span></span>
<span data-ttu-id="4d929-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="4d929-107">\end{align}</span></span>

```qsharp
operation M (qubit : Qubit) : Result
```


## <a name="input"></a><span data-ttu-id="4d929-108">Input</span><span class="sxs-lookup"><span data-stu-id="4d929-108">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="4d929-109">Qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4d929-109">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4d929-110">Qubit da misurare.</span><span class="sxs-lookup"><span data-stu-id="4d929-110">Qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="4d929-111">Output: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="4d929-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="4d929-112">`Zero` Se viene osservato il autovalore $ + $1 e `One` se viene osservato il autovalore $-$1.</span><span class="sxs-lookup"><span data-stu-id="4d929-112">`Zero` if the $+1$ eigenvalue is observed, and `One` if the $-1$ eigenvalue is observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="4d929-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="4d929-113">Remarks</span></span>

<span data-ttu-id="4d929-114">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="4d929-114">Equivalent to:</span></span>

```qsharp
Measure([PauliZ], [qubit]);
```
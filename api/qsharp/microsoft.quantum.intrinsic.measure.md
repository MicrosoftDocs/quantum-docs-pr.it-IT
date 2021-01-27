---
uid: Microsoft.Quantum.Intrinsic.Measure
title: Operazione di misurazione
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Measure
qsharp.summary: >-
  Performs a joint measurement of one or more qubits in the specified Pauli bases.

  The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$. That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.
ms.openlocfilehash: bf0a606b1bfc8c4762245422450ec26907ec1946
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818780"
---
# <a name="measure-operation"></a><span data-ttu-id="bca84-102">Operazione di misurazione</span><span class="sxs-lookup"><span data-stu-id="bca84-102">Measure operation</span></span>

<span data-ttu-id="bca84-103">Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="bca84-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="bca84-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="bca84-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="bca84-105">Esegue una misurazione congiunta di uno o più qubits nelle basi di Pauli specificate.</span><span class="sxs-lookup"><span data-stu-id="bca84-105">Performs a joint measurement of one or more qubits in the specified Pauli bases.</span></span>

<span data-ttu-id="bca84-106">Il risultato di output viene fornito dalla distribuzione: \begin{align} \Pr (\texttt{Zero} | \ket{\psi}) = \frac12 \braket{\psi \MID | \left (\boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_ {N-1} \right) \MID | \psi}, \end{align} dove $P _i $ è l'elemento $i $ th di `bases` e dove $N = \texttt{Length} (\texttt{Bases}) $.</span><span class="sxs-lookup"><span data-stu-id="bca84-106">The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$.</span></span>
<span data-ttu-id="bca84-107">Ovvero, la misurazione restituisce un `Result` $d $, in modo che il valore di autovalore dell'effetto di misurazione osservato sia $ (-1) ^ d $.</span><span class="sxs-lookup"><span data-stu-id="bca84-107">That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.</span></span>

```qsharp
operation Measure (bases : Pauli[], qubits : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="bca84-108">Input</span><span class="sxs-lookup"><span data-stu-id="bca84-108">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="bca84-109">basi: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="bca84-109">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="bca84-110">Matrice di valori Pauli Single-qubit che indicano i fattori del prodotto tensore in ogni qubit.</span><span class="sxs-lookup"><span data-stu-id="bca84-110">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="bca84-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="bca84-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="bca84-112">Registro di qubits da misurare.</span><span class="sxs-lookup"><span data-stu-id="bca84-112">Register of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="bca84-113">Output: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="bca84-113">Output : __invalid<Result>__</span></span>

<span data-ttu-id="bca84-114">`Zero` Se viene osservato il autovalore $ + $1 e `One` se viene osservato il autovalore $-$1.</span><span class="sxs-lookup"><span data-stu-id="bca84-114">`Zero` if the $+1$ eigenvalue is observed, and `One` if the $-1$ eigenvalue is observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="bca84-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="bca84-115">Remarks</span></span>

<span data-ttu-id="bca84-116">Se la matrice di base e la matrice qubit hanno lunghezze diverse, l'operazione avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="bca84-116">If the basis array and qubit array are different lengths, then the operation will fail.</span></span>
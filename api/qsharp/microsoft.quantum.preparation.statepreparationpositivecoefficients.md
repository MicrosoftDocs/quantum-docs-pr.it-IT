---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: StatePreparationPositiveCoefficients (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationPositiveCoefficients
qsharp.summary: >-
  > [!WARNING]

  > StatePreparationPositiveCoefficients has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> instead.


  Returns an operation that prepares the given quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}. \end{align} $$
ms.openlocfilehash: 8f1fd7d77531996faf566adb78f452929d6cbd50
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193251"
---
# <a name="statepreparationpositivecoefficients-function"></a><span data-ttu-id="7d17a-102">StatePreparationPositiveCoefficients (funzione)</span><span class="sxs-lookup"><span data-stu-id="7d17a-102">StatePreparationPositiveCoefficients function</span></span>

<span data-ttu-id="7d17a-103">Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="7d17a-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="7d17a-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7d17a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="7d17a-105">StatePreparationPositiveCoefficients è stato deprecato.</span><span class="sxs-lookup"><span data-stu-id="7d17a-105">StatePreparationPositiveCoefficients has been deprecated.</span></span> <span data-ttu-id="7d17a-106">Usare invece <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD>.</span><span class="sxs-lookup"><span data-stu-id="7d17a-106">Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> instead.</span></span>

<span data-ttu-id="7d17a-107">Restituisce un'operazione che prepara lo stato del quantum specificato.</span><span class="sxs-lookup"><span data-stu-id="7d17a-107">Returns an operation that prepares the given quantum state.</span></span>

<span data-ttu-id="7d17a-108">L'operazione restituita $U $ prepara uno stato quantico arbitrario $ \ket{\psi} $ con coefficienti positivi $ \ alpha_j \ge $0 dallo stato di base di calcolo $n $-qubit $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="7d17a-108">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="7d17a-109">L'azione di U in un registro appena allocato viene fornita da $ $ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} \ alpha_j \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | \ alpha_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="7d17a-109">The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}.</span></span>
<span data-ttu-id="7d17a-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="7d17a-110">\end{align} $$</span></span>

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="7d17a-111">Input</span><span class="sxs-lookup"><span data-stu-id="7d17a-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="7d17a-112">coefficienti: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="7d17a-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="7d17a-113">Matrice di un massimo di $2 ^ n $ coefficienti $ \ alpha_j $.</span><span class="sxs-lookup"><span data-stu-id="7d17a-113">Array of up to $2^n$ coefficients $\alpha_j$.</span></span> <span data-ttu-id="7d17a-114">Il coefficiente $j $ TH indicizza lo stato del numero $ \ket{j} $ codificato in formato little-endian.</span><span class="sxs-lookup"><span data-stu-id="7d17a-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="7d17a-115">Output: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) l' => [unità](xref:microsoft.quantum.lang-ref.unit) LittleEndian è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="7d17a-115">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="7d17a-116">Operazione unitaria di preparazione dello stato $U $.</span><span class="sxs-lookup"><span data-stu-id="7d17a-116">A state-preparation unitary operation $U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="7d17a-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="7d17a-117">Remarks</span></span>

<span data-ttu-id="7d17a-118">I coefficienti di input negativi $ \ alpha_j < $0 verranno trattati come se fossero positivi con il valore $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="7d17a-118">Negative input coefficients $\alpha_j < 0$ will be treated as though positive with value $|\alpha_j|$.</span></span> <span data-ttu-id="7d17a-119">`coefficients` verrà riempito con gli elementi $ \ alpha_j = $0,0 se sono specificati meno di $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="7d17a-119">`coefficients` will be padded with elements $\alpha_j = 0.0$ if fewer than $2^n$ are specified.</span></span>
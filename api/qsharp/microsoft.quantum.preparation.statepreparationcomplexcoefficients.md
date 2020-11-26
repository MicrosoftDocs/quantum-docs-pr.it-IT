---
uid: Microsoft.Quantum.Preparation.StatePreparationComplexCoefficients
title: StatePreparationComplexCoefficients (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationComplexCoefficients
qsharp.summary: >-
  > [!WARNING]

  > StatePreparationComplexCoefficients has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.


  Returns an operation that prepares a specific quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}. \end{align} $$
ms.openlocfilehash: 1d0efa7b83d2e8e75c4b293866f3929f357ec44b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210370"
---
# <a name="statepreparationcomplexcoefficients-function"></a><span data-ttu-id="427fd-102">StatePreparationComplexCoefficients (funzione)</span><span class="sxs-lookup"><span data-stu-id="427fd-102">StatePreparationComplexCoefficients function</span></span>

<span data-ttu-id="427fd-103">Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="427fd-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="427fd-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="427fd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="427fd-105">StatePreparationComplexCoefficients è stato deprecato.</span><span class="sxs-lookup"><span data-stu-id="427fd-105">StatePreparationComplexCoefficients has been deprecated.</span></span> <span data-ttu-id="427fd-106">Usare invece <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP>.</span><span class="sxs-lookup"><span data-stu-id="427fd-106">Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.</span></span>

<span data-ttu-id="427fd-107">Restituisce un'operazione che prepara uno stato quantico specifico.</span><span class="sxs-lookup"><span data-stu-id="427fd-107">Returns an operation that prepares a specific quantum state.</span></span>

<span data-ttu-id="427fd-108">L'operazione restituita $U $ prepara uno stato quantico arbitrario $ \ket{\psi} $ con coefficienti complessi $r _j e ^ {i t_j} $ dallo stato di base di calcolo $n $-qubit $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="427fd-108">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="427fd-109">L'azione di U in un registro appena allocato viene fornita da $ $ \begin{align} U\ket {0... 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="427fd-109">The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}.</span></span>
<span data-ttu-id="427fd-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="427fd-110">\end{align} $$</span></span>

```qsharp
function StatePreparationComplexCoefficients (coefficients : Microsoft.Quantum.Math.ComplexPolar[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="427fd-111">Input</span><span class="sxs-lookup"><span data-stu-id="427fd-111">Input</span></span>

### <a name="coefficients--complexpolar"></a><span data-ttu-id="427fd-112">coefficienti: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="427fd-112">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="427fd-113">Matrice di un massimo di $2 ^ n $ coefficienti complessi, rappresentati dal valore assoluto e dalla fase $ (r_j, t_j) $.</span><span class="sxs-lookup"><span data-stu-id="427fd-113">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="427fd-114">Il coefficiente $j $ TH indicizza lo stato del numero $ \ket{j} $ codificato in formato little-endian.</span><span class="sxs-lookup"><span data-stu-id="427fd-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="427fd-115">Output: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) l' => [unità](xref:microsoft.quantum.lang-ref.unit) LittleEndian è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="427fd-115">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="427fd-116">Operazione unitaria di preparazione dello stato $U $.</span><span class="sxs-lookup"><span data-stu-id="427fd-116">A state-preparation unitary operation $U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="427fd-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="427fd-117">Remarks</span></span>

<span data-ttu-id="427fd-118">I coefficienti di input negativi $r _j < $0 verranno trattati come se fossero positivi con il valore $ | r_j | $.</span><span class="sxs-lookup"><span data-stu-id="427fd-118">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="427fd-119">`coefficients` verrà riempito con gli elementi $ (r_j, t_j) = (0,0, 0,0) $ se sono specificati meno di $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="427fd-119">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>
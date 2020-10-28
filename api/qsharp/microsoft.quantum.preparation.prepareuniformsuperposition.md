---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: Operazione PrepareUniformSuperposition
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: 8b57a7a02e9f704cf9677574824dfdc93fff25b0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709456"
---
# <a name="prepareuniformsuperposition-operation"></a><span data-ttu-id="f7abb-102">Operazione PrepareUniformSuperposition</span><span class="sxs-lookup"><span data-stu-id="f7abb-102">PrepareUniformSuperposition operation</span></span>

<span data-ttu-id="f7abb-103">Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="f7abb-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="f7abb-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f7abb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f7abb-105">Crea una superposizione uniforme sugli Stati che codificano da 0 a `nIndices - 1` .</span><span class="sxs-lookup"><span data-stu-id="f7abb-105">Creates a uniform superposition over states that encode 0 through `nIndices - 1`.</span></span>

<span data-ttu-id="f7abb-106">Questo Unity $U $ crea una superposizione uniforme su tutti gli Stati numerici $0 $ $M-$1, dato lo stato di input $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="f7abb-106">That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$.</span></span> <span data-ttu-id="f7abb-107">In altre parole, $ $ \begin{align} U\ket {0} = \frac {1} {\sqrt{m}}\ Sum_ {j = 0} ^ {M-1} \ket{j}.</span><span class="sxs-lookup"><span data-stu-id="f7abb-107">In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}.</span></span>
<span data-ttu-id="f7abb-108">\end{align} $ $.</span><span class="sxs-lookup"><span data-stu-id="f7abb-108">\end{align} $$.</span></span>

```qsharp
operation PrepareUniformSuperposition (nIndices : Int, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="f7abb-109">Input</span><span class="sxs-lookup"><span data-stu-id="f7abb-109">Input</span></span>

### <a name="nindices--int"></a><span data-ttu-id="f7abb-110">nIndices: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f7abb-110">nIndices : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f7abb-111">Il numero desiderato di stati $M $ nella superposizione uniforme.</span><span class="sxs-lookup"><span data-stu-id="f7abb-111">The desired number of states $M$ in the uniform superposition.</span></span>


### <a name="indexregister--littleendian"></a><span data-ttu-id="f7abb-112">indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f7abb-112">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f7abb-113">Registro qubit che archivia gli Stati dei numeri nel `LittleEndian` formato.</span><span class="sxs-lookup"><span data-stu-id="f7abb-113">The qubit register that stores the number states in `LittleEndian` format.</span></span>
<span data-ttu-id="f7abb-114">Il registro deve essere in grado di archiviare il numero $M-$1 e si presuppone che venga inizializzato nello stato $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="f7abb-114">This register must be able to store the number $M-1$, and is assumed to be initialized in the state $\ket{0\cdots 0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f7abb-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f7abb-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f7abb-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="f7abb-116">Remarks</span></span>

<span data-ttu-id="f7abb-117">L'operazione è adjointable, ma richiede che `indexRegister` si trovi in una superposizione uniforme rispetto ai primi `nIndices` Stati di base in questo caso.</span><span class="sxs-lookup"><span data-stu-id="f7abb-117">The operation is adjointable, but requires that `indexRegister` is in a uniform superposition over the first `nIndices` basis states in that case.</span></span>
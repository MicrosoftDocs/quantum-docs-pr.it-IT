---
uid: Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance
title: Operazione AssertQubitIsInStateWithinTolerance
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitIsInStateWithinTolerance
qsharp.summary: >-
  Asserts that a qubit in the expected state.

  `expected` represents a complex vector, $\ket{\psi} = \begin{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}$. The first element of the tuples representing each of $a$, $b$ is the real part of the complex number, while the second one is the imaginary part. The last argument defines the tolerance with which assertion is made.
ms.openlocfilehash: 5d34bdac53870326dacb5a11c27c857793c3f420
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712939"
---
# <a name="assertqubitisinstatewithintolerance-operation"></a><span data-ttu-id="33183-102">Operazione AssertQubitIsInStateWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="33183-102">AssertQubitIsInStateWithinTolerance operation</span></span>

<span data-ttu-id="33183-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="33183-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="33183-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="33183-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="33183-105">Asserisce che un qubit nello stato previsto.</span><span class="sxs-lookup"><span data-stu-id="33183-105">Asserts that a qubit in the expected state.</span></span>

<span data-ttu-id="33183-106">`expected` rappresenta un vettore complesso, $ \ket{\psi} = \begin{Bmatrix}a & b\end {Bmatrix} ^ {\mathrm{T}} $.</span><span class="sxs-lookup"><span data-stu-id="33183-106">`expected` represents a complex vector, $\ket{\psi} = \begin{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}$.</span></span>
<span data-ttu-id="33183-107">Il primo elemento delle tuple che rappresenta ogni $a $, $b $ è la parte reale del numero complesso, mentre la seconda è la parte immaginaria.</span><span class="sxs-lookup"><span data-stu-id="33183-107">The first element of the tuples representing each of $a$, $b$ is the real part of the complex number, while the second one is the imaginary part.</span></span>
<span data-ttu-id="33183-108">L'ultimo argomento definisce la tolleranza con cui viene eseguita l'asserzione.</span><span class="sxs-lookup"><span data-stu-id="33183-108">The last argument defines the tolerance with which assertion is made.</span></span>

```qsharp
operation AssertQubitIsInStateWithinTolerance (expected : (Microsoft.Quantum.Math.Complex, Microsoft.Quantum.Math.Complex), register : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="33183-109">Input</span><span class="sxs-lookup"><span data-stu-id="33183-109">Input</span></span>

### <a name="expected--complexcomplex"></a><span data-ttu-id="33183-110">previsto: ([complesso](xref:Microsoft.Quantum.Math.Complex),[complesso](xref:Microsoft.Quantum.Math.Complex))</span><span class="sxs-lookup"><span data-stu-id="33183-110">expected : ([Complex](xref:Microsoft.Quantum.Math.Complex),[Complex](xref:Microsoft.Quantum.Math.Complex))</span></span>

<span data-ttu-id="33183-111">Sono previste ampiezze complesse per $ \ket {0} $ e $ \ket {1} $, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="33183-111">Expected complex amplitudes for $\ket{0}$ and $\ket{1}$, respectively.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="33183-112">registra: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="33183-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="33183-113">Qubit il cui stato deve essere dichiarato.</span><span class="sxs-lookup"><span data-stu-id="33183-113">Qubit whose state is to be asserted.</span></span> <span data-ttu-id="33183-114">Si presuppone che questo qubit sia separabile da altri qubits allocati e non sia stato impigliato.</span><span class="sxs-lookup"><span data-stu-id="33183-114">Note that this qubit is assumed to be separable from other allocated qubits, and not entangled.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="33183-115">tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="33183-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="33183-116">Tolleranza additiva in base alla quale le ampiezze effettive possono deviare rispetto a quanto previsto.</span><span class="sxs-lookup"><span data-stu-id="33183-116">Additive tolerance by which actual amplitudes are allowed to deviate from expected.</span></span>
<span data-ttu-id="33183-117">Per informazioni dettagliate, vedere la sezione Osservazioni di seguito.</span><span class="sxs-lookup"><span data-stu-id="33183-117">See remarks below for details.</span></span>



## <a name="output--unit"></a><span data-ttu-id="33183-118">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="33183-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="33183-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="33183-119">Remarks</span></span>

<span data-ttu-id="33183-120">Il codice di Mathematica seguente può essere usato per verificare le espressioni per mi, MX, My, MZ:</span><span class="sxs-lookup"><span data-stu-id="33183-120">The following Mathematica code can be used to verify expressions for mi, mx, my, mz:</span></span>

```mathematica
{Id, X, Y, Z} = Table[PauliMatrix[k], {k, 0, 3}];
st = {{ reA + I imA }, { reB + I imB} };
M = st . ConjugateTranspose[st];
mx = Tr[M.X] // ComplexExpand;
my = Tr[M.Y] // ComplexExpand;
mz = Tr[M.Z] // ComplexExpand;
mi = Tr[M.Id] // ComplexExpand;
2 m == Id mi + X mx + Z mz + Y my // ComplexExpand // Simplify
```

<span data-ttu-id="33183-121">La tolleranza è la $L \_ {\infty} $ distance tra il vettore reale 3 dimensionale (x ₂, x ₃, x ₄) definito da $ \langle\psi | \psi\rangle = x \_ 1 I + x \_ 2 x + x \_ 3 Y + x \_ 4 Z $ e Real Vector (y ₂, y ₃, y ₄) definito da ρ = y ₁ I + y ₂ x + y ₃ Y + y ₄ Z dove ρ è la matrice di densità corrispondente allo stato del registro.</span><span class="sxs-lookup"><span data-stu-id="33183-121">The tolerance is the $L\_{\infty}$ distance between 3 dimensional real vector (x₂,x₃,x₄) defined by $\langle\psi|\psi\rangle = x\_1 I + x\_2 X + x\_3 Y + x\_4 Z$ and real vector (y₂,y₃,y₄) defined by ρ = y₁I + y₂X + y₃Y + y₄Z where ρ is the density matrix corresponding to the state of the register.</span></span>
<span data-ttu-id="33183-122">Ciò si verifica solo se si presuppone che TR (ρ) e TR (| ψ ⟩ ⟨ ψ |) siano entrambi 1 (ad esempio x ₁ = 1/2, y ₁ = 1/2).</span><span class="sxs-lookup"><span data-stu-id="33183-122">This is only true under the assumption that Tr(ρ) and Tr(|ψ⟩⟨ψ|) are both 1 (e.g. x₁ = 1/2, y₁ = 1/2).</span></span>
<span data-ttu-id="33183-123">In caso contrario, la funzione dichiara che la distanza l ∞ tra (x ₂-x ₁, x ₃-x ₁, x ₄-x ₁, x ₄ + x ₁) e (y ₂-y ₁, y ₃-y ₁, y ₄-y ₁, y ₄ + y ₁) è inferiore al parametro tolerance.</span><span class="sxs-lookup"><span data-stu-id="33183-123">If this is not the case, the function asserts that l∞ distance between (x₂-x₁,x₃-x₁,x₄-x₁,x₄+x₁) and (y₂-y₁,y₃-y₁,y₄-y₁,y₄+y₁) is less than the tolerance parameter.</span></span>
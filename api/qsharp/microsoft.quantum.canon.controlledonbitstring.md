---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: ControlledOnBitString (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: 176170cc972ca67b812b84f79cf97ba5418be9b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840811"
---
# <a name="controlledonbitstring-function"></a><span data-ttu-id="49b50-102">ControlledOnBitString (funzione)</span><span class="sxs-lookup"><span data-stu-id="49b50-102">ControlledOnBitString function</span></span>

<span data-ttu-id="49b50-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="49b50-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="49b50-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="49b50-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="49b50-105">Restituisce un'operazione unitaria che applica un oggetto Oracle nel registro di destinazione se lo stato del registro di controllo corrisponde a una maschera di bit specificata.</span><span class="sxs-lookup"><span data-stu-id="49b50-105">Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.</span></span>

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a><span data-ttu-id="49b50-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="49b50-106">Description</span></span>

<span data-ttu-id="49b50-107">L'output di questa funzione è un'operazione che può essere rappresentata da una trasformazione unitaria $U $ tale che \begin{align} U \ket{b_0 b_1 \cdots b_ {n-1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_ {n-1}} \otimes \begin{cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_ {n-1}) = \texttt{bits} \\ \\ \ket{\psi} & \textrm{otherwise} \end{Cases}, \end{align} in cui $V $ è una trasformazione unitaria che rappresenta l'azione dell' `oracle` operazione.</span><span class="sxs-lookup"><span data-stu-id="49b50-107">The output of this function is an operation that can be represented by a unitary transformation $U$ such that \begin{align} U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_{n-1}} \otimes \begin{cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\\\ \ket{\psi} & \textrm{otherwise} \end{cases}, \end{align} where $V$ is a unitary transformation that represents the action of the `oracle` operation.</span></span>

## <a name="input"></a><span data-ttu-id="49b50-108">Input</span><span class="sxs-lookup"><span data-stu-id="49b50-108">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="49b50-109">BITS: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="49b50-109">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="49b50-110">Stringa di bit per controllare l'operazione unitaria specificata su.</span><span class="sxs-lookup"><span data-stu-id="49b50-110">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="49b50-111">Oracle:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="49b50-111">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="49b50-112">Operazione unitaria da applicare al registro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="49b50-112">The unitary operation to be applied on the target register.</span></span>



## <a name="output--qubitt--unit--is-adj--ctl"></a><span data-ttu-id="49b50-113">Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],' t) => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="49b50-113">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="49b50-114">Operazione unitaria che si applica al `oracle` Registro di destinazione se lo stato del registro di controllo corrisponde alla maschera di bit `bits` .</span><span class="sxs-lookup"><span data-stu-id="49b50-114">A unitary operation that applies `oracle` on the target register if the control register state corresponds to the bit mask `bits`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="49b50-115">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="49b50-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="49b50-116">T</span><span class="sxs-lookup"><span data-stu-id="49b50-116">'T</span></span>



## <a name="example"></a><span data-ttu-id="49b50-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="49b50-117">Example</span></span>

<span data-ttu-id="49b50-118">I frammenti di codice seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="49b50-118">The following code snippets are equivalent:</span></span>

```qsharp
(ControlledOnBitString(bits, oracle))(controlRegister, targetRegister);
```

<span data-ttu-id="49b50-119">e</span><span class="sxs-lookup"><span data-stu-id="49b50-119">and</span></span>

```qsharp
within {
    ApplyPauliFromBitString(PauliX, false, bits, controlRegister);
} apply {
    Controlled oracle(controlRegister, targetRegister);
}
```

<span data-ttu-id="49b50-120">Il codice seguente prepara uno stato $ \frac {1} {2} (\ket {00} -\ket {01} + \ket {10} + \ket {11} ) $:</span><span class="sxs-lookup"><span data-stu-id="49b50-120">The following code prepares a state $\frac{1}{2}(\ket{00} - \ket{01} + \ket{10} + \ket{11})$:</span></span>

```qsharp
using (register = Qubit[2]) {
    ApplyToEach(H, register);
    (ControlledOnBitString([false], Z))(register[0..0], register[1]);
}
```

## <a name="remarks"></a><span data-ttu-id="49b50-121">Commenti</span><span class="sxs-lookup"><span data-stu-id="49b50-121">Remarks</span></span>

<span data-ttu-id="49b50-122">Il modello fornito da `bits` può essere più breve di `controlRegister` , nel qual caso i qubits di controllo aggiuntivi vengono ignorati, ovvero non sono controllati in $ \ket {0} $ né $ \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="49b50-122">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="49b50-123">Se `bits` è più lungo di `controlRegister` , viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="49b50-123">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="49b50-124">Data una matrice booleana `bits` e un'operazione unitaria `oracle` , l'output di questa funzione è un'operazione che esegue i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="49b50-124">Given a Boolean array `bits` and a unitary operation `oracle`, the output of this function is an operation that performs the following steps:</span></span>

* <span data-ttu-id="49b50-125">applicare un' `X` operazione a ogni qubit del registro di controllo che corrisponde all' `false` elemento di `bits` ;</span><span class="sxs-lookup"><span data-stu-id="49b50-125">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits`;</span></span>
* <span data-ttu-id="49b50-126">applicare `Controlled oracle` ai registri di controllo e di destinazione;</span><span class="sxs-lookup"><span data-stu-id="49b50-126">apply `Controlled oracle` to the control and target registers;</span></span>
* <span data-ttu-id="49b50-127">applicare un' `X` operazione a ogni qubit del registro di controllo che corrisponde all' `false` elemento di di `bits` nuovo per restituire il registro di controllo allo stato originale.</span><span class="sxs-lookup"><span data-stu-id="49b50-127">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits` again to return the control register to the original state.</span></span>

<span data-ttu-id="49b50-128">L'output del `Controlled` functor è un caso speciale di `ControlledOnBitString` Where `bits` è uguale a `[true, ..., true]` .</span><span class="sxs-lookup"><span data-stu-id="49b50-128">The output of the `Controlled` functor is a special case of `ControlledOnBitString` where `bits` is equal to `[true, ..., true]`.</span></span>
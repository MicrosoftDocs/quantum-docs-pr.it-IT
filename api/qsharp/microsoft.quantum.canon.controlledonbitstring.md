---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: ControlledOnBitString (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: 9435406506fc99fe211f5dce628b21c18ee4f9fe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216660"
---
# <a name="controlledonbitstring-function"></a><span data-ttu-id="dbfab-102">ControlledOnBitString (funzione)</span><span class="sxs-lookup"><span data-stu-id="dbfab-102">ControlledOnBitString function</span></span>

<span data-ttu-id="dbfab-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dbfab-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dbfab-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dbfab-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dbfab-105">Restituisce un'operazione unitaria che applica un oggetto Oracle nel registro di destinazione se lo stato del registro di controllo corrisponde a una maschera di bit specificata.</span><span class="sxs-lookup"><span data-stu-id="dbfab-105">Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.</span></span>

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a><span data-ttu-id="dbfab-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dbfab-106">Description</span></span>

<span data-ttu-id="dbfab-107">L'output di questa funzione è un'operazione che può essere rappresentata da una trasformazione unitaria $U $ tale che \begin{align} U \ket{b_0 b_1 \cdots b_ {n-1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_ {n-1}} \otimes \begin{cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_ {n-1}) = \texttt{bits} \\ \\ \ket{\psi} & \textrm{otherwise} \end{Cases}, \end{align} in cui $V $ è una trasformazione unitaria che rappresenta l'azione dell' `oracle` operazione.</span><span class="sxs-lookup"><span data-stu-id="dbfab-107">The output of this function is an operation that can be represented by a unitary transformation $U$ such that \begin{align} U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_{n-1}} \otimes \begin{cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\\\ \ket{\psi} & \textrm{otherwise} \end{cases}, \end{align} where $V$ is a unitary transformation that represents the action of the `oracle` operation.</span></span>

## <a name="input"></a><span data-ttu-id="dbfab-108">Input</span><span class="sxs-lookup"><span data-stu-id="dbfab-108">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="dbfab-109">BITS: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="dbfab-109">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="dbfab-110">Stringa di bit per controllare l'operazione unitaria specificata su.</span><span class="sxs-lookup"><span data-stu-id="dbfab-110">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="dbfab-111">Oracle:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="dbfab-111">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="dbfab-112">Operazione unitaria da applicare al registro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="dbfab-112">The unitary operation to be applied on the target register.</span></span>



## <a name="output--qubitt--unit--is-adj--ctl"></a><span data-ttu-id="dbfab-113">Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],' t) => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="dbfab-113">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="dbfab-114">Operazione unitaria che si applica al `oracle` Registro di destinazione se lo stato del registro di controllo corrisponde alla maschera di bit `bits` .</span><span class="sxs-lookup"><span data-stu-id="dbfab-114">A unitary operation that applies `oracle` on the target register if the control register state corresponds to the bit mask `bits`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="dbfab-115">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="dbfab-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dbfab-116">T</span><span class="sxs-lookup"><span data-stu-id="dbfab-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="dbfab-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="dbfab-117">Remarks</span></span>

<span data-ttu-id="dbfab-118">Il modello fornito da `bits` può essere più breve di `controlRegister` , nel qual caso i qubits di controllo aggiuntivi vengono ignorati, ovvero non sono controllati in $ \ket {0} $ né $ \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="dbfab-118">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="dbfab-119">Se `bits` è più lungo di `controlRegister` , viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="dbfab-119">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="dbfab-120">Data una matrice booleana `bits` e un'operazione unitaria `oracle` , l'output di questa funzione è un'operazione che esegue i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="dbfab-120">Given a Boolean array `bits` and a unitary operation `oracle`, the output of this function is an operation that performs the following steps:</span></span>

* <span data-ttu-id="dbfab-121">applicare un' `X` operazione a ogni qubit del registro di controllo che corrisponde all' `false` elemento di `bits` ;</span><span class="sxs-lookup"><span data-stu-id="dbfab-121">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits`;</span></span>
* <span data-ttu-id="dbfab-122">applicare `Controlled oracle` ai registri di controllo e di destinazione;</span><span class="sxs-lookup"><span data-stu-id="dbfab-122">apply `Controlled oracle` to the control and target registers;</span></span>
* <span data-ttu-id="dbfab-123">applicare un' `X` operazione a ogni qubit del registro di controllo che corrisponde all' `false` elemento di di `bits` nuovo per restituire il registro di controllo allo stato originale.</span><span class="sxs-lookup"><span data-stu-id="dbfab-123">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits` again to return the control register to the original state.</span></span>

<span data-ttu-id="dbfab-124">L'output del `Controlled` functor è un caso speciale di `ControlledOnBitString` Where `bits` è uguale a `[true, ..., true]` .</span><span class="sxs-lookup"><span data-stu-id="dbfab-124">The output of the `Controlled` functor is a special case of `ControlledOnBitString` where `bits` is equal to `[true, ..., true]`.</span></span>
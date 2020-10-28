---
uid: Microsoft.Quantum.Canon.ApplyPauliFromBitString
title: Operazione ApplyPauliFromBitString
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauliFromBitString
qsharp.summary: Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.
ms.openlocfilehash: 09754accb92c1339b781003e5722e3c8f5884e6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717811"
---
# <a name="applypaulifrombitstring-operation"></a><span data-ttu-id="22421-102">Operazione ApplyPauliFromBitString</span><span class="sxs-lookup"><span data-stu-id="22421-102">ApplyPauliFromBitString operation</span></span>

<span data-ttu-id="22421-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="22421-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="22421-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="22421-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="22421-105">Applica un operatore Pauli in ogni qubit in una matrice se il bit corrispondente di una matrice booleana corrisponde a un input specificato.</span><span class="sxs-lookup"><span data-stu-id="22421-105">Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.</span></span>

```qsharp
operation ApplyPauliFromBitString (pauli : Pauli, bitApply : Bool, bits : Bool[], qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="22421-106">Input</span><span class="sxs-lookup"><span data-stu-id="22421-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="22421-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="22421-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="22421-108">Operatore Pauli da applicare a `qubits[idx]` where `bitsApply == bits[idx]`</span><span class="sxs-lookup"><span data-stu-id="22421-108">Pauli operator to apply to `qubits[idx]` where `bitsApply == bits[idx]`</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="22421-109">in una delle seguenti operazioni: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="22421-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="22421-110">applica Pauli se bit è questo valore</span><span class="sxs-lookup"><span data-stu-id="22421-110">apply Pauli if bit is this value</span></span>


### <a name="bits--bool"></a><span data-ttu-id="22421-111">BITS: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="22421-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="22421-112">Registro booleano che specifica quale qubit corrispondente in `qubits` deve essere utilizzato</span><span class="sxs-lookup"><span data-stu-id="22421-112">Boolean register specifying which corresponding qubit in `qubits` should be operated on</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="22421-113">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="22421-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="22421-114">Registro Quantum su cui applicare in modo selettivo l'operatore Pauli specificato</span><span class="sxs-lookup"><span data-stu-id="22421-114">Quantum register on which to selectively apply the specified Pauli operator</span></span>



## <a name="output--unit"></a><span data-ttu-id="22421-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="22421-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="22421-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="22421-116">Remarks</span></span>

<span data-ttu-id="22421-117">La matrice booleana e il registro Quantum devono essere di uguale lunghezza.</span><span class="sxs-lookup"><span data-stu-id="22421-117">The Boolean array and the quantum register must be of equal length.</span></span>
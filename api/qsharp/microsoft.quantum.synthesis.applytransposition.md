---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: Operazione ApplyTransposition
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: 46cf8c2c891aa02b0d8a1397e6c2b7a4b8618048
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855572"
---
# <a name="applytransposition-operation"></a><span data-ttu-id="cf70d-102">Operazione ApplyTransposition</span><span class="sxs-lookup"><span data-stu-id="cf70d-102">ApplyTransposition operation</span></span>

<span data-ttu-id="cf70d-103">Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="cf70d-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="cf70d-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cf70d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="cf70d-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cf70d-105">Description</span></span>

<span data-ttu-id="cf70d-106">Questa operazione scambia l'ampiezza in corrispondenza dell'indice `a` con l'ampiezza in corrispondenza dell'indice `b` nel vettore di stato specificato di `register` lunghezza $n $.</span><span class="sxs-lookup"><span data-stu-id="cf70d-106">This operation swaps the amplitude at index `a` with the amplitude at index `b` in the given state-vector of `register` of length $n$.</span></span>  <span data-ttu-id="cf70d-107">Se `a` è uguale `b` a, il vettore di stato non viene modificato.</span><span class="sxs-lookup"><span data-stu-id="cf70d-107">If `a` equals `b`, the state-vector is not changed.</span></span>

## <a name="input"></a><span data-ttu-id="cf70d-108">Input</span><span class="sxs-lookup"><span data-stu-id="cf70d-108">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="cf70d-109">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cf70d-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cf70d-110">Primo indice (deve essere un valore compreso tra 0 e $2 ^ n-$1)</span><span class="sxs-lookup"><span data-stu-id="cf70d-110">First index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="b--int"></a><span data-ttu-id="cf70d-111">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cf70d-111">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cf70d-112">Secondo indice (deve essere un valore compreso tra 0 e $2 ^ n-$1)</span><span class="sxs-lookup"><span data-stu-id="cf70d-112">Second index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="cf70d-113">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="cf70d-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="cf70d-114">Elenco di $n $ qubits a cui viene applicata la trasposizione.</span><span class="sxs-lookup"><span data-stu-id="cf70d-114">A list of $n$ qubits to which the transposition is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cf70d-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cf70d-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="cf70d-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="cf70d-116">Example</span></span>

<span data-ttu-id="cf70d-117">Preparare una superposizione uniforme dei numeri stati $ | 1 \ Rangle $, $ | 2 \ Rangle $ e $ | 3 \ Rangle $ su 2 qubits.</span><span class="sxs-lookup"><span data-stu-id="cf70d-117">Prepare a uniform superposition of number states $|1\rangle$, $|2\rangle$, and $|3\rangle$ on 2 qubits.</span></span>

```qsharp
using (qubits = Qubit[2]) {
  let register = LittleEndian(qubits);
  PrepareUniformSuperposition(3, register);
  ApplyTransposition(0, 3, register);
}
```
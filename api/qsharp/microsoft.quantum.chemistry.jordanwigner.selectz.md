---
uid: Microsoft.Quantum.Chemistry.JordanWigner.SelectZ
title: Operazione SelectZ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: SelectZ
qsharp.summary: A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$. That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$
ms.openlocfilehash: 171bbe28ce8f10ca4b213a94b23f8c049546e3bf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713793"
---
# <a name="selectz-operation"></a><span data-ttu-id="a9eaa-102">Operazione SelectZ</span><span class="sxs-lookup"><span data-stu-id="a9eaa-102">SelectZ operation</span></span>

<span data-ttu-id="a9eaa-103">Spazio dei nomi: [Microsoft. Quantum. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="a9eaa-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="a9eaa-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a9eaa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a9eaa-105">Un Unity $U $ che applica Pauli $Z $ Gate in una qubits $p $ conditioned in uno stato di indice $ \ket{p} $.</span><span class="sxs-lookup"><span data-stu-id="a9eaa-105">A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$.</span></span> <span data-ttu-id="a9eaa-106">Ovvero $ $ \begin{align} U\ket {p} \ KET {\ psi} = \ket{p}Z \_ p\ket {\ psi} \end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="a9eaa-106">That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$</span></span>

```qsharp
operation SelectZ (indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="a9eaa-107">Input</span><span class="sxs-lookup"><span data-stu-id="a9eaa-107">Input</span></span>

### <a name="indexregister--littleendian"></a><span data-ttu-id="a9eaa-108">indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a9eaa-108">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a9eaa-109">Lo stato $ \ket{p} $ di questo registro determina il qubit a cui viene applicato $Z $.</span><span class="sxs-lookup"><span data-stu-id="a9eaa-109">The state $\ket{p}$ of this register determines the qubit on which $Z$ is applied.</span></span>


### <a name="targetregister--qubit"></a><span data-ttu-id="a9eaa-110">targetRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a9eaa-110">targetRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a9eaa-111">Registro di qubits a cui vengono applicati gli operatori Pauli.</span><span class="sxs-lookup"><span data-stu-id="a9eaa-111">Register of qubits on which the Pauli operators are applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a9eaa-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a9eaa-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


---
uid: Microsoft.Quantum.Chemistry.JordanWigner.SelectZ
title: Operazione SelectZ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: SelectZ
qsharp.summary: A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$. That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$
ms.openlocfilehash: 2b38be5c196d81635daa8b478f6e727fdf378c62
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850230"
---
# <a name="selectz-operation"></a><span data-ttu-id="c0938-102">Operazione SelectZ</span><span class="sxs-lookup"><span data-stu-id="c0938-102">SelectZ operation</span></span>

<span data-ttu-id="c0938-103">Spazio dei nomi: [Microsoft. Quantum. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="c0938-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="c0938-104">Pacchetto: [Microsoft. Quantum. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="c0938-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="c0938-105">Un Unity $U $ che applica Pauli $Z $ Gate in una qubits $p $ conditioned in uno stato di indice $ \ket{p} $.</span><span class="sxs-lookup"><span data-stu-id="c0938-105">A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$.</span></span> <span data-ttu-id="c0938-106">Ovvero $ $ \begin{align} U\ket {p} \ KET {\ psi} = \ket{p}Z \_ p\ket {\ psi} \end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="c0938-106">That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$</span></span>

```qsharp
operation SelectZ (indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c0938-107">Input</span><span class="sxs-lookup"><span data-stu-id="c0938-107">Input</span></span>

### <a name="indexregister--littleendian"></a><span data-ttu-id="c0938-108">indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c0938-108">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c0938-109">Lo stato $ \ket{p} $ di questo registro determina il qubit a cui viene applicato $Z $.</span><span class="sxs-lookup"><span data-stu-id="c0938-109">The state $\ket{p}$ of this register determines the qubit on which $Z$ is applied.</span></span>


### <a name="targetregister--qubit"></a><span data-ttu-id="c0938-110">targetRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c0938-110">targetRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c0938-111">Registro di qubits a cui vengono applicati gli operatori Pauli.</span><span class="sxs-lookup"><span data-stu-id="c0938-111">Register of qubits on which the Pauli operators are applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c0938-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c0938-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


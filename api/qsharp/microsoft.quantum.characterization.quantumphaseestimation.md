---
uid: Microsoft.Quantum.Characterization.QuantumPhaseEstimation
title: Operazione QuantumPhaseEstimation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: QuantumPhaseEstimation
qsharp.summary: Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.
ms.openlocfilehash: 14ba3e012f6561e7089f9fe59b2a13516b211d51
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204216"
---
# <a name="quantumphaseestimation-operation"></a><span data-ttu-id="d0653-102">Operazione QuantumPhaseEstimation</span><span class="sxs-lookup"><span data-stu-id="d0653-102">QuantumPhaseEstimation operation</span></span>

<span data-ttu-id="d0653-103">Spazio dei nomi: [Microsoft. Quantum. characteration](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="d0653-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="d0653-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d0653-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d0653-105">Esegue l'algoritmo di stima della fase quantistica per un determinato Oracle `U` e `targetState` , leggendo la fase in un registro Quantum big-endian.</span><span class="sxs-lookup"><span data-stu-id="d0653-105">Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.</span></span>

```qsharp
operation QuantumPhaseEstimation (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[], controlRegister : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d0653-106">Input</span><span class="sxs-lookup"><span data-stu-id="d0653-106">Input</span></span>

### <a name="oracle--discreteoracle"></a><span data-ttu-id="d0653-107">Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="d0653-107">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="d0653-108">Un'operazione che implementa $U ^ m $ per dati Integer specificati m.</span><span class="sxs-lookup"><span data-stu-id="d0653-108">An operation implementing $U^m$ for given integer powers m.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="d0653-109">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d0653-109">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d0653-110">Un registro Quantum che rappresenta lo stato $ \ket{\Phi} $ agito da $U $.</span><span class="sxs-lookup"><span data-stu-id="d0653-110">A quantum register representing the state $\ket{\phi}$ acted on by $U$.</span></span> <span data-ttu-id="d0653-111">Se $ \ket{\Phi} $ è un autostato di $U $, $U \ket{\Phi} = e ^ {i\phi} \ket{\Phi} $ per $ \Phi \In [0, 2 \ PI) $ una fase sconosciuta.</span><span class="sxs-lookup"><span data-stu-id="d0653-111">If $\ket{\phi}$ is an eigenstate of $U$, $U\ket{\phi} = e^{i\phi} \ket{\phi}$ for $\phi \in [0, 2\pi)$ an unknown phase.</span></span>


### <a name="controlregister--bigendian"></a><span data-ttu-id="d0653-112">controlRegister: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="d0653-112">controlRegister : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="d0653-113">Registro Integer di rappresentazione big-endian che può essere utilizzato per controllare l'oggetto Oracle specificato e che conterrà la rappresentazione di $ \Phi $ dopo l'applicazione di questa operazione.</span><span class="sxs-lookup"><span data-stu-id="d0653-113">A big-endian representation integer register that can be used to control the provided oracle, and that will contain the a representation of $\phi$ following the application of this operation.</span></span> <span data-ttu-id="d0653-114">Si presuppone che controlRegister si avvii nello stato iniziale $ \ket{00\cdots 0} $, dove la lunghezza del registro indica la precisione desiderata.</span><span class="sxs-lookup"><span data-stu-id="d0653-114">The controlRegister is assumed to start in the initial state $\ket{00\cdots 0}$, where the length of the register indicates the desired precision.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d0653-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d0653-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


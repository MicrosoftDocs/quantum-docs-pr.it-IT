---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracle
title: Tipo definito dall'utente DeterministicStateOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracle
qsharp.summary: >-
  Represents an oracle for deterministic state preparation.

  The input to the oracle $O$ is:

  - The register that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: f02267d48cf42fb5b02782dc6b667ac7b60a05dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724297"
---
# <a name="deterministicstateoracle-user-defined-type"></a><span data-ttu-id="0088e-102">Tipo definito dall'utente DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="0088e-102">DeterministicStateOracle user defined type</span></span>

<span data-ttu-id="0088e-103">Spazio dei nomi: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="0088e-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="0088e-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0088e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0088e-105">Rappresenta un oggetto Oracle per la preparazione dello stato deterministico.</span><span class="sxs-lookup"><span data-stu-id="0088e-105">Represents an oracle for deterministic state preparation.</span></span>

<span data-ttu-id="0088e-106">L'input per Oracle $O $ è:</span><span class="sxs-lookup"><span data-stu-id="0088e-106">The input to the oracle $O$ is:</span></span>

- <span data-ttu-id="0088e-107">Registro in cui viene archiviato lo stato quantum desiderato $ \ket{\psi} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="0088e-107">The register that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="0088e-108">Commenti</span><span class="sxs-lookup"><span data-stu-id="0088e-108">Remarks</span></span>

<span data-ttu-id="0088e-109">Questo Oracle definito da $O \ket {0} = \ket{\psi} $ agisce sullo stato di base di calcolo $ \ket {0} $ per creare lo stato $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="0088e-109">This oracle defined by $O\ket{0}=\ket{\psi}$ acts on the on computational basis state $\ket{0}$ to create the state $\ket{\psi}$.</span></span>
<span data-ttu-id="0088e-110">Il primo parametro è il registro qubit di $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="0088e-110">The first parameter is the qubit register of $\ket{\psi}$.</span></span>
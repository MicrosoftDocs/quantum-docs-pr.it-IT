---
title: Quantum Development Kit Toffoli Simulator
description: Informazioni sul simulatore Microsoft QDK Toffoli, un simulatore Quantum con scopo speciale che può essere usato con milioni di qubits.
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 01/16/2019
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: 8a29caaa0fa058600a74e7d130e644374cbfa19c
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276025"
---
# <a name="quantum-development-kit-toffoli-simulator"></a><span data-ttu-id="1a27a-103">Quantum Development Kit Toffoli Simulator</span><span class="sxs-lookup"><span data-stu-id="1a27a-103">Quantum Development Kit Toffoli Simulator</span></span>

<span data-ttu-id="1a27a-104">Quantum Development Kit fornisce un simulatore Toffoli, che è un simulatore per scopi specifici che consente di simulare gli algoritmi quantistici limitati alle operazioni Quantum x, CNOT e multicontrollo (tutti i calcoli e la logica classica sono disponibili).</span><span class="sxs-lookup"><span data-stu-id="1a27a-104">The Quantum Development Kit provides a Toffoli simulator, which is a special-purpose simulator that can simulate quantum algorithms that are limited to X, CNOT, and multi-controlled X quantum operations (all classical logic and computations are available).</span></span>

<span data-ttu-id="1a27a-105">Sebbene il simulatore Toffoli sia molto più limitato in termini di funzionamento rispetto al [simulatore di stato completo](xref:microsoft.quantum.machines.full-state-simulator), può simulare molto più qubits.</span><span class="sxs-lookup"><span data-stu-id="1a27a-105">While the Toffoli simulator is much more restricted in operation than the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), it can simulate far more qubits.</span></span>
<span data-ttu-id="1a27a-106">Il simulatore Toffoli può essere usato con milioni di qubits, mentre il simulatore di stato completo è in genere limitato a circa 30.</span><span class="sxs-lookup"><span data-stu-id="1a27a-106">The Toffoli simulator can be used with millions of qubits, while the full state simulator is generally limited to about 30.</span></span>
<span data-ttu-id="1a27a-107">Può eseguire ed eseguire il debug di un set limitato di algoritmi Quantum scritti in Q # nel computer. ad esempio, gli Oracle che valutano le funzioni booleane possono essere implementati usando queste attività di controllo e quindi testati su un numero elevato di qubits con questo simulatore.</span><span class="sxs-lookup"><span data-stu-id="1a27a-107">It can execute and debug a limited set of quantum algorithms written in Q# on your computer; for instance, oracles that evaluate Boolean functions can be implemented using these gates and so tested on vary large numbers of qubits using this simulator.</span></span>

<span data-ttu-id="1a27a-108">Questo simulatore quantum viene esposto tramite la `ToffoliSimulator` classe.</span><span class="sxs-lookup"><span data-stu-id="1a27a-108">This quantum simulator is exposed via the `ToffoliSimulator` class.</span></span>
<span data-ttu-id="1a27a-109">Per usare il simulatore, è sufficiente creare un'istanza di questa classe e passarla al `Run` metodo dell'operazione Quantum che si vuole eseguire insieme ai restanti parametri:</span><span class="sxs-lookup"><span data-stu-id="1a27a-109">To use the simulator, simply create an instance of this class and pass it to the `Run` method of the quantum operation you want to execute along with the rest of the parameters:</span></span>

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

## <a name="other-operations"></a><span data-ttu-id="1a27a-110">Altre operazioni</span><span class="sxs-lookup"><span data-stu-id="1a27a-110">Other Operations</span></span>

<span data-ttu-id="1a27a-111">`ToffoliSimulator`Supporta le rotazioni e exponentiated Paulis, ad esempio `R` e `Exp` , quando l'operazione risultante è uguale a `X` o all'identità.</span><span class="sxs-lookup"><span data-stu-id="1a27a-111">The `ToffoliSimulator` supports rotations and exponentiated Paulis, such as `R` and `Exp`, when the resulting operation is equal to `X` or to the identity.</span></span>

<span data-ttu-id="1a27a-112">La misurazione e l'asserzione sono supportate, ma solo in base a Pauli `Z` .</span><span class="sxs-lookup"><span data-stu-id="1a27a-112">Measurement and assert are supported, but only in the Pauli `Z` basis.</span></span>
<span data-ttu-id="1a27a-113">Si noti che la probabilità di alcune misure è sempre 0 o 1. non esiste alcuna casualità nel simulatore Toffoli.</span><span class="sxs-lookup"><span data-stu-id="1a27a-113">Note that the probability of some measurement is always either 0 or 1; there is no randomness in the Toffoli simulator.</span></span>

<span data-ttu-id="1a27a-114">`DumpMachine`e `DumpRegister` sono supportati.</span><span class="sxs-lookup"><span data-stu-id="1a27a-114">`DumpMachine` and `DumpRegister` are supported.</span></span>
<span data-ttu-id="1a27a-115">Entrambi restituiscono lo `Z` stato di base corrente di ogni qubit, un qubit per riga.</span><span class="sxs-lookup"><span data-stu-id="1a27a-115">They both output the current `Z`-basis state of each qubit, one qubit per line.</span></span>

## <a name="qubitcount"></a><span data-ttu-id="1a27a-116">QubitCount</span><span class="sxs-lookup"><span data-stu-id="1a27a-116">QubitCount</span></span>

<span data-ttu-id="1a27a-117">Per impostazione predefinita, `ToffoliSimulator` alloca spazio per 65.536 qubits.</span><span class="sxs-lookup"><span data-stu-id="1a27a-117">By default, the `ToffoliSimulator` allocates space for 65,536 qubits.</span></span>
<span data-ttu-id="1a27a-118">Se l'algoritmo richiede più di questo, è possibile modificare il numero di qubit fornendo un valore per il `qubitCount` parametro al costruttore.</span><span class="sxs-lookup"><span data-stu-id="1a27a-118">If your algorithm requires more than this, you can change the qubit count by providing a value for the `qubitCount` parameter to the constructor.</span></span>
<span data-ttu-id="1a27a-119">Ogni qubit aggiuntivo richiede un byte aggiuntivo di memoria, quindi non vi è alcun costo significativo per sovrastimare il numero di qubits necessarie.</span><span class="sxs-lookup"><span data-stu-id="1a27a-119">Each additional qubit requires an additional byte of memory, so there is no significant cost to overestimating the number of qubits you'll need.</span></span>

<span data-ttu-id="1a27a-120">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1a27a-120">For example:</span></span>

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```

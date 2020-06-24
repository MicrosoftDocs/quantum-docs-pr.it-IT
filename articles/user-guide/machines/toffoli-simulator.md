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
# <a name="quantum-development-kit-toffoli-simulator"></a>Quantum Development Kit Toffoli Simulator

Quantum Development Kit fornisce un simulatore Toffoli, che è un simulatore per scopi specifici che consente di simulare gli algoritmi quantistici limitati alle operazioni Quantum x, CNOT e multicontrollo (tutti i calcoli e la logica classica sono disponibili).

Sebbene il simulatore Toffoli sia molto più limitato in termini di funzionamento rispetto al [simulatore di stato completo](xref:microsoft.quantum.machines.full-state-simulator), può simulare molto più qubits.
Il simulatore Toffoli può essere usato con milioni di qubits, mentre il simulatore di stato completo è in genere limitato a circa 30.
Può eseguire ed eseguire il debug di un set limitato di algoritmi Quantum scritti in Q # nel computer. ad esempio, gli Oracle che valutano le funzioni booleane possono essere implementati usando queste attività di controllo e quindi testati su un numero elevato di qubits con questo simulatore.

Questo simulatore quantum viene esposto tramite la `ToffoliSimulator` classe.
Per usare il simulatore, è sufficiente creare un'istanza di questa classe e passarla al `Run` metodo dell'operazione Quantum che si vuole eseguire insieme ai restanti parametri:

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

## <a name="other-operations"></a>Altre operazioni

`ToffoliSimulator`Supporta le rotazioni e exponentiated Paulis, ad esempio `R` e `Exp` , quando l'operazione risultante è uguale a `X` o all'identità.

La misurazione e l'asserzione sono supportate, ma solo in base a Pauli `Z` .
Si noti che la probabilità di alcune misure è sempre 0 o 1. non esiste alcuna casualità nel simulatore Toffoli.

`DumpMachine`e `DumpRegister` sono supportati.
Entrambi restituiscono lo `Z` stato di base corrente di ogni qubit, un qubit per riga.

## <a name="qubitcount"></a>QubitCount

Per impostazione predefinita, `ToffoliSimulator` alloca spazio per 65.536 qubits.
Se l'algoritmo richiede più di questo, è possibile modificare il numero di qubit fornendo un valore per il `qubitCount` parametro al costruttore.
Ogni qubit aggiuntivo richiede un byte aggiuntivo di memoria, quindi non vi è alcun costo significativo per sovrastimare il numero di qubits necessarie.

Ad esempio:

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```

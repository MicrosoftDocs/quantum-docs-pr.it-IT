---
title: Quantum Toffoli Simulator-Quantum Development Kit
description: Informazioni sul simulatore Microsoft QDK Toffoli, un simulatore Quantum con scopo speciale che può essere usato con milioni di qubits.
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 6/25/2020
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: a6ceee592e628215511ec83475d9e25bf54674f7
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870618"
---
# <a name="quantum-development-kit-qdk-toffoli-simulator"></a>Simulatore di Toffoli per Quantum Development Kit (QDK)

Il simulatore di Toffoli QDK è un simulatore per scopi specifici con un ambito limitato e supporta solo `X` `CNOT` le operazioni Quantum, e multicontrollate `X` . Sono disponibili tutte le logiche e i calcoli classici.

Sebbene il simulatore Toffoli sia più limitato alle funzionalità rispetto al [simulatore di stato completo](xref:microsoft.quantum.machines.full-state-simulator), ha il vantaggio di poter simulare molto più qubits. Il simulatore Toffoli può essere usato con milioni di qubits, mentre il simulatore di stato completo è limitato a circa 30 qubits. Questa operazione è utile, ad esempio, con i Oracle che valutano le funzioni booleane, che possono essere implementati usando un set limitato di algoritmi supportati e testati su un numero elevato di qubits.

## <a name="invoking-the-toffoli-simulator"></a>Richiamo del simulatore Toffoli

Il simulatore Toffoli viene esposto tramite la `ToffoliSimulator` classe. Per ulteriori informazioni, vedere [modalità di esecuzione di un programma Q #](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-toffoli-simulator-from-c"></a>Richiamo del simulatore Toffoli da C #

Come per gli altri computer di destinazione, creare prima un'istanza della `ToffoliSimulator` classe e quindi passarla come primo parametro del metodo di un'operazione `Run` .

Si noti che, a differenza della `QuantumSimulator` classe, la `ToffoliSimulator` classe non implementa l' <xref:System.IDisposable> interfaccia e pertanto non è necessario racchiuderla in un' `using` istruzione.

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

### <a name="invoking-the-toffoli-simulator-from-python"></a>Richiamo del simulatore Toffoli da Python

Usare il metodo [toffoli_simulate ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) dalla libreria Python con l'operazione Q # importata:

```python
qubit_result = myOperation.toffoli_simulate()
```

### <a name="invoking-the-toffoli-simulator-from-the-command-line"></a>Richiamo del simulatore Toffoli dalla riga di comando

Quando si esegue un programma Q # dalla riga di comando, usare il parametro **--Simulator** (o **-s** Shortcut) per specificare il computer di destinazione del simulatore Toffoli. Il comando che segue esegue un programma usando lo strumento di stima delle risorse: 

```dotnetcli
dotnet run -s ToffoliSimulator
```

### <a name="invoking-the-toffoli-simulator-from-juptyer-notebooks"></a>Richiamo del simulatore Toffoli da Juptyer Notebooks

Usare il comando IQ # Magic [% Toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) per eseguire l'operazione Q #.

```
%toffoli myOperation
```

## <a name="supported-operations"></a>Operazioni supportate

Il simulatore Toffoli supporta:

* Rotazioni e exponentiated Paulis, ad esempio `R` e `Exp` , quando l'operazione risultante è uguale a `X` o alla matrice di identità.
* Operazioni di misurazione e [asserzione](xref:microsoft.quantum.diagnostics.assertmeasurement) , ma solo in `Z` base a Pauli. Si noti che la probabilità di un'operazione di misurazione è sempre **0** o **1**. non esiste alcuna casualità nel simulatore Toffoli.
* `DumpMachine``DumpRegister`funzioni e.
Entrambe le funzioni restituiscono lo `Z` stato di base corrente di ogni qubit, un qubit per riga.

## <a name="specifying-the-number-of-qubits"></a>Specifica del numero di qubits

Per impostazione predefinita, un' `ToffoliSimulator` istanza di alloca spazio per 65.536 qubits.
Se l'algoritmo richiede più qubits di questo, è possibile specificare il numero di qubit fornendo un valore per il `qubitCount` parametro al costruttore.
Ogni qubit aggiuntivo richiede un solo byte di memoria, quindi non vi è alcun costo significativo per sovrastimare il numero di qubits necessarie.

Ad esempio:

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```

## <a name="see-also"></a>Vedere anche

- [Strumento di stima risorse Quantum](xref:microsoft.quantum.machines.resources-estimator)
- [Simulatore di traccia Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [Simulatore di stato completo Quantum](xref:microsoft.quantum.machines.full-state-simulator) 
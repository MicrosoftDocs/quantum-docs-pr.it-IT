---
uid: Microsoft.Quantum.Simulation.QuantumWalkByQubitization
title: QuantumWalkByQubitization (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: QuantumWalkByQubitization
qsharp.summary: Converts a block-encoding reflection into a quantum walk.
ms.openlocfilehash: ef9740f1867cee3c79a7ec0bf90f2c2f4b39ad28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725574"
---
# <a name="quantumwalkbyqubitization-function"></a>QuantumWalkByQubitization (funzione)

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto [](https://nuget.org/packages/)


Converte una reflection di codifica a blocchi in una procedura quantistica.

```qsharp
function QuantumWalkByQubitization (blockEncoding : Microsoft.Quantum.Simulation.BlockEncodingReflection) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="description"></a>Descrizione

Dato un oggetto `BlockEncodingReflection` rappresentato da un unity $U $ che codifica un operatore $H $ di interesse, lo converte in un quantum walk $W $ contenente lo spettro di $ \pm e ^ {\pm i\sin ^ {-1} (H)} $.

## <a name="input"></a>Input

### <a name="blockencoding--blockencodingreflection"></a>blockEncoding: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)

`BlockEncodingReflection`Unitario $U $ da convertire in un percorso quantistico.



## <a name="output--qubitqubit--unit-adj--ctl"></a>Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Un quantum walk $W $ agisce congiuntamente sui registri `a` e `s` tale codifica a blocchi $H $ e contiene lo spettro di $ \pm e ^ {\pm i\sin ^ {-1} (H)} $.

## <a name="references"></a>Riferimenti

- Simulazione Hamiltoniana di Qubitization Guang Hao low, Isaac L. Chuang https://arxiv.org/abs/1610.06546

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Simulation. BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [Microsoft. Quantum. Simulation. BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)
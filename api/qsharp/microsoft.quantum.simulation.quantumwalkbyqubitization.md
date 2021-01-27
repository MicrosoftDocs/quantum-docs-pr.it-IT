---
uid: Microsoft.Quantum.Simulation.QuantumWalkByQubitization
title: QuantumWalkByQubitization (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: QuantumWalkByQubitization
qsharp.summary: Converts a block-encoding reflection into a quantum walk.
ms.openlocfilehash: 8ffb6eb77a3f910d3064c4a3c90215d5d9a694aa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851045"
---
# <a name="quantumwalkbyqubitization-function"></a>QuantumWalkByQubitization (funzione)

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Converte una reflection di codifica a blocchi in una procedura quantistica.

```qsharp
function QuantumWalkByQubitization (blockEncoding : Microsoft.Quantum.Simulation.BlockEncodingReflection) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="description"></a>Descrizione

Dato un oggetto `BlockEncodingReflection` rappresentato da un unity $U $ che codifica un operatore $H $ di interesse, lo converte in un quantum walk $W $ contenente lo spettro di $ \pm e ^ {\pm i\sin ^ {-1} (H)} $.

## <a name="input"></a>Input

### <a name="blockencoding--blockencodingreflection"></a>blockEncoding: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)

`BlockEncodingReflection`Unitario $U $ da convertire in un percorso quantistico.



## <a name="output--qubitqubit--unit--is-adj--ctl"></a>Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL

Un quantum walk $W $ agisce congiuntamente sui registri `a` e `s` tale codifica a blocchi $H $ e contiene lo spettro di $ \pm e ^ {\pm i\sin ^ {-1} (H)} $.

## <a name="references"></a>Riferimenti

- Simulazione Hamiltoniana di Qubitization Guang Hao low, Isaac L. Chuang https://arxiv.org/abs/1610.06546

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Simulation. BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [Microsoft. Quantum. Simulation. BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)
---
uid: Microsoft.Quantum.Preparation.QuantumROMQubitCount
title: QuantumROMQubitCount (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROMQubitCount
qsharp.summary: >-
  > [!WARNING]

  > QuantumROMQubitCount has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> instead.


  Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.
ms.openlocfilehash: 0ec1e042b9f675505f73bfcdcc6706d0bc0367df
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210404"
---
# <a name="quantumromqubitcount-function"></a>QuantumROMQubitCount (funzione)

Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> QuantumROMQubitCount è stato deprecato. Usare invece <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements>.

Restituisce il numero totale di qubits che devono essere allocati all'operazione restituita da `QuantumROM` .

```qsharp
function QuantumROMQubitCount (targetError : Double, nCoeffs : Int) : (Int, (Int, Int))
```


## <a name="input"></a>Input

### <a name="targeterror--double"></a>targetError: [Double](xref:microsoft.quantum.lang-ref.double)

Errore di destinazione $ \epsilon $.


### <a name="ncoeffs--int"></a>nCoeffs: [int](xref:microsoft.quantum.lang-ref.int)

Numero di coefficienti specificati in `QuantumROM` .



## <a name="output--intintint"></a>Output: ([int](xref:microsoft.quantum.lang-ref.int), ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)))

## <a name="first-parameter"></a>Primo parametro

Tupla `(x,(y,z))` `x = y + z` in cui è il numero totale di qubits allocato, `y` è il numero di qubits per il `LittleEndian` registro e `z` è il numero di Garbage qubits.
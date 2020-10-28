---
uid: Microsoft.Quantum.Canon.ApproximatelyMultiplexZ
title: Operazione ApproximatelyMultiplexZ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyMultiplexZ
qsharp.summary: Applies a Pauli Z rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: ac5195b8b3afaad4d41fe50d45652644e2397e1b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716792"
---
# <a name="approximatelymultiplexz-operation"></a>Operazione ApproximatelyMultiplexZ

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Applica una rotazione di Pauli Z condizionata su una matrice di qubits, troncando gli angoli di rotazione piccoli in base a una determinata tolleranza.

```qsharp
operation ApproximatelyMultiplexZ (tolerance : Double, coefficients : Double[], control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="description"></a>Descrizione

Questa operazione applica l'operazione unitaria controllata di moltiplicazione che esegue rotazioni in base all'angolo $ \ theta_j $ about Single-qubit Pauli operator $Z $ quando viene controllata dallo $n $-qubit numero stato $ \ket{j} $.
In particolare, questa operazione può essere rappresentata dall'unità

$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i Z \ theta_j}.
\end{align} $ $

## <a name="input"></a>Input

### <a name="tolerance--double"></a>tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)

Tolleranza sotto la quale vengono troncati i coefficienti di piccole dimensioni.


### <a name="coefficients--double"></a>coefficienti: [Double](xref:microsoft.quantum.lang-ref.double)[]

Matrice di un massimo di $2 ^ n $ coefficienti $ \ theta_j $. Il coefficiente $j $ TH indicizza lo stato del numero $ \ket{j} $ codificato in formato little-endian.


### <a name="control--littleendian"></a>controllo: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n il registro di controllo $-qubit che codifica gli Stati numerici $ \ket{j} $ in formato little-endian.


### <a name="target--qubit"></a>destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Singolo registro qubit ruotato da $e ^ {i P \ theta_j} $.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

`coefficients` verrà riempito con gli elementi $ \ theta_j = $0,0 se sono specificati meno di $2 ^ n $.

## <a name="references"></a>Riferimenti

- Sintesi dei circuiti logici Quantum Simone V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. MultiplexZ](xref:Microsoft.Quantum.Canon.MultiplexZ)
---
uid: Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryStateCP
title: Operazione ApproximatelyPrepareArbitraryStateCP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApproximatelyPrepareArbitraryStateCP
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.
ms.openlocfilehash: 44352a4d6325c128539351695fb14d3706ce842f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226537"
---
# <a name="approximatelypreparearbitrarystatecp-operation"></a>Operazione ApproximatelyPrepareArbitraryStateCP

Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dato un set di coefficienti e un registro Quantum con codifica little-endian, prepara uno stato in tale registro descritto dai coefficienti specificati, fino a una determinata tolleranza di approssimazione.

```qsharp
operation ApproximatelyPrepareArbitraryStateCP (tolerance : Double, coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Descrizione

Questa operazione prepara uno stato quantico arbitrario $ \ket{\psi} $ con coefficienti complessi $r _j e ^ {i t_j} $ dallo stato di base di calcolo $n $-qubit $ \ket{0 \cdots 0} $.
In particolare, l'azione di questa operazione può essere simulata dalla trasformazione unitaria $U $ che agisce sullo stato all-zero come

$ $ \begin{align} U\ket {0... 0} & = \ket{\psi} \\ \\ & = \frac{\ Sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\sqrt{\ Sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.
\end{align} $ $

## <a name="input"></a>Input

### <a name="tolerance--double"></a>tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)

Tolleranza di approssimazione da utilizzare durante la preparazione dello stato specificato.


### <a name="coefficients--complexpolar"></a>coefficienti: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]

Matrice di un massimo di $2 ^ n $ coefficienti complessi, rappresentati dal valore assoluto e dalla fase $ (r_j, t_j) $. Il coefficiente $j $ TH indicizza lo stato del numero $ \ket{j} $ codificato in formato little-endian.


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Qubit registra il numero di codifica in formato little-endian. Questo dovrebbe essere inizializzato nello stato di base di calcolo $ \ket{0...0} $.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

I coefficienti di input negativi $r _j < $0 verranno trattati come se fossero positivi con il valore $ | r_j | $. `coefficients` verrà riempito con gli elementi $ (r_j, t_j) = (0,0, 0,0) $ se sono specificati meno di $2 ^ n $.

## <a name="references"></a>Riferimenti

- Sintesi dei circuiti logici Quantum Simone V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176
---
uid: Microsoft.Quantum.Intrinsic.M
title: Operazione M
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: M
qsharp.summary: >-
  Performs a measurement of a single qubit in the Pauli $Z$ basis.

  The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. \end{align}
ms.openlocfilehash: 8d4b120385bfc7086a7cb0e3f77034c760d78d92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720939"
---
# <a name="m-operation"></a>Operazione M

Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)

Pacchetto [](https://nuget.org/packages/)


Esegue una misurazione di un singolo qubit in Pauli $Z $ base.

Il risultato dell'output viene fornito da Distribution \begin{align} \Pr (\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}.
\end{align}

```qsharp
operation M (qubit : Qubit) : Result
```


## <a name="input"></a>Input

### <a name="qubit--qubit"></a>Qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit da misurare.



## <a name="output--__invalidresult__"></a>Output: __non <Result> valido__

`Zero` Se viene osservato il autovalore $ + $1 e `One` se viene osservato il autovalore $-$1.

## <a name="remarks"></a>Commenti

Equivalente a:

```qsharp
Measure([PauliZ], [qubit]);
```
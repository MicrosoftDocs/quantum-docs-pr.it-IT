---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: Operazione PrepareUniformSuperposition
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: dc9d4ce1638b397748cafaa757241ce78633c67c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854309"
---
# <a name="prepareuniformsuperposition-operation"></a>Operazione PrepareUniformSuperposition

Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Crea una superposizione uniforme sugli Stati che codificano da 0 a `nIndices - 1` .

Questo Unity $U $ crea una superposizione uniforme su tutti gli Stati numerici $0 $ $M-$1, dato lo stato di input $ \ket{0\cdots 0} $. In altre parole, $ $ \begin{align} U\ket {0} = \frac {1} {\sqrt{m}}\ Sum_ {j = 0} ^ {M-1} \ket{j}.
\end{align} $ $.

```qsharp
operation PrepareUniformSuperposition (nIndices : Int, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Input

### <a name="nindices--int"></a>nIndices: [int](xref:microsoft.quantum.lang-ref.int)

Il numero desiderato di stati $M $ nella superposizione uniforme.


### <a name="indexregister--littleendian"></a>indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registro qubit che archivia gli Stati dei numeri nel `LittleEndian` formato.
Il registro deve essere in grado di archiviare il numero $M-$1 e si presuppone che venga inizializzato nello stato $ \ket{0\cdots 0} $.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Esempio

Nell'esempio seguente viene preparato lo stato $ \frac {1} {\sqrt {6} } \ Sum_ {j = 0} ^ {5} \ket{j} $ su $3 $ qubits.

```qsharp
let nIndices = 6;
using(indexRegister = Qubit[3]) {
    PrepareUniformSuperposition(nIndices, LittleEndian(indexRegister));
    // ...
}
```

## <a name="remarks"></a>Commenti

L'operazione è adjointable, ma richiede che `indexRegister` si trovi in una superposizione uniforme rispetto ai primi `nIndices` Stati di base in questo caso.
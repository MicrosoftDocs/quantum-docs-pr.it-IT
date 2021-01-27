---
uid: Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance
title: Operazione AssertQubitIsInStateWithinTolerance
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitIsInStateWithinTolerance
qsharp.summary: >-
  Asserts that a qubit in the expected state.

  `expected` represents a complex vector, $\ket{\psi} = \begin{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}$. The first element of the tuples representing each of $a$, $b$ is the real part of the complex number, while the second one is the imaginary part. The last argument defines the tolerance with which assertion is made.
ms.openlocfilehash: b40c5c4f731190c8c0d00d33718680e5448bf767
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829793"
---
# <a name="assertqubitisinstatewithintolerance-operation"></a>Operazione AssertQubitIsInStateWithinTolerance

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Asserisce che un qubit nello stato previsto.

`expected` rappresenta un vettore complesso, $ \ket{\psi} = \begin{Bmatrix}a & b\end {Bmatrix} ^ {\mathrm{T}} $.
Il primo elemento delle tuple che rappresenta ogni $a $, $b $ è la parte reale del numero complesso, mentre la seconda è la parte immaginaria.
L'ultimo argomento definisce la tolleranza con cui viene eseguita l'asserzione.

```qsharp
operation AssertQubitIsInStateWithinTolerance (expected : (Microsoft.Quantum.Math.Complex, Microsoft.Quantum.Math.Complex), register : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a>Input

### <a name="expected--complexcomplex"></a>previsto: ([complesso](xref:Microsoft.Quantum.Math.Complex),[complesso](xref:Microsoft.Quantum.Math.Complex))

Sono previste ampiezze complesse per $ \ket {0} $ e $ \ket {1} $, rispettivamente.


### <a name="register--qubit"></a>registra: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit il cui stato deve essere dichiarato. Si presuppone che questo qubit sia separabile da altri qubits allocati e non sia stato impigliato.


### <a name="tolerance--double"></a>tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)

Tolleranza additiva in base alla quale le ampiezze effettive possono deviare rispetto a quanto previsto.
Per informazioni dettagliate, vedere la sezione Osservazioni di seguito.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Esempio

```qsharp
using (qubits = Qubit[2]) {
    // Both qubits are initialized as |0〉: a=(1 + 0*i), b=(0 + 0*i)
    AssertQubitIsInStateWithinTolerance((Complex(1., 0.), Complex(0., 0.)), qubits[0], 1e-5);
    AssertQubitIsInStateWithinTolerance((Complex(1., 0.), Complex(0., 0.)), qubits[1], 1e-5);
    Y(qubits[1]);
    // Y |0〉 = i |1〉: a=(0 + 0*i), b=(0 + 1*i)
    AssertQubitIsInStateWithinTolerance((Complex(0., 0.), Complex(0., 1.)), qubits[1], 1e-5);
}
```

## <a name="remarks"></a>Commenti

Il codice di Mathematica seguente può essere usato per verificare le espressioni per mi, MX, My, MZ:

```mathematica
{Id, X, Y, Z} = Table[PauliMatrix[k], {k, 0, 3}];
st = {{ reA + I imA }, { reB + I imB} };
M = st . ConjugateTranspose[st];
mx = Tr[M.X] // ComplexExpand;
my = Tr[M.Y] // ComplexExpand;
mz = Tr[M.Z] // ComplexExpand;
mi = Tr[M.Id] // ComplexExpand;
2 m == Id mi + X mx + Z mz + Y my // ComplexExpand // Simplify
```

La tolleranza è la $L \_ {\infty} $ distance tra il vettore reale 3 dimensionale (x ₂, x ₃, x ₄) definito da $ \langle\psi | \psi\rangle = x \_ 1 I + x \_ 2 x + x \_ 3 Y + x \_ 4 Z $ e Real Vector (y ₂, y ₃, y ₄) definito da ρ = y ₁ I + y ₂ x + y ₃ Y + y ₄ Z dove ρ è la matrice di densità corrispondente allo stato del registro.
Ciò si verifica solo se si presuppone che TR (ρ) e TR (| ψ ⟩ ⟨ ψ |) siano entrambi 1 (ad esempio x ₁ = 1/2, y ₁ = 1/2).
In caso contrario, la funzione dichiara che la distanza l ∞ tra (x ₂-x ₁, x ₃-x ₁, x ₄-x ₁, x ₄ + x ₁) e (y ₂-y ₁, y ₃-y ₁, y ₄-y ₁, y ₄ + y ₁) è inferiore al parametro tolerance.
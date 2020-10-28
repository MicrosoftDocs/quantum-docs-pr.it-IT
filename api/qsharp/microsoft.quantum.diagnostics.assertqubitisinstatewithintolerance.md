---
uid: Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance
title: Operazione AssertQubitIsInStateWithinTolerance
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitIsInStateWithinTolerance
qsharp.summary: >-
  Asserts that a qubit in the expected state.

  `expected` represents a complex vector, $\ket{\psi} = \begin{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}$. The first element of the tuples representing each of $a$, $b$ is the real part of the complex number, while the second one is the imaginary part. The last argument defines the tolerance with which assertion is made.
ms.openlocfilehash: 5d34bdac53870326dacb5a11c27c857793c3f420
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712939"
---
# <a name="assertqubitisinstatewithintolerance-operation"></a>Operazione AssertQubitIsInStateWithinTolerance

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto [](https://nuget.org/packages/)


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
---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced
title: Operazione AssertOperationsEqualReferenced
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualReferenced
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers. Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated. This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.
ms.openlocfilehash: 045f00a720e9f4d2e6993c66ace44a81e192ff30
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853475"
---
# <a name="assertoperationsequalreferenced-operation"></a>Operazione AssertOperationsEqualReferenced

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Date due operazioni, asserisce che agiscono in modo identico per tutti gli Stati di input.

Questa asserzione viene implementata usando il isomorfismo Choi-Jamiołkowski per ridurre l'asserzione a una delle asserzioni di stato qubit su due registri coinvolti.
Pertanto, per questa operazione è necessaria una sola chiamata a ogni operazione sottoposta a test, ma è necessario allocare un numero di qubits pari al doppio.
Questa asserzione può essere usata per garantire, ad esempio, che una versione ottimizzata di un'operazione agisca in modo identico alla relativa implementazione ingenua o che un'operazione che agisce su un intervallo di input non quantistici accetti i casi noti.

```qsharp
operation AssertOperationsEqualReferenced (nQubits : Int, actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Input

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Numero di qubits da passare a ogni operazione.


### <a name="actual--qubit--unit"></a>effettivo: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unità](xref:microsoft.quantum.lang-ref.unit)> 

Operazione da verificare.


### <a name="expected--qubit--unit--is-adj"></a>previsto: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ

Operazione che definisce il comportamento previsto per l'operazione sottoposta a test.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Questa operazione richiede che l'operazione di modellazione del comportamento previsto sia adjointable, in modo che l'inverso possa essere eseguito solo sul Registro di destinazione.
Formalmente, è possibile specificare un'operazione di trasposizione, che consente di attenuare questo requisito, ma l'operazione di trasposizione non è in genere fisicamente realizzabile per le operazioni Quantum arbitrarie e pertanto non è inclusa in questa opzione.
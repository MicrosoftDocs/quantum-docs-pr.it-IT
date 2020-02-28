---
title: 'Uso della libreria Microsoft Q # Numerics'
description: Informazioni sui tipi e le operazioni disponibili nella libreria Quantum Numerics di Microsoft.
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.usage
ms.openlocfilehash: ad9f529efd06fdf13bab4467b091aafacf1d5b09
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907257"
---
# <a name="using-the-numerics-library"></a>Uso della libreria Numerics

## <a name="overview"></a>Panoramica

La libreria Numerics è costituita da tre componenti

1. **Aritmetica di base di interi** con comparatori e comparatori Integer
1. **Funzionalità Integer di alto livello** basata sulle funzionalità di base. include moltiplicazione, divisione, inversione e così via.  per gli interi con segno e senza segno.
1. **Funzionalità aritmetica a virgola** fissa con inizializzazione a virgola fissa, addizione, moltiplicazione, reciproca, valutazione polinomiale e misurazione.

È possibile accedere a tutti questi componenti utilizzando una singola istruzione `open`:
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a>Tipi

La libreria Numerics supporta i tipi seguenti

1. **`LittleEndian`** : una matrice qubit `qArr : Qubit[]` che rappresenta un Integer in cui `qArr[0]` denota il bit meno significativo.
1. **`SignedLittleEndian`** : uguale `LittleEndian` con la differenza che rappresenta un intero con segno archiviato nel complemento a due.
1. **`FixedPoint`** : rappresenta un numero reale costituito da una matrice qubit `qArr2 : Qubit[]` e da una posizione del punto binario `pos`, che conta il numero di cifre binarie a sinistra del punto binario. `qArr2` viene archiviato allo stesso modo di `SignedLittleEndian`.

## <a name="operations"></a>Operazioni

Per ognuno dei tre tipi precedenti, è disponibile un'ampia gamma di operazioni:

1. **`LittleEndian`**
    - Addizione
    - Confronto
    - Moltiplicazione
    - Quadratura
    - Divisione (con resto)

1. **`SignedLittleEndian`**
    - Addizione
    - Confronto
    - Complemento di Inversion modulo 2
    - Moltiplicazione
    - Quadratura

1. **`FixedPoint`**
    - Preparazione/inizializzazione di valori classici
    - Addizione (costante classica o altro punto fisso Quantum)
    - Confronto
    - Moltiplicazione
    - Quadratura
    - Valutazione polinomiale con specializzazione per funzioni pari e dispari
    - Reciproco (1/x)
    - Misurazione (doppia classica)

Per ulteriori informazioni e documentazione dettagliata per ognuna di queste operazioni, vedere la documentazione di riferimento della libreria Q # in [docs.Microsoft.com](https://docs.microsoft.com/quantum)

## <a name="sample-integer-addition"></a>Esempio: aggiunta di numeri interi

Come esempio di base, si consideri l'operazione $ $ \ket x\ket y\mapsto \ket x\ket {x + y} $ $, ovvero un'operazione che accetta un integer n-qubit $x $ e un n-o (n + 1)-qubit registra $y $ come input, il secondo dei quali esegue il mapping alla somma $ (x + y) $. Si noti che la somma viene calcolata modulo $2 ^ n $ se $y $ viene archiviato in un registro $n $ bit.

Utilizzando Quantum Development Kit, è possibile applicare questa operazione come indicato di seguito:
```qsharp
operation TestMyAddition(xValue : Int, yValue : Int, n : Int) : Unit {
    using ((xQubits, yQubits) = (Qubit[n], Qubit[n]))
    {
        x = LittleEndian(xQubits); // define bit order
        y = LittleEndian(yQubits);
        
        ApplyXorInPlace(xValue, x); // initialize values
        ApplyXorInPlace(yValue, y);
        
        AddI(x, y); // perform addition x+y into y
        
        // ... (use the result)
    }
}
```

## <a name="sample-evaluating-smooth-functions"></a>Esempio: valutazione di funzioni Smooth

Per valutare le funzioni smussate, ad esempio $ \sin (x) $ in un computer Quantum, dove $x $ è un numero `FixedPoint` Quantum, la libreria Quantum Development Kit Numerics fornisce le operazioni `EvaluatePolynomialFxP` e `Evaluate[Even/Odd]PolynomialFxP`.

Il primo, `EvaluatePolynomialFxP`, consente di valutare un polinomio nel formato $ $ P (x) = a_0 + a_1x + a_2x ^ 2 + \cdots + a_dx ^ d, $ $ dove $d $ indica il *grado*. A tale scopo, sono necessari solo i coefficienti polinomiali `[a_0,..., a_d]` (di tipo `Double[]`), il `x : FixedPoint` di input e l'output `y : FixedPoint` (inizialmente zero):
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], x, y);
```
Il risultato, $P (x) = 1 + 2x $, verrà archiviato nel `yFxP`.

La seconda, la `EvaluateEvenPolynomialFxP`e la terza `EvaluateOddPolynomialFxP`sono specializzazioni per i casi di funzioni pari e dispari, rispettivamente. Ovvero, per una funzione uniforme/dispari $f (x) $ e $ $ P_ {even} (x) = a_0 + a_1 x ^ 2 + a_2 x ^ 4 + \cdots + a_d x ^ {2D}, $ $ $f (x) $ è approssimato bene $P _ {even} (x) $ o $P _ {Odd} (x): = x\cdot P_ {even} (x) $, rispettivamente.
In Q # questi due casi possono essere gestiti come indicato di seguito:
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], x, y);
```
che valuta $P _ {even} (x) = 1 + 2x ^ 2 $ e
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], x, y);
```
che valuta $P _ {Odd} (x) = x + 2x ^ 3 $.

## <a name="more-samples"></a>Altri esempi

Altri esempi sono disponibili nel [repository principale degli esempi](https://github.com/Microsoft/Quantum).

Per iniziare, clonare il repository e aprire la sottocartella `Numerics`:

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics
```

Quindi, `cd` in una delle cartelle di esempio ed eseguire l'esempio tramite

```bash
dotnet run
```

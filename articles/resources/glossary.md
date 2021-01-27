---
title: quantum computing glossal Description: un glossario dei termini, delle azioni e degli oggetti comuni usati in quantum computing.
autore: bradben ms. Author: v-benbra ms. Date: 9/1/2020 ms. Topic: Reference UID: Microsoft. Quantum. glossal no-loc:
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "\cdots"
- "bmatrix"
- "\ddots"
- "\equiv"
- "\sum"
- "\begin"
- "\end"
- "\sqrt"
- "\otimes"
- "{"
- "}"
- "\text"
- "\phi"
- "\kappa"
- "\psi"
- "\alpha"
- "\beta"
- "\gamma"
- "\delta"
- "\omega"
- "\bra"
- "\ket"
- "\boldone"
- "\\\\"
- "\\"
- "="
- "\frac"
- "\text"
- "\mapsto"
- "\dagger"
- "\to"
- "\begin{cases}"
- "\end{cases}"
- "\operatorname"
- "\braket"
- "\id"
- "\expect"
- "\defeq"
- "\variance"
- "\dd"
- "&"
- "\begin{align}"
- "\end{align}"
- "\Lambda"
- "\lambda"
- "\Omega"
- "\mathrm"
- "\left"
- "\right"
- "\qquad"
- "\times"
- "\big"
- "\langle"
- "\rangle"
- "\bigg"
- "\Big"
- "|"
- "\mathbb"
- "\vec"
- "\in"
- "\texttt"
- "\ne"
- "<"
- ">"
- "\leq"
- "\geq"
- "~~"
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- "\_"

---

# <a name="quantum-computing-glossary"></a>Glossario calcolo Quantum

## <a name="adjoint"></a>Adjoint

Trasposta complessa di un' [operazione](xref:microsoft.quantum.glossary#operation). Per le operazioni che implementano un operatore [unitario](xref:microsoft.quantum.glossary#unitary-operator) , l'elemento contiguo è l'inverso dell'operazione ed è indicato da un simbolo a pugni. Ad esempio, se l'operazione `U` rappresenta l'operatore unitario $ u $ , `Adjoint U` rappresenta $ u ^ \dagger $ . Per altre informazioni, vedere [applicazione functor](xref:microsoft.quantum.qsharp.functorapplication#functor-application).

## <a name="ancilla"></a>Ancilla

Un [qubit](xref:microsoft.quantum.glossary#qubit) che funge da memoria temporanea per un computer Quantum e viene allocato e deallocato in base alle esigenze.  Per ulteriori informazioni, vedere la pagina relativa a [più qubits](xref:microsoft.quantum.concepts.multiple-qubits).

## <a name="bell-state"></a>Stato Campanella

Uno dei quattro [](xref:microsoft.quantum.glossary#entanglement) [Stati Quantum](xref:microsoft.quantum.glossary#quantum-state) più specifici di due qubits. I quattro Stati sono definiti $ \ket { \beta _ { IJ } } = ( \mathbb { i } \otimes X ^ iz ^ j) ( \ket { 00 }  +  \ket { 11 } )/ \sqrt { 2 } $ . Uno stato di campana è anche noto come [coppia EPR](xref:microsoft.quantum.glossary#epr-pair).

## <a name="bloch-sphere"></a>Sfera Bloch

Rappresentazione grafica di uno [stato del quantum](xref:microsoft.quantum.glossary#quantum-state) a[qubit](xref:microsoft.quantum.glossary#qubit) singolo come punto in una sfera di unità tridimensionale. Per altre informazioni, vedere  [la pagina relativa alla visualizzazione di qubits e delle trasformazioni con la sfera Bloch](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).

## <a name="callable"></a>Callable

[Operazione](xref:microsoft.quantum.glossary#operation) o [funzione](xref:microsoft.quantum.glossary#function) nel [ Q# linguaggio](https://github.com/microsoft/qsharp-language/tree/main/Specifications/Language#q-language).
Per ulteriori informazioni, vedere [ Q# programmi](xref:microsoft.quantum.guide.programs)

## <a name="clifford-group"></a>Gruppo Clifford

Il set di operazioni che occupano il ottanti della [sfera Bloch](xref:microsoft.quantum.glossary#bloch-sphere) e le permutazioni degli effetti degli [operatori Pauli](xref:microsoft.quantum.glossary#pauli-operators). Sono incluse le operazioni [ $ X $ ](xref:Microsoft.Quantum.Intrinsic.X), [ $ Y $ ](xref:Microsoft.Quantum.Intrinsic.Y), [ $ Z $ ](xref:Microsoft.Quantum.Intrinsic.Z), [ $ H $ ](xref:Microsoft.Quantum.Intrinsic.H) e [ $ S $ ](xref:Microsoft.Quantum.Intrinsic.S).

## <a name="controlled"></a>Controllato

[Operazione](xref:microsoft.quantum.glossary#operation) Quantum che accetta uno o più [qubits](xref:microsoft.quantum.glossary#qubit) come abilitatori per l'operazione di destinazione. Per altre informazioni, vedere [applicazione functor](xref:microsoft.quantum.qsharp.functorapplication#functor-application).

## <a name="dirac-notation"></a>Notazione Dirac

Abbreviazione simbolica che semplifica la rappresentazione degli [Stati Quantum](xref:microsoft.quantum.glossary#quantum-state), detta anche notazione *bra-ket* .  La parte *Bra* rappresenta un vettore di riga, ad esempio $ \bra { a } = \begin{bmatrix} { _1 } & a { _2 } \end{bmatrix} $ e la parte *KET* rappresenta un vettore di colonna, $ \ket { b } = \begin{bmatrix} b { _1 } \\\\ b { _2 } \end{bmatrix} $ . Per ulteriori informazioni, vedere la [notazione Dirac](xref:microsoft.quantum.concepts.dirac).

## <a name="eigenvalue"></a>Autovalore

Fattore in base al quale la grandezza di un [autovettore](xref:microsoft.quantum.glossary#eigenvector) di una determinata trasformazione viene modificata dall'applicazione della trasformazione.  Data una matrice quadrata $ M $ e una autovettore $ v $ , quindi $ MV = CV $ , dove $ c $ è il autovalore e può essere un numero complesso di qualsiasi argomento. Per ulteriori informazioni, vedere [Advanced Matrix Concepts](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="eigenvector"></a>Autovettore

Vettore la cui direzione è invariata da una determinata trasformazione e la cui grandezza viene modificata da un fattore corrispondente a [autovalore](xref:microsoft.quantum.glossary#eigenvalue)del vettore. Data una matrice quadrata $ M $ e una autovalore $ c $ , quindi $ MV = CV $ , dove $ v $ è un autovettore della matrice e può essere un numero complesso di qualsiasi argomento. Per ulteriori informazioni, vedere [Advanced Matrix Concepts](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="entanglement"></a>Entanglement

Le particelle quantistiche, ad esempio [qubits](xref:microsoft.quantum.glossary#qubit), possono essere connesse o *aggrovigliate* in modo che non possano essere descritte indipendentemente l'una dall'altra. I risultati della misurazione sono correlati anche quando sono separati all'infinito. L'accoppiamento è essenziale per [misurare](xref:microsoft.quantum.glossary#measurement) lo [stato](xref:microsoft.quantum.glossary#quantum-state) di un qubit.  Per ulteriori informazioni, vedere [Advanced Matrix Concepts](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="epr-pair"></a>Coppia EPR

Uno dei quattro [Stati Quantum](xref:microsoft.quantum.glossary#quantum-state) più specifici di due [qubits](xref:microsoft.quantum.glossary#qubit). I quattro Stati sono definiti $ \ket { \beta _ { IJ } } = ( \mathbb { 1 } \otimes X ^ iz ^ j) ( \ket { 00 }  +  \ket { 11 } )/ \sqrt { 2 } $ . Una coppia EPR è nota anche come [stato di campana](xref:microsoft.quantum.glossary#bell-state)

## <a name="evolution"></a>Evoluzione

Modifica [dello stato del quantum](xref:microsoft.quantum.glossary#quantum-state) nel tempo. Per altre informazioni, vedere [matrici esponenziali](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials).

## <a name="function"></a>Funzione
Tipo di subroutine nel Q# linguaggio puramente deterministico. Mentre le funzioni vengono utilizzate all'interno degli algoritmi quantistici, non possono agire su [qubits](xref:microsoft.quantum.glossary#qubit) o sulle [operazioni](xref:microsoft.quantum.glossary#operation)di chiamata. Per ulteriori informazioni, vedere [ Q# programmi](xref:microsoft.quantum.guide.programs)

## <a name="gate"></a>Cancello

Termine legacy per determinate [operazioni](xref:microsoft.quantum.glossary#operation)Quantum intrinseche, in base al concetto di controlli di logica classici. Un [circuito quantico](xref:microsoft.quantum.glossary#quantum-circuit-diagram) è una rete di controlli, basati sul concetto simile di circuiti logici classici.

## <a name="global-phase"></a>Fase globale

Quando due [Stati](xref:microsoft.quantum.glossary#quantum-state) sono identici a un multiplo di un numero complesso $ e ^ { i \phi } $ , viene detto che differiscono per una fase globale. Diversamente dalle fasi locali, le fasi globali non possono essere osservate attraverso alcuna [misurazione](xref:microsoft.quantum.glossary#measurement). Per ulteriori informazioni, vedere [qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="hadamard"></a>Hadamard

L'operazione Hadamard (detta anche controllo o trasformazione Hadamard) agisce su un singolo [qubit](xref:microsoft.quantum.glossary#qubit) e lo inserisce in una [sovrapposizione](xref:microsoft.quantum.glossary#superposition) pari a $ \ket { 0 } $ o $ \ket { 1 } $ se il qubit è inizialmente nello $ \ket { } $ stato 0. In Q# questa operazione viene applicata dall' [`H`](xref:Microsoft.Quantum.Intrinsic.H) operazione predefinita.

## <a name="immutable"></a>Non modificabile

Variabile il cui valore non può essere modificato. Una variabile non modificabile in Q# viene creata usando la `let` parola chiave. Per dichiarare variabili che *possono* essere modificate, usare la parola chiave [mutable](xref:microsoft.quantum.glossary#immutable) per dichiarare e la `set` parola chiave per modificare il valore. 

## <a name="measurement"></a>Misura

Manipolazione di un [qubit](xref:microsoft.quantum.glossary#qubit) (o set di qubits) che restituisce il risultato di un'osservazione, ottenendo in effetti un bit classico. Per ulteriori informazioni, vedere [qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit).

## <a name="mutable"></a>Modificabile

Variabile il cui valore può essere modificato dopo la creazione. Una variabile modificabile in Q# viene dichiarata utilizzando la `mutable` parola chiave e modificata utilizzando la `set` parola chiave. Le variabili create con la `let` parola chiave non sono [modificabili](xref:microsoft.quantum.glossary#immutable) e il relativo valore non può essere modificato.

## <a name="namespace"></a>Spazio dei nomi

Etichetta per una raccolta di nomi correlati, ad esempio [operazioni](xref:microsoft.quantum.glossary#operation), [funzioni](xref:microsoft.quantum.glossary#function)e [tipi definiti dall'utente](xref:microsoft.quantum.glossary#user-defined-type). Ad esempio, lo spazio dei nomi [Microsoft. Quantum. preping](xref:Microsoft.Quantum.Preparation) etichetta tutti i simboli definiti nella libreria standard che consentono di preparare gli stati iniziali.

## <a name="operation"></a>Operazione

Unità di base del calcolo quantistico in Q# . È approssimativamente equivalente a una funzione in C, C++ o Python o a un metodo statico in C# o Java. Per ulteriori informazioni, vedere [ Q# programmi](xref:microsoft.quantum.guide.programs).

## <a name="oracle"></a>Oracle

Subroutine che fornisce informazioni dipendenti dai dati a un algoritmo Quantum in fase di esecuzione. In genere, l'obiettivo è quello di fornire una [superposizione](xref:microsoft.quantum.glossary#superposition) degli output corrispondenti agli input in posizione superposizionata. Per ulteriori informazioni, vedere [Oracles](xref:microsoft.quantum.libraries.data-structures#oracles).

## <a name="partial-application"></a>Applicazione parziale

Chiamata di una [funzione](xref:microsoft.quantum.glossary#function) o di un' [operazione](xref:microsoft.quantum.glossary#operation) senza tutti gli input necessari. Viene restituito un nuovo oggetto [chiamabile](xref:microsoft.quantum.glossary#callable) che necessita solo dei parametri mancanti (indicati da un carattere di sottolineatura) da fornire durante un'applicazione futura. Per ulteriori informazioni, vedere [applicazione parziale](xref:microsoft.quantum.qsharp.partialapplication).

## <a name="pauli-operators"></a>Operatori Pauli

Set di matrici di unità 3 2 x 2 note come `X` `Y` `Z` operazioni Quantum e. La matrice di identità, $ i $ , viene spesso inclusa anche nel set.  $I = \begin{bmatrix} 1 & 0 \\\\ 0 & 1 \end{bmatrix} $ , $ X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} $ , $ Y = \begin{bmatrix} 0 & -i \\\\ io & 0 \end{bmatrix} $ , $ Z = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix} $ .   Per altre informazioni, vedere [operazioni Single-qubit](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).

## <a name="quantum-circuit-diagram"></a>Diagramma del circuito quantico

Un metodo per rappresentare graficamente la [sequenza di attività di controllo](xref:microsoft.quantum.glossary#gate) per i semplici programmi Quantum, ad esempio 

![Diagramma di circuito di esempio](~/media/qpe.png). 

Per altre informazioni, vedere [Quantum Circuits](xref:microsoft.quantum.concepts.circuits).

## <a name="quantum-libraries"></a>Librerie Quantum

Raccolte di [operazioni](xref:microsoft.quantum.glossary#operation), [funzioni](xref:microsoft.quantum.glossary#function) e [tipi definiti dall'utente](xref:microsoft.quantum.glossary#user-defined-type) per la creazione di Q# programmi. La [libreria standard](xref:microsoft.quantum.libraries.standard.intro) viene installata per impostazione predefinita. Altre librerie disponibili sono la [libreria di chimica](xref:microsoft.quantum.chemistry.concepts.intro), la libreria [Numerics](xref:microsoft.quantum.numerics.intro) e la [libreria di Machine Learning](xref:microsoft.quantum.machine-learning.concepts.intro).

## <a name="quantum-state"></a>Stato quantum

Stato preciso di un sistema quantico isolato, da cui è possibile estrarre le probabilità di [misurazione](xref:microsoft.quantum.glossary#measurement) . Nel quantum computing, il simulatore Quantum usa queste informazioni per simulare il modo in cui qubits risponde alle operazioni. Per ulteriori informazioni, vedere [qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="qubit"></a>Qubit

Unità di base di informazioni sui quantum, analoga a un *bit* nell'elaborazione classica. Per ulteriori informazioni, vedere [qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="repeat-until-success"></a>Ripeti fino a-esito positivo

Un concetto spesso usato negli algoritmi quantistici che consiste nell'applicare ripetutamente un calcolo fino a quando non viene soddisfatta una determinata condizione. Quando la condizione non viene soddisfatta, spesso è necessaria una correzione prima di riprovare immettendo l'iterazione successiva. Per ulteriori informazioni, vedere la [ Q# Guida dell'utente](xref:microsoft.quantum.guide)

## <a name="standard-libraries"></a>Librerie standard

[Operazioni](xref:microsoft.quantum.glossary#operation), [funzioni](xref:microsoft.quantum.glossary#function) e [tipi definiti dall'utente](xref:microsoft.quantum.glossary#user-defined-type) installati insieme al Q# compilatore durante l'installazione. L'implementazione della libreria standard è indipendente rispetto ai computer di destinazione. Per altre informazioni, vedere [librerie standard](xref:microsoft.quantum.libraries.standard.intro).

## <a name="superposition"></a>Sovrapposizione

Il concetto di quantum computing che un [qubit](xref:microsoft.quantum.glossary#qubit) è una combinazione lineare di due Stati, $ \ket { 0 } $ e $ \ket { 1 } $ , fino a quando non viene [misurato](xref:microsoft.quantum.glossary#measurement).  Per ulteriori informazioni, vedere informazioni sul [quantum computing](xref:microsoft.quantum.overview.understanding).

## <a name="target-machine"></a>Computer di destinazione

Destinazione di compilazione che abbassa un programma Quantum astratto per l'hardware o la simulazione. Questo include in genere riscritture per molti scopi, tra cui la sostituzione del Gate, la codifica per la correzione degli errori, il layout geometrico e altro. Per altre informazioni, vedere [Quantum Simulators and host Applications](xref:microsoft.quantum.machines).

## <a name="teleportation"></a>Teletrasporto

Metodo per rigenerare i dati, o lo [stato del quantum](xref:microsoft.quantum.glossary#quantum-state), di [un qubit](xref:microsoft.quantum.glossary#qubit) da una posizione a un'altra senza spostamento fisico del qubit, mediante l'uso di [nodi](xref:microsoft.quantum.glossary#entanglement) e [misurazioni](xref:microsoft.quantum.glossary#measurement).  Per altre informazioni, vedere [Quantum Circuits](xref:microsoft.quantum.concepts.circuits) e il rispettivo Kata in [Quantum Katas](xref:microsoft.quantum.overview.katas).

## <a name="tuple"></a>Tupla

Raccolta di valori delimitati da virgole che funge da singolo valore. Il *tipo* di una tupla è definito dai tipi di valori in esso contenuti. In Q# le tuple non sono [modificabili](xref:microsoft.quantum.glossary#immutable) e possono essere annidate, contengono matrici o utilizzate in una matrice. Per ulteriori informazioni, vedere [Tuple](xref:microsoft.quantum.qsharp.valueliterals#tuple-literals).

## <a name="unitary-operator"></a>Operatore unitario

Operatore il cui inverso è uguale al relativo [contiguo](xref:microsoft.quantum.glossary#adjoint), ad esempio $ UU ^ { \dagger } = \id $ .

## <a name="user-defined-type"></a>Tipo definito dall'utente

Tipo personalizzato che può contenere uno o più elementi denominati o anonimi. Per altre informazioni, vedere [dichiarazioni di tipo] Microsoft. Quantum. qsharp. typedeclarations # Type-Declarations).

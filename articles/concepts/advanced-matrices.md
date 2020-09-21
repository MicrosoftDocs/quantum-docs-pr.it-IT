---
Titolo: Advanced Matrix Concepts Description: informazioni sugli esponenziali autovettori, autovalori e matrici, gli strumenti fondamentali usati per descrivere e simulare gli algoritmi Quantum.
autore: QuantumWriter UID: Microsoft. Quantum. Concepts. Matrix-Advanced MS. Author: v-benbra ms. Date: 12/11/2017 ms. Topic: article no-loc:
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "$$$"
- "$$$"
- "$$$"
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
# <a name="advanced-matrix-concepts"></a>Concetti avanzati della matrice #

Si estenderà ora la manipolazione delle matrici agli [*autovalori, autovettori*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) ed [*esponenziali*](https://en.wikipedia.org/wiki/Matrix_exponential) , che costituiscono un insieme fondamentale di strumenti necessari per descrivere e implementare gli algoritmi Quantum.

## <a name="eigenvalues-and-eigenvectors"></a>Autovalori e autovettori ##

Let $ M è $ una matrice quadrata e $ v è $ un vettore che non è il vettore di tutti gli zeri (ovvero, il vettore con tutte le voci uguale a $ 0 $ ).

Si dice che $ v $ è un [*autovettore*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) di  $ M $ se $ MV = CV $ per un numero $ c $ . Si dice che $ c $ è il [*autovalore*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) corrispondente a autovettore $ v $ . In generale, una matrice $ M $ può trasformare un vettore in qualsiasi altro vettore, ma un autovettore è speciale perché viene lasciato invariato, ad eccezione del fatto che viene moltiplicato per un numero. Si noti che se $ v $ è un autovettore con autovalore $ c $ , $ AV $ è anche un autovettore (per qualsiasi valore diverso da zero $ a $ ) con lo stesso autovalore.

Per la matrice di identità, ad esempio, ogni vector $ v $ è un autovettore con autovalore $ 1 $ .

Per un altro esempio, si consideri una [*matrice diagonale*](https://en.wikipedia.org/wiki/Diagonal_matrix) $ D $ che ha solo voci non zero sulla diagonale:

$$
\begin{bmatrix}
d_1 & 0 0 0 & \\\\ & d_2 & 0 \\\\ 0 & 0 & D_3 \end{bmatrix} .
$$

Vettori

$$\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix} , \begin{bmatrix} 0 \\\\ 1 \\\\ 0 \end{bmatrix} e \begin{bmatrix} 0 \\\\ 0 \\\\ 1\end{bmatrix}$$

sono autovettori di questa matrice con autovalori  $ D_1 $ , $ D_2 $ e $ D_3 $ rispettivamente. Se $ D_1 $ , $ D_2 $ e $ D_3 $ sono numeri distinti, questi vettori (e i relativi multipli) sono gli unici autovettori della matrice $ d $ . In generale, per una matrice diagonale è facile leggere gli autovalori e autovettori. Gli autovalori sono tutti i numeri visualizzati sulla diagonale e i rispettivi autovettori sono i vettori di unità con una voce uguale a $ 1 $ e le voci rimanenti uguale a $ 0 $ .

Si noti che nell'esempio precedente il autovettori di $ D $ costituisce una base per $ i $ vettori tridimensionali. Una base è costituita da un set di vettori in modo che qualsiasi vettore possa essere scritto come una combinazione lineare. In modo più esplicito, $ V_1 $ , $ v_2 $ e $ v_3 $ costituiscono una base se qualsiasi vettore $ v $ può essere scritto come $ v = A_1 v_1 + a_2 v_2 + A_3 v_3 $ per alcuni numeri $ A_1 $ , $ A_2 $ e $ A_3 $ .

Si tenga presente che una matrice Hermitiane (detta anche self-adiacentt) è una matrice quadrata complessa uguale alla relativa trasposizione di coniugata complessa, mentre una matrice unitaria è una matrice quadrata complessa il cui inverso è uguale alla trasposizione di un coniugato complesso o contiguo.
Per le matrici Hermitiane e unitarie, che sono essenzialmente le uniche matrici rilevate nel quantum computing, è presente un risultato generale noto come [*teorema spettrale*](https://en.wikipedia.org/wiki/Spectral_theorem), che asserisce quanto segue: per qualsiasi Hermitiane o matrice unitaria $ m $ , esiste un u unitario $ $ che $ m u = ^ \dagger D u $ per una matrice diagonale $ d $ . Inoltre, le voci diagonali di $ D $ saranno gli autovalori di $ M $ .

È già noto come calcolare gli autovalori e la autovettori di una matrice diagonale $ D $ . Con questo teorema sappiamo che se $ v $ è un autovettore di $ D $ con autovalore $ c $ , ad esempio $ DV = CV $ , $ U ^ \dagger v $ sarà un autovettore di $ M $ con autovalore $ c $ . Questo perché

$$M (U ^ \dagger v) = u ^ \dagger d u (u ^ \dagger v) = U ^ \dagger d (u u ^ \dagger ) v = u ^ \dagger d v = c u ^ \dagger v.$$

## <a name="matrix-exponentials"></a>Esponenziali matrice
Una [*matrice esponenziale*](https://en.wikipedia.org/wiki/Matrix_exponential) può anche essere definita esattamente Analogamente alla funzione esponenziale.  L'esponenziale matrice di una matrice $ a $ può essere espresso come

$$
e ^ A = \boldone + a + \frac { a ^ 2 } { 2! } + \frac { A ^ 3 } { 3!}+\cdots
$$

Questo è importante perché l'evoluzione del tempo di Quantum Mechanical è descritta da una matrice unitaria nel formato $ e ^ { IB } $ per Hermitiane Matrix $ B $ .  Per questo motivo, l'esecuzione esponenziale della matrice è una parte fondamentale dell'elaborazione quantistica e, di conseguenza, Q# offre routine intrinseche per la descrizione di queste operazioni.
Ci sono molti modi per calcolare una matrice esponenziale in un computer classico e, in generale, l'approssimazione di un esponenziale tale esponenziale è irta di rischi.  Vedere [*Cleve Moler e Charles Van Loan. "Diciannove modi dubbi per calcolare l'esponenziale di una matrice". SIAM Review 20,4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) per ulteriori informazioni sui problemi correlati.

Il modo più semplice per comprendere come calcolare l'esponenziale di una matrice è tramite gli autovalori e autovettori di tale matrice.  In particolare, il teorema spettrale illustrato sopra dice che per ogni Hermitiane o matrice unitaria esiste una matrice $ $ unitaria $ u $ e una matrice diagonale $ D $ tale che $ a = u ^ \dagger D u $ .  A causa delle proprietà di unitarietà è presente $ un ^ 2 = u ^ \dagger d ^ 2 u $ e allo stesso modo per qualsiasi Power $ p $ $ A ^ p = u ^ \dagger D ^ p u $ .  Se si sostituisce questa operazione nella definizione dell'operatore dell'operatore esponenziale, si ottiene:

$$
e ^ A = U ^ \dagger \left ( \boldone + d + \frac { d ^ 2 } { 2! } + \cdots \right ) U = u ^ \dagger \begin{bmatrix} \exp (D_ { 11 } ) & 0 & \cdots & 0 \\\\ 0 & \exp (D_ { 22 } ) & \cdots & 0 \\\\ \vdots & \vdots & \ddots & \vdots \\\\ 0 & 0 & \cdots & \exp (D_ { nn } ) \end{bmatrix} U.$$

In altre parole, se si trasforma in eigenbasis della matrice a, $ il $ calcolo dell'esponenziale della matrice equivale a calcolare l'esponenziale comune degli autovalori della matrice.  Poiché il numero di operazioni in quantum computing comporta l'esecuzione di esponenziali matrice, questo espediente di trasformazione nel eigenbasis di una matrice per semplificare l'esecuzione dell'operatore esponenziale viene visualizzato spesso ed è la base per molti algoritmi quantistici, ad esempio i metodi di simulazione Quantum di tipo Trotter-Suzuki descritti più avanti in questa guida.

Un'altra proprietà utile è se $ b $ è sia Unity che hermitiane, ad esempio $ b = b ^ { -1 } = b ^ \dagger $ then $ b ^ 2 = \boldone $ . Applicando questa regola all'espansione precedente della matrice esponenziale e raggruppando i $ \boldone $ $ termini e B $ insieme, è possibile vedere che per qualsiasi valore reale $ x $ l'identità

$$e ^ { iBx } = \boldone \cos (x) + iB\sin (x)$$


tiene. Questo espediente è particolarmente utile in quanto consente di ragionare sulle azioni esponenziali della matrice, anche se la dimensione di $ b $ è esponenzialmente grande, per il caso speciale quando $ B $ è sia unitario che Hermitiane.

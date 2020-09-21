---
title: vettori e matrici in quantum computing Description: informazioni di base sull'uso di vettori e matrici.
autore: QuantumWriter UID: Microsoft. Quantum. Concepts. vectors ms. Author: v-benbra ms. Date: 12/11/2017 ms. Topic: article no-loc:
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

# <a name="vectors-and-matrices"></a>Vettori e matrici

Una certa familiarità con i vettori e le matrici è essenziale per comprendere il quantum computing. Viene fornita una breve introduzione e i lettori interessati sono consigliati per leggere un riferimento standard sull'algebra lineare, ad esempio *Strang, G. (1993). Introduzione all'algebra lineare (vol. 3). Wellesley, MA: Wellesley-Cambridge Press* o un riferimento online, ad esempio [algebra lineare](http://joshua.smcvt.edu/linearalgebra/).

Una colonna Vector (o semplicemente [*vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $ v $ della dimensione (o size) $ n $ è una raccolta di $ n $ numeri complessi $ (V_1, v_2, \ldots, v_n) $ disposti come colonna:

$$v =\begin{bmatrix}
v_1\\\\
v_2\\\\
\vdots\\\\
v_n \end{bmatrix}$$

La norma di un vettore $ v $ è definita come $ \sqrt { \sum \_ i | v \_ i | ^ 2 } $ . Un vettore viene detto unità Norm (oppure in alternativa viene definito [*vettore di unità*](https://en.wikipedia.org/wiki/Unit_vector)) se la norma è $ 1 $ . Il [*contiguo di un vettore*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ v $ è indicato come $ v ^ \dagger $ e viene definito come il vettore di riga seguente, dove $ \* $ indica il coniugato complesso,

$$\begin{bmatrix}V_1 \\\\ \vdots \\\\ v_n \end{bmatrix} ^ \dagger = \begin{bmatrix} V_1 ^ * & \cdots & v_n ^ *\end{bmatrix}$$

Il modo più comune per moltiplicare due vettori è il [*prodotto interno*](https://en.wikipedia.org/wiki/Inner_product_space), noto anche come prodotto a punti.  Il prodotto interno fornisce la proiezione di un vettore su un altro e non è utile per descrivere come esprimere un vettore come una somma di altri vettori più semplici.  Il prodotto interno tra $ u $ e $ v $ , indica $ \left \langle u, v \right \rangle $ è definito come

$$
\langleu, v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } V_1 + \cdots + u \_ n ^ { \* } v \_ n.
$$

Questa notazione consente inoltre la scrittura della norma di un vettore $ v $ come $ \sqrt { \langle v, v \rangle } $ .

È possibile moltiplicare un vettore con un numero $ c $ per formare un nuovo vettore le cui voci vengono moltiplicate per $ c $ . È anche possibile aggiungere due vettori $ u $ e $ v $ per formare un nuovo vettore le cui voci sono la somma delle voci di $ u $ e $ v $ . Queste operazioni sono illustrate di seguito:

$$\mathrm{Se } ~ u=\begin{bmatrix}
u_1\\\\
u_2\\\\
\vdots\\\\
u_n \end{bmatrix} ~ \mathrm { e}~
v =\begin{bmatrix}
    v_1\\\\
    v_2\\\\
    \vdots\\\\
    v_n \end{bmatrix} , ~ \mathrm { quindi}~
Au + BV =\begin{bmatrix}
au_1 + bv_1\\\\
au_2 + bv_2\\\\
\vdots\\\\
au_n + bv_n \end{bmatrix} .
$$

Una [*matrice*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) di dimensioni $ m \times n $ è una raccolta di $ $ numeri complessi Mn disposti in $ m $ righe e $ n $ colonne, come mostrato di seguito:

$$M = 
\begin{bmatrix}
M_ { 11 } ~~ m_ { 12 } ~~ \cdots ~~ m_ { 1N}\\\\
M_ { 21 } ~~ m_ { 22 } ~~ \cdots ~~ m_ { 2n}\\\\
\ddots\\\\
M_ { M1 } ~~ m_ { m2 } ~~ \cdots ~~ m_ { MN}\\\\
\end{bmatrix}.$$

Si noti che un vettore della dimensione $ n $ è semplicemente una matrice di dimensioni $ n \times 1 $ . Come per i vettori, è possibile moltiplicare una matrice con un numero $ c $ per ottenere una nuova matrice in cui ogni voce viene moltiplicata con $ c ed è $ possibile aggiungere due matrici con le stesse dimensioni per produrre una nuova matrice le cui voci sono la somma delle rispettive voci delle due matrici. 

## <a name="matrix-multiplication-and-tensor-products"></a>Moltiplicazione di matrici e prodotti tensori

È anche possibile moltiplicare due matrici $ m $ della dimensione $ m \times n $ e $ n $ della dimensione $ n \times p $ per ottenere una nuova matrice $ p $ della dimensione $ m \times p $ come segue:

\begin{align}
&\begin{bmatrix}
    M_ { 11 } ~~ m_ { 12 } ~~ \cdots ~~ m_ { 1N}\\\\
    M_ { 21 } ~~ m_ { 22 } ~~ \cdots ~~ m_ { 2n}\\\\
    \ddots\\\\
    M_ { M1 } ~~ m_ { m2 } ~~ \cdots ~~ m_ { MN}
\end{bmatrix}
\begin{bmatrix}
N_ { 11 } ~~ N_ { 12 } ~~ \cdots ~~ N_ { 1P}\\\\
N_ { 21 } ~~ N_ { 22 } ~~ \cdots ~~ N_ { 2P}\\\\
\ddots\\\\
N_ { N1 } ~~ N_ { N2 } ~~ \cdots ~~ N_ { NP}
\end{bmatrix}=\begin{bmatrix}
P_ { 11 } ~~ P_ { 12 } ~~ \cdots ~~ P_ { 1P}\\\\
P_ { 21 } ~~ P_ { 22 } ~~ \cdots ~~ P_ { 2P}\\\\
\ddots\\\\
P_ { M1 } ~~ P_ { m2 } ~~ \cdots ~~ P_ { MP}
\end{bmatrix}
\end{align}

dove le voci di $ P $ sono $ P_ { ik } = \sum _j M_ { IJ } N_ { JK } $ . La voce P_ 11, ad esempio, $ { } $ è il prodotto interno della prima riga di $ M $ con la prima colonna di $ N $ . Si noti che poiché un vettore è semplicemente un caso speciale di una matrice, questa definizione si estende alla moltiplicazione dei vettori di matrici. 

Tutte le matrici considerate saranno matrici quadre, in cui il numero di righe e colonne è uguale, o vettori, che corrisponde a $ una sola $ colonna. Una matrice quadrata speciale è la [*matrice di identità*](https://en.wikipedia.org/wiki/Identity_matrix), identificata $ \boldone $ , che include tutti i relativi elementi diagonali pari a $ 1 $ e gli elementi rimanenti uguale a $ 0 $ :

$$\boldone=\begin{bmatrix}
1 ~~ 0 ~~ \cdots ~~ 0\\\\
0 ~~ 1 ~~ \cdots ~~ 0\\\\
~~ \ddots\\\\
0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix} .$$

Per una matrice quadrata $ a $ , si dice che la matrice $ B $ è la relativa [*inversa*](https://en.wikipedia.org/wiki/Invertible_matrix) se $ AB = BA = \boldone $ . L'inverso di una matrice non deve esistere, ma quando esiste è univoco e viene indicato come $ ^ { -1 } $ . 

Per qualsiasi matrice $ m $ , la trasportazione contigua o coniugata di $ m $ è una matrice $ N $ tale che $ N_ { IJ } = m_ { Ji } ^ \* $ . Il contiguo di $ m $ è in genere indicato $ m ^ \dagger $ . Si dice che una matrice $ u $ è [*unitaria*](https://en.wikipedia.org/wiki/Unitary_matrix) se $ UU ^ \dagger = u ^ \dagger u = \boldone $ o equivalente, $ u ^ { -1 } = u ^ \dagger $ .  Probabilmente la proprietà più importante delle matrici unitarie è che conservano la norma di un vettore.  Questo problema si verifica perché 

$$\langlev, v ^ v v ^ \rangle = \dagger = \dagger u ^ { -1 } u v v = ^ \dagger u ^ u v u v \dagger = \langle , u v \rangle .$$  

Una matrice $ m $ è detta [*Hermitiane*](https://en.wikipedia.org/wiki/Hermitian_matrix) se $ m = m ^ \dagger $ .

Infine, il [*prodotto tensore*](https://en.wikipedia.org/wiki/Tensor_product) (o prodotto Kronecker) di due matrici $ m $ di dimensione $ m \times n $ e $ n $ di dimensioni $ p \times q $ è una matrice più grande $ p = M \otimes n $ di dimensioni $ MP \times NQ $ ed è ottenuta da $ m $ e $ n $ come indicato di seguito:

\begin{align}
    M \otimes N &=
    \begin{bmatrix}
        M_ { 11 } ~~ \cdots ~~ m_ { 1N }\\\\
        \ddots\\\\
        M_ { M1 } ~~ \cdots ~~ m_ { MN  }
    \end{bmatrix}
    \otimes
    \begin{bmatrix}
        N_ { 11 } ~~ \cdots ~~ N_ { 1Q  }\\\\
        \ddots\\\\
        N_ { P1 } ~~ \cdots ~~ N_ { PQ}
    \end{bmatrix}\\\\
    &=
    \begin{bmatrix}
        M_ { 11 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { PQ } \end{bmatrix} ~~ \cdots  ~~ 
        M_ { 1N } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { PQ }  \end{bmatrix}\\\\
        \ddots\\\\
        M_ { M1 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { PQ } \end{bmatrix} ~~ \cdots  ~~ 
        M_ { MN } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { PQ }  \end{bmatrix}
    \end{bmatrix}.
\end{align}

Si tratta di una dimostrazione migliore con alcuni esempi:

$$
    \begin{bmatrix}
        a \\\\ b \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}=
    \begin{bmatrix}
        \begin{bmatrix}c \\\\ d \\\\ e\end{bmatrix}
        \\\\[1.5 em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}
    \end{bmatrix}
    =\begin{bmatrix}c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\\end{bmatrix}
$$

e

$$
    \begin{bmatrix}
        a \ b \\\\ c \ d \end{bmatrix}
    \otimes 
    \begin{bmatrix}
        e \ f \\\\ g \ h \end{bmatrix}
     =
    \begin{bmatrix}
    un\begin{bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    b\begin{bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    \\\\[1em] c\begin{bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    d\begin{bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    \end{bmatrix}
    =
    \begin{bmatrix}
    AE-AF \ be \ BF \\\\
    AG \ Ah \ BG \ BH \\\\
    CE \ CF \ de \ DF \\\\
    CG \ ch \ DG \ DH \end{bmatrix} .
$$

Una convenzione di notazione utile finale che circonda i prodotti tensori è che, per qualsiasi vettore $ v $ o matrice $ M $ , $ v ^ { \otimes n } $ o $ m ^ { \otimes n } $ è una mano breve per un $ $ prodotto tensore ripetuto a n riduzioni.  Ad esempio:

\begin{align}
&\begin{bmatrix}1 \\\\ 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} , \qquad \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ \end{bmatrix} , \qquad \begin{bmatrix} 1 \\\\ -1 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ -1 \\\\ -1 \\\\ 1 \end{bmatrix} ,\\\\
  &\begin{bmatrix}0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} , \qquad \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 1 & 0 & 0 & 0 \end{bmatrix} .
\end{align}

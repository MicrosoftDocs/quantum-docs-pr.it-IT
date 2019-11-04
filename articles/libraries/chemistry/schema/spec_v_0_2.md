---
title: Specifica dello schema Broombridge
author: guanghaolow
ms.author: gulow@microsoft.com
ms.date: 05/28/2019
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_2
ms.openlocfilehash: 2f4be96bc6f1e8e6fe21b93bc0d9ab2aa367fd53
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185308"
---
# <a name="broombridge-specification-v02"></a><span data-ttu-id="490d2-102">Specifica Broombridge v 0.2</span><span class="sxs-lookup"><span data-stu-id="490d2-102">Broombridge Specification v0.2</span></span> #

<span data-ttu-id="490d2-103">Le parole chiave "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDed", "MAY" e "OPTIONAL" in questo documento devono essere interpretate come descritto nella [specifica RFC 2119](https://tools.ietf.org/html/rfc2119).</span><span class="sxs-lookup"><span data-stu-id="490d2-103">The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).</span></span>

<span data-ttu-id="490d2-104">Qualsiasi sidebar con le intestazioni "NOTE", "informazioni" o "avviso" è informativa.</span><span class="sxs-lookup"><span data-stu-id="490d2-104">Any sidebar with the headings "NOTE," "INFORMATION," or "WARNING" is informative.</span></span>

## <a name="introduction"></a><span data-ttu-id="490d2-105">Introduzione</span><span class="sxs-lookup"><span data-stu-id="490d2-105">Introduction</span></span> ##

<span data-ttu-id="490d2-106">Questa sezione è informativa.</span><span class="sxs-lookup"><span data-stu-id="490d2-106">This section is informative.</span></span>

<span data-ttu-id="490d2-107">I documenti Broombridge sono destinati a comunicare istanze di problemi di simulazione nella chimica quantistica per l'elaborazione usando la simulazione quantistica e la programmazione toolchain.</span><span class="sxs-lookup"><span data-stu-id="490d2-107">Broombridge documents are intended to communicate instances of simulation problems in quantum chemistry for processing using quantum simulation and programming toolchains.</span></span>

## <a name="serialization"></a><span data-ttu-id="490d2-108">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="490d2-108">Serialization</span></span> ##

<span data-ttu-id="490d2-109">Questa sezione è normativa.</span><span class="sxs-lookup"><span data-stu-id="490d2-109">This section is normative.</span></span>

<span data-ttu-id="490d2-110">Un documento Broombridge deve essere serializzato come [documento YAML 1,2](http://yaml.org/spec/) che rappresenta un oggetto JSON, come descritto in [RFC 4627](https://tools.ietf.org/html/rfc4627) Section 2,2.</span><span class="sxs-lookup"><span data-stu-id="490d2-110">A Broombridge document MUST be serialized as a [YAML 1.2 document](http://yaml.org/spec/) representing a JSON object as described in [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2.2.</span></span>
<span data-ttu-id="490d2-111">L'oggetto serializzato per YAML deve avere una proprietà `"$schema"` il cui valore è `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"`e deve essere valido in base alle specifiche bozza-06 dello schema JSON [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span><span class="sxs-lookup"><span data-stu-id="490d2-111">The object serialized to YAML MUST have a property `"$schema"` whose value is `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"`, and MUST be valid according to the JSON Schema draft-06 specifications [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span></span>

<span data-ttu-id="490d2-112">Per la parte restante di questa specifica, "l'oggetto Broombridge" si riferisce all'oggetto JSON deserializzato da un documento YAML di Broombridge.</span><span class="sxs-lookup"><span data-stu-id="490d2-112">For the remainder of this specification, "the Broombridge object" will refer to the JSON object deserialized from a Broombridge YAML document.</span></span>

<span data-ttu-id="490d2-113">Se non diversamente specificato in modo esplicito, gli oggetti non devono avere proprietà aggiuntive oltre a quelle specificate in modo esplicito in questo documento.</span><span class="sxs-lookup"><span data-stu-id="490d2-113">Unless otherwise explicitly noted, objects MUST NOT have additional properties beyond those specified explicitly in this document.</span></span>

## <a name="additional-definitions"></a><span data-ttu-id="490d2-114">Definizioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="490d2-114">Additional Definitions</span></span> ##

<span data-ttu-id="490d2-115">Questa sezione è normativa.</span><span class="sxs-lookup"><span data-stu-id="490d2-115">This section is normative.</span></span>

### <a name="quantity-objects"></a><span data-ttu-id="490d2-116">Quantità-oggetti</span><span class="sxs-lookup"><span data-stu-id="490d2-116">Quantity Objects</span></span> ###

<span data-ttu-id="490d2-117">Questa sezione è normativa.</span><span class="sxs-lookup"><span data-stu-id="490d2-117">This section is normative.</span></span>

<span data-ttu-id="490d2-118">Un _oggetto Quantity_ è un oggetto JSON e deve avere una proprietà `units` il cui valore è uno dei valori consentiti elencati nella tabella 1.</span><span class="sxs-lookup"><span data-stu-id="490d2-118">A _quantity object_ is a JSON object, and MUST have a property `units` whose value is one of the allowed values listed in Table 1.</span></span>

<span data-ttu-id="490d2-119">Un oggetto Quantity è un _oggetto quantità semplice_ se dispone di una singola proprietà `value` oltre alla relativa proprietà `units`.</span><span class="sxs-lookup"><span data-stu-id="490d2-119">A quantity object is a _simple quantity object_ if it has a single property `value` in addition to its `units` property.</span></span>
<span data-ttu-id="490d2-120">Il valore della proprietà `value` deve essere un numero.</span><span class="sxs-lookup"><span data-stu-id="490d2-120">The value of the `value` property MUST be a number.</span></span>

<span data-ttu-id="490d2-121">Un oggetto Quantity è un _oggetto Quantity associato_ se dispone delle proprietà `lower` e `upper` oltre alla relativa proprietà `units`.</span><span class="sxs-lookup"><span data-stu-id="490d2-121">A quantity object is a _bounded quantity object_ if it has the properties `lower` and `upper` in addition to its `units` property.</span></span>
<span data-ttu-id="490d2-122">I valori delle proprietà `lower` e `upper` devono essere numeri.</span><span class="sxs-lookup"><span data-stu-id="490d2-122">The values of the `lower` and `upper` properties MUST be numbers.</span></span>
<span data-ttu-id="490d2-123">Un oggetto della quantità limitata può avere una proprietà `value` il cui valore è un numero.</span><span class="sxs-lookup"><span data-stu-id="490d2-123">A bounded quantity object MAY have a property `value` whose value is a number.</span></span>

<span data-ttu-id="490d2-124">Un oggetto Quantity è un _oggetto quantità di matrici di tipo sparse_ se ha la proprietà `format` e una proprietà `values` oltre alla relativa proprietà `units`.</span><span class="sxs-lookup"><span data-stu-id="490d2-124">A quantity object is a _sparse array quantity object_ if it has the property `format` and a property `values` in addition to its `units` property.</span></span>
<span data-ttu-id="490d2-125">Il valore di `format` deve essere la stringa `sparse`.</span><span class="sxs-lookup"><span data-stu-id="490d2-125">The value of `format` MUST be the string `sparse`.</span></span>
<span data-ttu-id="490d2-126">Il valore della proprietà `values` deve essere una matrice.</span><span class="sxs-lookup"><span data-stu-id="490d2-126">The value of the `values` property MUST be an array.</span></span>
<span data-ttu-id="490d2-127">Ogni elemento di `values` deve essere una matrice che rappresenta gli indici e il valore della quantità di matrici di tipo sparse.</span><span class="sxs-lookup"><span data-stu-id="490d2-127">Each element of `values` MUST be an array representing the indices and value of the sparse array quantity.</span></span>

<span data-ttu-id="490d2-128">Gli indici per ogni elemento di un oggetto della quantità di matrici di tipo sparse devono essere univoci nell'intero oggetto della quantità di matrici di tipo sparse.</span><span class="sxs-lookup"><span data-stu-id="490d2-128">The indices for each element of a sparse array quantity object MUST be unique across the entire sparse array quantity object.</span></span>
<span data-ttu-id="490d2-129">Se è presente un indice con un valore di `0`, un parser deve considerare l'oggetto quantità di matrici di tipo sparse in modo identico a un oggetto quantità di matrici di tipo sparse in cui tale indice non è presente.</span><span class="sxs-lookup"><span data-stu-id="490d2-129">If an index is present with a value of `0`, a parser MUST treat the sparse array quantity object identically to a sparse array quantity object in which that index is not present at all.</span></span>


<span data-ttu-id="490d2-130">Un oggetto Quantity deve essere</span><span class="sxs-lookup"><span data-stu-id="490d2-130">A quantity object MUST either be</span></span>

- <span data-ttu-id="490d2-131">un oggetto quantità semplice,</span><span class="sxs-lookup"><span data-stu-id="490d2-131">a simple quantity object,</span></span>
- <span data-ttu-id="490d2-132">oggetto della quantità delimitata o</span><span class="sxs-lookup"><span data-stu-id="490d2-132">a bounded quantity object, or</span></span>
- <span data-ttu-id="490d2-133">oggetto della quantità di matrici di tipo sparse.</span><span class="sxs-lookup"><span data-stu-id="490d2-133">a sparse array quantity object.</span></span>


### <a name="examples"></a><span data-ttu-id="490d2-134">esempi</span><span class="sxs-lookup"><span data-stu-id="490d2-134">Examples</span></span> ###

<span data-ttu-id="490d2-135">Questa sezione è informativa.</span><span class="sxs-lookup"><span data-stu-id="490d2-135">This section is informative.</span></span>

<span data-ttu-id="490d2-136">Quantità semplice che rappresenta $1.9844146837\,\mathrm{Ha} $:</span><span class="sxs-lookup"><span data-stu-id="490d2-136">A simple quantity representing $1.9844146837\,\mathrm{Ha}$:</span></span>

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

<span data-ttu-id="490d2-137">Una quantità limitata che rappresenta una distribuzione uniforme nell'intervallo $ [-7,-6]\,\mathrm{Ha} $:</span><span class="sxs-lookup"><span data-stu-id="490d2-137">A bounded quantity representing a uniform distribution over the interval $[-7, -6]\,\mathrm{Ha}$:</span></span>

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

<span data-ttu-id="490d2-138">Di seguito è riportata una quantità di matrici di tipo sparse con un elemento `[1, 2]` uguale a `hello` e un elemento `[3, 4]` uguale a `world`:</span><span class="sxs-lookup"><span data-stu-id="490d2-138">The following is a sparse array quantity with an element `[1, 2]` equal to `hello` and an element `[3, 4]` equal to `world`:</span></span>

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a><span data-ttu-id="490d2-139">Sezione Format</span><span class="sxs-lookup"><span data-stu-id="490d2-139">Format Section</span></span> ##

<span data-ttu-id="490d2-140">Questa sezione è normativa.</span><span class="sxs-lookup"><span data-stu-id="490d2-140">This section is normative.</span></span>

<span data-ttu-id="490d2-141">L'oggetto Broombridge deve avere una proprietà `format` il cui valore è un oggetto JSON con una proprietà denominata `version`.</span><span class="sxs-lookup"><span data-stu-id="490d2-141">The Broombridge object MUST have a property `format` whose value is a JSON object with one property called `version`.</span></span>
<span data-ttu-id="490d2-142">Il valore della proprietà `version` deve essere `"0.2"`.</span><span class="sxs-lookup"><span data-stu-id="490d2-142">The `version` property MUST have the value `"0.2"`.</span></span>

### <a name="example"></a><span data-ttu-id="490d2-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="490d2-143">Example</span></span> ###

<span data-ttu-id="490d2-144">Questa sezione è informativa.</span><span class="sxs-lookup"><span data-stu-id="490d2-144">This section is informative.</span></span>

```yaml
format:                        # required
    version: "0.2"             # must match exactly
```

## <a name="problem-description-section"></a><span data-ttu-id="490d2-145">Sezione Descrizione problema</span><span class="sxs-lookup"><span data-stu-id="490d2-145">Problem Description Section</span></span> ##

<span data-ttu-id="490d2-146">Questa sezione è normativa.</span><span class="sxs-lookup"><span data-stu-id="490d2-146">This section is normative.</span></span>

<span data-ttu-id="490d2-147">L'oggetto Broombridge deve avere una proprietà `problem_description` il cui valore è una matrice JSON.</span><span class="sxs-lookup"><span data-stu-id="490d2-147">The Broombridge object MUST have a property `problem_description` whose value is a JSON array.</span></span>
<span data-ttu-id="490d2-148">Ogni elemento del valore della proprietà `problem_description` deve essere un oggetto JSON che descrive un set di integrali, come descritto nella parte restante di questa sezione.</span><span class="sxs-lookup"><span data-stu-id="490d2-148">Each item in the value of the `problem_description` property MUST be a JSON object describing one set of integrals, as described in the remainder of this section.</span></span>
<span data-ttu-id="490d2-149">Nella parte restante di questa sezione, il termine "oggetto Descrizione problema" si riferisce a un elemento nel valore della proprietà `problem_description` dell'oggetto Broombridge.</span><span class="sxs-lookup"><span data-stu-id="490d2-149">In the remainder of this section, the term "problem description object" will refer to an item in the value of the `problem_description` property of the Broombridge object.</span></span>

<span data-ttu-id="490d2-150">Ogni oggetto Descrizione problema deve avere una proprietà `metadata` il cui valore è un oggetto JSON.</span><span class="sxs-lookup"><span data-stu-id="490d2-150">Each problem description object MUST have a property `metadata` whose value is a JSON object.</span></span>
<span data-ttu-id="490d2-151">Il valore di `metadata` può essere l'oggetto JSON vuoto (ovvero `{}`) oppure può contenere proprietà aggiuntive definite dall'implementatore.</span><span class="sxs-lookup"><span data-stu-id="490d2-151">The value of `metadata` MAY be the empty JSON object (that is, `{}`), or MAY contain additional properties defined by the implementor.</span></span>

### <a name="hamiltonian-section"></a><span data-ttu-id="490d2-152">Sezione hamiltoniana</span><span class="sxs-lookup"><span data-stu-id="490d2-152">Hamiltonian Section</span></span> ###

#### <a name="overview"></a><span data-ttu-id="490d2-153">Panoramica</span><span class="sxs-lookup"><span data-stu-id="490d2-153">Overview</span></span> ####

<span data-ttu-id="490d2-154">Questa sezione è informativa.</span><span class="sxs-lookup"><span data-stu-id="490d2-154">This section is informative.</span></span>

<span data-ttu-id="490d2-155">La proprietà `hamiltonian` di ogni oggetto Descrizione problema descrive l'Hamiltoniana per un particolare problema di chimica quantistica elencando i termini di uno e due corpi come matrici di tipo sparse di numeri reali.</span><span class="sxs-lookup"><span data-stu-id="490d2-155">The `hamiltonian` property of each problem description object describes the Hamiltonian for a particular quantum chemistry problem by listing out its one- and two-body terms as sparse arrays of real numbers.</span></span>
<span data-ttu-id="490d2-156">Gli operatori hamiltoniana descritti da ogni oggetto Descrizione problema hanno il formato</span><span class="sxs-lookup"><span data-stu-id="490d2-156">The Hamiltonian operators described by each problem description object take the form</span></span>

<span data-ttu-id="490d2-157">$ $ H = \sum\_\{i, j\}\sum\_{\sigma\in\\{\uparrow, \downarrow\\}} H\_\{IJ\} a ^\{\dagger\}\_{i , \sigma} a\_{j, \sigma} + \frac{1}{2}\sum\_\{i, j, k, l\}\sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}} h\_{IJKL} a ^ \dagger\_{i , \sigma} a ^ \dagger\_{k, \rho} a\_{l, \rho} a\_{j, \sigma}, $ $</span><span class="sxs-lookup"><span data-stu-id="490d2-157">$$ H = \sum\_\{i,j\}\sum\_{\sigma\in\\{\uparrow,\downarrow\\}} h\_\{ij\} a^\{\dagger\}\_{i,\sigma} a\_{j,\sigma} + \frac{1}{2}\sum\_\{i,j,k,l\}\sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}} h\_{ijkl} a^\dagger\_{i,\sigma} a^\dagger\_{k,\rho} a\_{l,\rho} a\_{j,\sigma}, $$</span></span>

<span data-ttu-id="490d2-158">qui $h _ {IJKL} = (IJ | KL) $ nella convenzione Mulliken.</span><span class="sxs-lookup"><span data-stu-id="490d2-158">here $h_{ijkl}= (ij|kl)$ in Mulliken convention.</span></span>

<span data-ttu-id="490d2-159">Per maggiore chiarezza, il termine a un elettrone è</span><span class="sxs-lookup"><span data-stu-id="490d2-159">For clarity, the one-electron term is</span></span>

<span data-ttu-id="490d2-160">$ $ h {IJ} = \int {\mathrm d} x \psi ^ \*\_i (x) \left (\frac{1}{2}\nabla ^ 2 + \sum\_{A} \frac{Z\_A} {| x-x\_A |}  \right) \psi\_j (x), $ $</span><span class="sxs-lookup"><span data-stu-id="490d2-160">$$ h_{ij} = \int {\mathrm d}x \psi^\*\_i(x) \left(\frac{1}{2}\nabla^2 + \sum\_{A}\frac{Z\_A}{|x-x\_A|}  \right) \psi\_j(x), $$</span></span>

<span data-ttu-id="490d2-161">e il termine a due elettroni è</span><span class="sxs-lookup"><span data-stu-id="490d2-161">and the two-electron term is</span></span>

<span data-ttu-id="490d2-162">$ $ h\_\{IJKL\} = \iint \{\mathrm d\}x ^ 2 \psi ^\{\*\}\_i (x\_1) \psi\_j (x\_1) \frac\{1\}\{\|x\_1-x\_2\|\}\psi\_k ^\{\*\}(x\_2) \psi\_l (x\_2).</span><span class="sxs-lookup"><span data-stu-id="490d2-162">$$ h\_\{ijkl\} = \iint \{\mathrm d\}x^2 \psi^\{\*\}\_i(x\_1)\psi\_j(x\_1) \frac\{1\}\{\|x\_1 -x\_2\|\}\psi\_k^\{\*\}(x\_2) \psi\_l(x\_2).</span></span>
$$

<span data-ttu-id="490d2-163">Come indicato nella descrizione della [proprietà`basis_set`](#basis-set-object) di ogni elemento della proprietà `integral_sets`, si presuppone in modo esplicito che le funzioni di base usate siano di valore reale.</span><span class="sxs-lookup"><span data-stu-id="490d2-163">As noted in our description of the [`basis_set` property](#basis-set-object) of each element of the `integral_sets` property, we further explicitly assume that the basis functions used are real-valued.</span></span>
<span data-ttu-id="490d2-164">In questo modo è possibile usare le simmetrie seguenti tra i termini per comprimere la rappresentazione dell'hamiltoniana.</span><span class="sxs-lookup"><span data-stu-id="490d2-164">This allows us to use the following symmetries between the terms to compress the representation of the Hamiltonian.</span></span>

<span data-ttu-id="490d2-165">$ $ h {IJKL} = h {Ijlk} = h {jikl} = h {JILK} = h {klij} = h {klji} = h {lkij} = h {lkji}.</span><span class="sxs-lookup"><span data-stu-id="490d2-165">$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.</span></span>
$$


#### <a name="contents"></a><span data-ttu-id="490d2-166">Contenuti</span><span class="sxs-lookup"><span data-stu-id="490d2-166">Contents</span></span> ####

<span data-ttu-id="490d2-167">Questa sezione è normativa.</span><span class="sxs-lookup"><span data-stu-id="490d2-167">This section is normative.</span></span>

<span data-ttu-id="490d2-168">Ogni oggetto Descrizione problema deve avere una proprietà `hamiltonian` il cui valore è un oggetto JSON.</span><span class="sxs-lookup"><span data-stu-id="490d2-168">Each problem description object MUST have a property `hamiltonian` whose value is a JSON object.</span></span>
<span data-ttu-id="490d2-169">Il valore della proprietà `hamiltonian` è noto come oggetto hamiltoniana ed è necessario che le proprietà `one_electron_integrals` e `two_electron_integrals` come descritto nella parte restante di questa sezione.</span><span class="sxs-lookup"><span data-stu-id="490d2-169">The value of the `hamiltonian` property is known as a Hamiltonian object, and MUST have the properties `one_electron_integrals` and `two_electron_integrals` as described in the remainder of this section.</span></span>

<span data-ttu-id="490d2-170">Ogni oggetto Descrizione problema deve disporre di una proprietà `coulomb_repulsion` il cui valore è un oggetto quantità semplice.</span><span class="sxs-lookup"><span data-stu-id="490d2-170">Each problem description object MUST have a property `coulomb_repulsion` whose value is a simple quantity object.</span></span>
<span data-ttu-id="490d2-171">Ogni oggetto Descrizione problema deve disporre di una proprietà `energy_offet` il cui valore è un oggetto quantità semplice.</span><span class="sxs-lookup"><span data-stu-id="490d2-171">Each problem description object MUST have a property `energy_offet` whose value is a simple quantity object.</span></span>
> <span data-ttu-id="490d2-172">Si noti I valori di `coulomb_repulsion` e `energy_offet` aggiunti insieme acquisiscono il termine di identità dell'hamiltoniana.</span><span class="sxs-lookup"><span data-stu-id="490d2-172">[NOTE] The values of `coulomb_repulsion` and `energy_offet` added together capture the identity term of the Hamiltonian.</span></span>

##### <a name="one-electron-integrals-object"></a><span data-ttu-id="490d2-173">Oggetto integrali a un elettrone</span><span class="sxs-lookup"><span data-stu-id="490d2-173">One-Electron Integrals Object</span></span> #####

<span data-ttu-id="490d2-174">Questa sezione è normativa.</span><span class="sxs-lookup"><span data-stu-id="490d2-174">This section is normative.</span></span>

<span data-ttu-id="490d2-175">La proprietà `one_electron_integrals` dell'oggetto hamiltoniana deve essere una quantità di matrici di tipo sparse i cui indici sono due Integer e i cui valori sono numeri.</span><span class="sxs-lookup"><span data-stu-id="490d2-175">The `one_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity whose indices are two integers and whose values are numbers.</span></span>
<span data-ttu-id="490d2-176">Ogni termine deve avere indici `[i, j]` in cui `i >= j`.</span><span class="sxs-lookup"><span data-stu-id="490d2-176">Every term MUST have indices `[i, j]` where `i >= j`.</span></span>

> <span data-ttu-id="490d2-177">Si noti Ciò riflette la simmetria che $h _ {IJ} = h {ji} $, che è una conseguenza del fatto che l'hamiltoniana è Hermitiane.</span><span class="sxs-lookup"><span data-stu-id="490d2-177">[NOTE] This reflects the symmetry that $h_{ij} = h_{ji}$ which is a consequence of the fact that the Hamiltonian is Hermitian.</span></span>


###### <a name="example"></a><span data-ttu-id="490d2-178">Esempio</span><span class="sxs-lookup"><span data-stu-id="490d2-178">Example</span></span> ######

<span data-ttu-id="490d2-179">Questa sezione è informativa.</span><span class="sxs-lookup"><span data-stu-id="490d2-179">This section is informative.</span></span>

<span data-ttu-id="490d2-180">La seguente quantità di matrici di tipo sparse rappresenta l'Hamiltoniana $ $ H = \left (-5,0 (a ^\{\dagger\}\_{1, \uparrow} a\_{1, \uparrow} + a ^\{\dagger\}\_{1, \downarrow} a\_{1 , \downarrow}) + 0,17 (a ^\{\dagger\}\_{2, \uparrow} a\_{1, \uparrow} + a ^\{\dagger\}\_{1, \uparrow} a\_{2, \uparrow} + a ^\{\dagger\}\_{2 , \downarrow} a\_{1, \downarrow} + a ^\{\dagger\}\_{1, \downarrow} a\_{2, \downarrow}) \right)\\, \mathrm{Ha}.</span><span class="sxs-lookup"><span data-stu-id="490d2-180">The following sparse array quantity represents the Hamiltonian $$ H = \left(-5.0  (a^\{\dagger\}\_{1,\uparrow} a\_{1,\uparrow}+a^\{\dagger\}\_{1,\downarrow} a\_{1,\downarrow})+ 0.17 (a^\{\dagger\}\_{2,\uparrow} a\_{1,\uparrow}+ a^\{\dagger\}\_{1,\uparrow} a\_{2,\uparrow}+a^\{\dagger\}\_{2,\downarrow} a\_{1,\downarrow}+ a^\{\dagger\}\_{1,\downarrow} a\_{2,\downarrow})\right)\\,\mathrm{Ha}.</span></span>
$$

```yaml
one_electron_integrals:     # required
    units: hartree          # required
    format: sparse          # required
    values:                 # required
        # i j f(i,j)
        - [1, 1, -5.0]
        - [2, 1,  0.17]
```
> [!NOTE]
> <span data-ttu-id="490d2-181">Broombridge usa l'indicizzazione in base 1.</span><span class="sxs-lookup"><span data-stu-id="490d2-181">Broombridge uses 1-based indexing.</span></span>


##### <a name="two-electron-integrals-object"></a><span data-ttu-id="490d2-182">Oggetto integrali a due elettroni</span><span class="sxs-lookup"><span data-stu-id="490d2-182">Two-Electron Integrals Object</span></span> #####

<span data-ttu-id="490d2-183">Questa sezione è normativa.</span><span class="sxs-lookup"><span data-stu-id="490d2-183">This section is normative.</span></span>

<span data-ttu-id="490d2-184">La proprietà `two_electron_integrals` dell'oggetto hamiltoniana deve essere una quantità di matrici di tipo sparse con una proprietà aggiuntiva denominata `index_convention`.</span><span class="sxs-lookup"><span data-stu-id="490d2-184">The `two_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity with one additional property called `index_convention`.</span></span>
<span data-ttu-id="490d2-185">Ogni elemento del valore di `two_electron_integrals` deve avere quattro indici.</span><span class="sxs-lookup"><span data-stu-id="490d2-185">Each element of the value of `two_electron_integrals` MUST have four indices.</span></span>

<span data-ttu-id="490d2-186">Ogni proprietà `two_electron_integrals` deve avere una proprietà `index_convention`.</span><span class="sxs-lookup"><span data-stu-id="490d2-186">Each `two_electron_integrals` property MUST have a `index_convention` property.</span></span>
<span data-ttu-id="490d2-187">Il valore della proprietà `index_convention` deve essere uno dei valori consentiti elencati nella tabella 1.</span><span class="sxs-lookup"><span data-stu-id="490d2-187">The value of the `index_convention` property MUST be one of the allowed values listed in Table 1.</span></span>
<span data-ttu-id="490d2-188">Se il valore di `index_convention` è `mulliken`, per ogni elemento della quantità `two_electron_integrals` matrice di tipo sparse, un parser che carica un documento Broombridge deve creare un'istanza di un termine hamiltoniana uguale all'operatore a due elettroni $h _ {i, j, k, l} a ^ \dagger_i a ^ \dagger_j a_k a_L $ , dove $i $, $j $, $k $ e $l $ devono essere numeri interi di valore almeno 1 e dove $h _ {i, j, k, l} $ è l'elemento `[i, j, k, l, h(i, j, k, l)]` della quantità di matrici di tipo sparse.</span><span class="sxs-lookup"><span data-stu-id="490d2-188">If the value of `index_convention` is `mulliken`, then for each element of the `two_electron_integrals` sparse array quantity, a parser loading a Broombridge document MUST instantiate a Hamiltonian term equal to the two-electron operator $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, where $i$, $j$, $k$, and $l$ MUST be integers of value at least 1, and where $h_{i, j, k, l}$ is the element `[i, j, k, l, h(i, j, k, l)]` of the sparse array quantity.</span></span>

###### <a name="symmetries"></a><span data-ttu-id="490d2-189">Simmetrie</span><span class="sxs-lookup"><span data-stu-id="490d2-189">Symmetries</span></span> ######

<span data-ttu-id="490d2-190">Questa sezione è normativa.</span><span class="sxs-lookup"><span data-stu-id="490d2-190">This section is normative.</span></span>

<span data-ttu-id="490d2-191">Se la proprietà `index_convention` di un oggetto `two_electron_integrals` è uguale a `mulliken`, se è presente un elemento con indici `[i, j, k, l]`, gli indici seguenti non devono essere presenti, a meno che non siano uguali a `[i, j, k, l]`:</span><span class="sxs-lookup"><span data-stu-id="490d2-191">If the `index_convention` property of a `two_electron_integrals` object is equal to `mulliken`, then if an element with indices `[i, j, k, l]` is present, the following indices MUST NOT be present unless they are equal to `[i, j, k, l]`:</span></span>

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> <span data-ttu-id="490d2-192">Poiché la proprietà `index_convention` è un oggetto quantità di tipo sparse, non è possibile ripetere gli indici su elementi diversi.</span><span class="sxs-lookup"><span data-stu-id="490d2-192">Because the `index_convention` property is a sparse quantity object, no indices may be repeated on different elements.</span></span>
> <span data-ttu-id="490d2-193">In particolare, se è presente un elemento con indici `[i, j, k, l]`, nessun altro elemento potrà avere tali indici.</span><span class="sxs-lookup"><span data-stu-id="490d2-193">In particular, if an element with indices `[i, j, k, l]` is present, no other element may have those indices.</span></span>


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a><span data-ttu-id="490d2-194">Esempio</span><span class="sxs-lookup"><span data-stu-id="490d2-194">Example</span></span> #######

<span data-ttu-id="490d2-195">Questa sezione è informativa.</span><span class="sxs-lookup"><span data-stu-id="490d2-195">This section is informative.</span></span>

<span data-ttu-id="490d2-196">L'oggetto seguente specifica l'Hamiltoniana</span><span class="sxs-lookup"><span data-stu-id="490d2-196">The following object specifies the Hamiltonian</span></span>

<span data-ttu-id="490d2-197">$ $ H = \frac12 \sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}} \Biggr (1,6 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{1, \rho} a\_{1, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{6 , \sigma} a ^ {\dagger}\_{1, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{6, \sigma} a ^ {\dagger}\_{1, \rho} a\_{2, \rho} a\_{3 , \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{6, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{6, \rho} a\_{2 , \rho} a\_{3, \sigma} $ $ $ $-0,1 a ^ {\dagger}\_{3, \sigma} a ^ {\dagger}\_{2, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{3, \sigma} a ^ {\dagger}\_{2 , \rho} a\_{1, \rho} a\_{6, \sigma}-0,1 a ^ {\dagger}\_{2, \sigma} a ^ {\dagger}\_{3, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{2 , \sigma} a ^ {\dagger}\_{3, \rho} a\_{1, \rho} a\_{6, \sigma}\Biggr)\\, \textrm{Ha}.</span><span class="sxs-lookup"><span data-stu-id="490d2-197">$$ H = \frac12 \sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}}\Biggr( 1.6 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{1,\rho} a\_{1,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{2,\rho} a\_{3,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{2,\rho} a\_{3,\sigma} $$ $$- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{1,\rho} a\_{6,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{1,\rho} a\_{6,\sigma}\Biggr)\\,\textrm{Ha}.</span></span>
$$

```yaml
two_electron_integrals:
    index_convention: mulliken
    units: hartree
    format: sparse
    values:
        - [1, 1, 1, 1,  1.6]
        - [6, 1, 3, 2, -0.1]
```

### <a name="initial-state-section"></a><span data-ttu-id="490d2-198">Sezione stato iniziale</span><span class="sxs-lookup"><span data-stu-id="490d2-198">Initial State Section</span></span> ###

<span data-ttu-id="490d2-199">Questa sezione è normativa.</span><span class="sxs-lookup"><span data-stu-id="490d2-199">This section is normative.</span></span>

<span data-ttu-id="490d2-200">L'oggetto `initial_state_suggestion` il cui valore è una matrice JSON specifica gli Stati del quantum iniziale di interesse per l'Hamiltoniana specificata.</span><span class="sxs-lookup"><span data-stu-id="490d2-200">The `initial_state_suggestion` object whose value is a JSON array specifies initial quantum states of interest to the specified Hamiltonian.</span></span> <span data-ttu-id="490d2-201">Ogni elemento del valore della proprietà `initial_state_suggestion` deve essere un oggetto JSON che descrive uno stato quantum, come descritto nella parte restante di questa sezione.</span><span class="sxs-lookup"><span data-stu-id="490d2-201">Each item in the value of the `initial_state_suggestion` property MUST be a JSON object describing one quantum state, as described in the remainder of this section.</span></span>
<span data-ttu-id="490d2-202">Nella parte restante di questa sezione, il termine "oggetto stato" fa riferimento a un elemento nel valore della proprietà `initial_state_suggestion` dell'oggetto Broombridge.</span><span class="sxs-lookup"><span data-stu-id="490d2-202">In the remainder of this section, the term "state object" will refer to an item in the value of the `initial_state_suggestion` property of the Broombridge object.</span></span>

#### <a name="state-object"></a><span data-ttu-id="490d2-203">State (oggetto)</span><span class="sxs-lookup"><span data-stu-id="490d2-203">State object</span></span> ####

<span data-ttu-id="490d2-204">Questa sezione è normativa.</span><span class="sxs-lookup"><span data-stu-id="490d2-204">This section is normative.</span></span>

<span data-ttu-id="490d2-205">Ogni oggetto stato deve avere una proprietà `label` contenente una stringa.</span><span class="sxs-lookup"><span data-stu-id="490d2-205">Each state object MUST have a `label` property containing a string.</span></span> <span data-ttu-id="490d2-206">Ogni oggetto stato deve avere una proprietà `method`.</span><span class="sxs-lookup"><span data-stu-id="490d2-206">Each state object MUST have a `method` property.</span></span> <span data-ttu-id="490d2-207">Il valore della proprietà `method` deve essere uno dei valori consentiti elencati nella tabella 3.</span><span class="sxs-lookup"><span data-stu-id="490d2-207">The value of the `method` property MUST be one of the allowed values listed in Table 3.</span></span>
<span data-ttu-id="490d2-208">Ogni oggetto stato può avere una proprietà `energy` il cui valore deve essere un oggetto quantità semplice.</span><span class="sxs-lookup"><span data-stu-id="490d2-208">Each state object MAY have a property `energy` whose value MUST be a simple quantity object.</span></span>

<span data-ttu-id="490d2-209">Se il valore della proprietà `method` è `sparse_multi_configurational`, l'oggetto stato deve avere una proprietà `superposition` contenente una matrice di Stati di base e le relative ampiezze non normalizzate.</span><span class="sxs-lookup"><span data-stu-id="490d2-209">If the value of the `method` property is `sparse_multi_configurational`, the state object MUST have a `superposition` property containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="490d2-210">Ad esempio, gli stati iniziali $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) \ket{0} $ $ $ $ \ket{E} = \frac{0.1 (a ^ {\dagger}\_{1 , \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) + 0.2 (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{3, \uparrow}a ^ {\dagger}\_{2, \downarrow})} {\sqrt{| 0.1 | ^ 2 + | 0.2 | ^ 2}} \ket{0}, $ $ dove $ \ket{E} $ ha energia $0,987 \textrm{Ha} $, sono rappresentati da</span><span class="sxs-lookup"><span data-stu-id="490d2-210">For example, the initial states $$ \ket{G0}=\ket{G1}=\ket{G2}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0} $$ $$ \ket{E}=\frac{0.1 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})+0.2 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\uparrow}a^{\dagger}\_{2,\downarrow})}{\sqrt{|0.1|^2+|0.2|^2}}\ket{0}, $$ where $\ket{E}$ has energy $0.987 \textrm{Ha}$, are represented by</span></span>
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
  - label: "|G0>"
    method: sparse_multi_configurational
    superposition:
      - [1.0, "(1a)+","(2a)+","(2b)+","|vacuum>"]
  - label: "|G1>"
    method: sparse_multi_configurational
    superposition:
      - [-1.0, "(2a)+","(1a)+","(2b)+","|vacuum>"]
  - label: "|G2>"
    method: sparse_multi_configurational
    superposition:
      - [1.0, "(3a)","(1a)+","(2a)+","(3a)+","(2b)+","|vacuum>"]
  - label: "|E>"
    energy: {units: hartree, value: 0.987}
    method: sparse_multi_configurational
    superposition:
      - [0.1, "(1a)+","(2a)+","(2b)+","|vacuum>"]
      - [0.2, "(1a)+","(3a)+","(2b)+","|vacuum>"]
```

<span data-ttu-id="490d2-211">Se il valore della proprietà `method` è `unitary_coupled_cluster`, l'oggetto stato deve avere una proprietà `cluster_operator` il cui valore è un oggetto JSON.</span><span class="sxs-lookup"><span data-stu-id="490d2-211">If the value of the `method` property is `unitary_coupled_cluster`, the state object MUST have a `cluster_operator` property whose value is a JSON object.</span></span>
<span data-ttu-id="490d2-212">L'oggetto JSON deve avere una proprietà `reference_state` il cui valore è uno stato di base.</span><span class="sxs-lookup"><span data-stu-id="490d2-212">The JSON object MUST have a `reference_state` property whose value is a basis state.</span></span>
<span data-ttu-id="490d2-213">L'oggetto JSON può avere una proprietà `one_body_amplitudes` il cui valore è una matrice di operatori del cluster a corpo singolo e le relative ampiezze.</span><span class="sxs-lookup"><span data-stu-id="490d2-213">The JSON object MAY have a `one_body_amplitudes` property whose value is an array of one-body cluster operators and their amplitudes.</span></span>
<span data-ttu-id="490d2-214">L'oggetto JSON può avere una proprietà `two_body_amplitudes` il cui valore è una matrice di operatori di cluster con due corpi e le relative ampiezze.</span><span class="sxs-lookup"><span data-stu-id="490d2-214">The JSON object MAY have a `two_body_amplitudes` property whose value is an array of two-body cluster operators and their amplitudes.</span></span>
<span data-ttu-id="490d2-215">contenente una matrice di Stati di base e le relative ampiezze non normalizzate.</span><span class="sxs-lookup"><span data-stu-id="490d2-215">containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="490d2-216">Ad esempio, lo stato $ $ \ket{\Text{Reference}} = (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) \ket{0}, $ $</span><span class="sxs-lookup"><span data-stu-id="490d2-216">For example, the state $$ \ket{\text{reference}}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0}, $$</span></span>

<span data-ttu-id="490d2-217">$ $ \ket{\text{UCCSD}} = e ^ {T-T ^ \dagger}\ket{\Text{Reference}}, $ $</span><span class="sxs-lookup"><span data-stu-id="490d2-217">$$ \ket{\text{UCCSD}}=e^{T-T^\dagger}\ket{\text{reference}}, $$</span></span>

<span data-ttu-id="490d2-218">$ $ T = 0,1 a ^ {\dagger}\_{3, \uparrow}a\_{2, \downarrow} + 0,2 a ^ {\dagger}\_{2, \uparrow}a\_{2, \downarrow}-0,3 a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{3, \downarrow}a\_{3 , \uparrow}a\_{2, \downarrow} $ $ è rappresentato da</span><span class="sxs-lookup"><span data-stu-id="490d2-218">$$ T = 0.1 a^{\dagger}\_{3,\uparrow}a\_{2,\downarrow} + 0.2 a^{\dagger}\_{2,\uparrow}a\_{2,\downarrow} - 0.3 a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\downarrow}a\_{3,\uparrow}a\_{2,\downarrow} $$ is represented by</span></span>
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
  - label: "UCCSD"
    method: unitary_coupled_cluster
    cluster_operator: # Initial state that cluster operator is applied to.
        reference_state: 
          [1.0, "(1a)+", "(2a)+", "(2b)+", '|vacuum>']
        one_body_amplitudes: # A one-body cluster term is t^{q}_{p} a^\dag_p a_q   
            - [0.1, "(3a)+", "(2b)"]
            - [-0.2, "(2a)+", "(2b)"]
        two_body_amplitudes: # A two-body unitary cluster term is t^{rs}_{pq} a^\dag_p a^\dag_q a_r a_s
            - [-0.3, "(1a)+", "(3b)+", "(3a)", "(2b)"]
```

#### <a name="basis-set-object"></a><span data-ttu-id="490d2-219">Oggetto set di basi</span><span class="sxs-lookup"><span data-stu-id="490d2-219">Basis Set Object</span></span> ####

<span data-ttu-id="490d2-220">Questa sezione è normativa.</span><span class="sxs-lookup"><span data-stu-id="490d2-220">This section is normative.</span></span>

<span data-ttu-id="490d2-221">Ogni oggetto descrizione del problema può avere una proprietà `basis_set`.</span><span class="sxs-lookup"><span data-stu-id="490d2-221">Each problem description object MAY have a `basis_set` property.</span></span>
<span data-ttu-id="490d2-222">Se presente, il valore della proprietà `basis_set` deve essere un oggetto con due proprietà, `type` e `name`.</span><span class="sxs-lookup"><span data-stu-id="490d2-222">If present, the value of the `basis_set` property MUST be an object with two properties, `type` and `name`.</span></span>

<span data-ttu-id="490d2-223">Le funzioni di base identificate dal valore della proprietà `basis_set` devono essere con valori reali.</span><span class="sxs-lookup"><span data-stu-id="490d2-223">The basis functions identified by the value of the `basis_set` property MUST be real-valued.</span></span>

> [!NOTE]
> <span data-ttu-id="490d2-224">Il presupposto che tutte le funzioni di base siano a valore reale possono essere rilassate nelle versioni future di questa specifica.</span><span class="sxs-lookup"><span data-stu-id="490d2-224">The assumption that all basis functions are real-valued may be relaxed in future versions of this specification.</span></span>

## <a name="tables-and-lists"></a><span data-ttu-id="490d2-225">Tabelle ed elenchi</span><span class="sxs-lookup"><span data-stu-id="490d2-225">Tables and Lists</span></span> ##

### <a name="table-1-allowed-physical-units"></a><span data-ttu-id="490d2-226">Tabella 1.</span><span class="sxs-lookup"><span data-stu-id="490d2-226">Table 1.</span></span> <span data-ttu-id="490d2-227">Unità fisiche consentite</span><span class="sxs-lookup"><span data-stu-id="490d2-227">Allowed Physical Units</span></span> ###

<span data-ttu-id="490d2-228">Questa sezione è normativa.</span><span class="sxs-lookup"><span data-stu-id="490d2-228">This section is normative.</span></span>

<span data-ttu-id="490d2-229">Qualsiasi stringa che specifica un'unità deve essere una delle seguenti:</span><span class="sxs-lookup"><span data-stu-id="490d2-229">Any string specifying a unit MUST be one of the following:</span></span>

- `hartree`
- `ev`

<span data-ttu-id="490d2-230">I parser e i producer devono considerare come equivalenti gli oggetti della quantità semplice seguenti:</span><span class="sxs-lookup"><span data-stu-id="490d2-230">Parsers and producers MUST treat the following simple quantity objects as equivalent:</span></span>

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a><span data-ttu-id="490d2-231">Tabella 2.</span><span class="sxs-lookup"><span data-stu-id="490d2-231">Table 2.</span></span> <span data-ttu-id="490d2-232">Convenzioni di indice consentite</span><span class="sxs-lookup"><span data-stu-id="490d2-232">Allowed Index Conventions</span></span> ###

<span data-ttu-id="490d2-233">Questa sezione è normativa.</span><span class="sxs-lookup"><span data-stu-id="490d2-233">This section is normative.</span></span>

<span data-ttu-id="490d2-234">Qualsiasi stringa che specifica una convenzione di indice deve essere una delle seguenti:</span><span class="sxs-lookup"><span data-stu-id="490d2-234">Any string specifying an index convention MUST be one of the following:</span></span>

- `mulliken`

<span data-ttu-id="490d2-235">Questa sezione è informativa.</span><span class="sxs-lookup"><span data-stu-id="490d2-235">This section is informative.</span></span>

<span data-ttu-id="490d2-236">Le convenzioni di indice aggiuntive possono essere introdotte nelle versioni future di questa specifica.</span><span class="sxs-lookup"><span data-stu-id="490d2-236">Additional index conventions may be introduced in future versions of this specification.</span></span>

#### <a name="interpretation-of-index-conventions"></a><span data-ttu-id="490d2-237">Interpretazione delle convenzioni degli indici</span><span class="sxs-lookup"><span data-stu-id="490d2-237">Interpretation of Index Conventions</span></span> ####

<span data-ttu-id="490d2-238">Questa sezione è informativa.</span><span class="sxs-lookup"><span data-stu-id="490d2-238">This section is informative.</span></span>

### <a name="table-3-allowed-state-methods"></a><span data-ttu-id="490d2-239">Tabella 3.</span><span class="sxs-lookup"><span data-stu-id="490d2-239">Table 3.</span></span> <span data-ttu-id="490d2-240">Metodi di stato consentiti</span><span class="sxs-lookup"><span data-stu-id="490d2-240">Allowed State methods</span></span> ###

<span data-ttu-id="490d2-241">Questa sezione è normativa.</span><span class="sxs-lookup"><span data-stu-id="490d2-241">This section is normative.</span></span>

<span data-ttu-id="490d2-242">Qualsiasi stringa che specifica un metodo di stato deve essere una delle seguenti:</span><span class="sxs-lookup"><span data-stu-id="490d2-242">Any string specifying a state method MUST be one of the following:</span></span>

- `sparse_multi_configurational`
- `unitary_coupled_cluster`

<span data-ttu-id="490d2-243">Questa sezione è informativa.</span><span class="sxs-lookup"><span data-stu-id="490d2-243">This section is informative.</span></span>

<span data-ttu-id="490d2-244">Ulteriori metodi di stato possono essere introdotti nelle versioni future di questa specifica.</span><span class="sxs-lookup"><span data-stu-id="490d2-244">Additional state methods may be introduced in future versions of this specification.</span></span>

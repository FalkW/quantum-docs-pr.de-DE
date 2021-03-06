---
title: Broombridge-Schema Spezifikation (ver 0,2)
description: Erläutert die Spezifikationen für das broombridge-Quantum-Schema v 0,2 für die Microsoft Quantum Chemistry Library.
author: guanghaolow
ms.author: gulow
ms.date: 05/28/2019
ms.topic: conceptual
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_2
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8d26b56d88f365144510692466bfffc7feb71d88
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854061"
---
# <a name="broombridge-specification-v02"></a>Broombridge-Spezifikation v 0,2 #

Die Schlüsselwörter "muss", "darf nicht", "erforderlich", "soll", "soll nicht", "sollte", "sollte nicht", "empfohlen", "Mai" und "optional" in diesem Dokument interpretiert werden, wie in [RFC 2119](https://tools.ietf.org/html/rfc2119)beschrieben.

Jede Rand Leiste mit den Überschriften "Note", "Information" oder "Warning" ist informativ.

## <a name="introduction"></a>Einführung ##

Dieser Abschnitt ist informativ.

Broombridge-Dokumente sollen Instanzen von Simulations Problemen in der Quantum-Chemie für die Verarbeitung mithilfe der Quantum-Simulation und der Programmier Toolkette kommunizieren.

## <a name="serialization"></a>Serialisierung ##

Dieser Abschnitt ist normativ.

Ein broombridge-Dokument muss als [YAML 1,2-Dokument](http://yaml.org/spec/) serialisiert werden, das ein JSON-Objekt darstellt, wie in [RFC 4627](https://tools.ietf.org/html/rfc4627) Abschnitt 2,2 beschrieben.
Das in YAML serialisierte-Objekt muss über eine `"$schema"` -Eigenschaft verfügen, deren Wert ist `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"` und gemäß den Spezifikationen des JSON-Schema Entwurfs-06 [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)] gültig sein muss.

Im restlichen Teil dieser Spezifikation verweist "das broombridge-Objekt" auf das JSON-Objekt, das aus einem broombridge-YAML-Dokument deserialisiert wurde.

Sofern nicht anders angegeben, dürfen Objekte keine zusätzlichen Eigenschaften aufweisen, die über die explizit in diesem Dokument angegebenen verfügen.

## <a name="additional-definitions"></a>Zusätzliche Definitionen ##

Dieser Abschnitt ist normativ.

### <a name="quantity-objects"></a>Mengen Objekte ###

Dieser Abschnitt ist normativ.

Bei einem _Mengen Objekt_ handelt es sich um ein JSON-Objekt, und es muss über eine Eigenschaft verfügen, `units` deren Wert einem der in Tabelle 1 aufgeführten zulässigen Werte entspricht.

Ein Mengen Objekt ist ein _einfaches Mengen Objekt_ , wenn es über eine einzelne Eigenschaft `value` zusätzlich zu seiner- `units` Eigenschaft verfügt.
Der Wert der- `value` Eigenschaft muss eine Zahl sein.

Bei einem Mengen Objekt handelt es sich um ein _Objekt mit begrenzter Menge_ , wenn es über die Eigenschaften `lower` und `upper` zusätzlich zur- `units` Eigenschaft verfügt.
Die Werte der `lower` Eigenschaften und `upper` müssen zahlen sein.
Ein Objekt mit begrenzter Menge kann über eine Eigenschaft verfügen, `value` deren Wert eine Zahl ist.

Bei einem Mengen Objekt handelt es sich um ein _Array Objekt_ mit geringer Dichte `format` , wenn die-Eigenschaft und eine-Eigenschaft `values` zusätzlich zur-Eigenschaft aufweisen `units` .
Der Wert von `format` muss die Zeichenfolge sein `sparse` .
Der Wert der `values` Eigenschaft muss ein Array sein.
Jedes Element von `values` muss ein Array sein, das die Indizes und den Wert der Menge an Arrays mit geringer Dichte darstellt.

Die Indizes für jedes Element eines Arrays mit geringer Dichte Menge müssen innerhalb des gesamten Objekts mit geringer Dichte Menge eindeutig sein.
Wenn ein Index mit dem Wert vorhanden ist `0` , muss ein Parser das Mengen Objekt mit geringer Dichte mit einem Array mit geringer Menge an Mengen Objekten behandeln, in dem dieser Index überhaupt nicht vorhanden ist.


Ein Mengen Objekt muss entweder

- ein einfaches Mengen Objekt,
- ein Objekt mit begrenzter Menge oder
- ein Mengen Objekt mit geringer Dichte.


### <a name="examples"></a>Beispiele ###

Dieser Abschnitt ist informativ.

Eine einfache Menge, die $1.9844146837 \, \mathrm{ha} $ darstellt:

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

Eine begrenzte Menge, die eine einheitliche Verteilung im Intervall von $ [-7,-6] \, \mathrm{ha} $ darstellt:

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

Im folgenden finden Sie eine Array Menge mit geringer Dichte, bei der ein `[1, 2]` -Element gleich ist `hello` und ein-Element `[3, 4]` gleich ist `world` :

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a>Abschnitt "Format" ##

Dieser Abschnitt ist normativ.

Das broombridge-Objekt muss über eine-Eigenschaft verfügen, `format` deren Wert ein JSON-Objekt mit einer Eigenschaft namens ist `version` .
Die- `version` Eigenschaft muss den Wert aufweisen `"0.2"` .

### <a name="example"></a>Beispiel ###

Dieser Abschnitt ist informativ.

```yaml
format:                        # required
    version: "0.2"             # must match exactly
```

## <a name="problem-description-section"></a>Problem Beschreibungs Abschnitt ##

Dieser Abschnitt ist normativ.

Das broombridge-Objekt muss über eine Eigenschaft verfügen, `problem_description` deren Wert ein JSON-Array ist.
Jedes Element im Wert der- `problem_description` Eigenschaft muss ein JSON-Objekt sein, das einen Satz von inteden beschreibt, wie im restlichen Teil dieses Abschnitts beschrieben.
Im restlichen Teil dieses Abschnitts verweist der Begriff "problembeschreibungs-Objekt" auf ein Element im Wert der- `problem_description` Eigenschaft des broombridge-Objekts.

Jedes Problem Beschreibungs Objekt muss über eine Eigenschaft verfügen, `metadata` deren Wert ein JSON-Objekt ist.
Der Wert von `metadata` kann das leere JSON-Objekt (d. h `{}` .) sein oder zusätzliche Eigenschaften enthalten, die durch den implemenor definiert werden.

### <a name="hamiltonian-section"></a>Hamiltona-Abschnitt ###

#### <a name="overview"></a>Übersicht ####

Dieser Abschnitt ist informativ.

Die- `hamiltonian` Eigenschaft der einzelnen problembeschreibungs Objekte beschreibt den hamiltonan für ein bestimmtes Quantum-Chemie Problem, indem er seine ein-und zwei Text Begriffe als sparsesrearrays von reellen Zahlen auflistet.
Die von den einzelnen problembeschreibungs-Objekten beschriebenen hamiltonan-Operatoren haben das Formular.

$ $ H = \sum \_ \{ i, j \} \sum \_ {\sigma\in \\ {\uparser, \downpfeil \\ }} h \_ \{ IJ \} a ^ \{ \dagger \} \_ {i, \sigma} a \_ {j, \sigma} + \frac {1} {2} \sum \_ \{ i, j, k, l \} \sum \_ {\sigma, \rho\in \\ {\uparser, \downpfeil \\ }} H \_ {IJKL} a ^ \dagger \_ {i, \sigma} a ^ \dagger \_ {k, \rho} a \_ {l, \rho} a \_ {j, \sigma}, $ $

Hier $h _ {IJKL} = (IJ | KL) $ in der Mulliken-Konvention.

Aus Gründen der Übersichtlichkeit lautet der Begriff mit einem-Elektronen

$ $ H_ {IJ} = \int {\mathrm d} x \psi ^ * \_ i (x) \left (\frac {1} {2} \nabla ^ 2 + \sum \_ {A} \bruchteil {z \_ A} {| x-x \_ A |}  \right) \psi \_ j (x), $ $

und der zwei-Elektronen-Begriff ist

$ $ h \_ \{ IJKL \} = \iint \{ \mathrm d \} x ^ 2 \psi ^ \{ \* \} \_ i (x \_ 1) \psi \_ j (x \_ 1) \frac \{ 1 \} \{ \| x \_ 1-x \_ 2 \| \} \psi \_ k ^ \{ \* \} (x \_ 2) \psi \_ l (x \_ 2).
$$

Wie in der Beschreibung der- [ `basis_set` Eigenschaft](#basis-set-object) der einzelnen Elemente der- `integral_sets` Eigenschaft erwähnt, wird explizit angenommen, dass die verwendeten Basisfunktionen einen echten Wert haben.
Dies ermöglicht es uns, die folgenden Symmetries zwischen den Begriffen zu verwenden, um die Darstellung der hamiltonan zu komprimieren.

$ $ H_ {IJKL} = H_ {IJLK} = H_ {jikl} = H_ {jilk} = H_ {klij} = H_ {klji} = H_ {lkij} = H_ {lkji}.
$$


#### <a name="contents"></a>Inhalte ####

Dieser Abschnitt ist normativ.

Jedes Problem Beschreibungs Objekt muss über eine Eigenschaft verfügen, `hamiltonian` deren Wert ein JSON-Objekt ist.
Der Wert der- `hamiltonian` Eigenschaft wird als "hamiltonan"-Objekt bezeichnet und muss über die Eigenschaften und verfügen, `one_electron_integrals` `two_electron_integrals` wie im restlichen Teil dieses Abschnitts beschrieben.

Jedes Problem Beschreibungs Objekt muss über eine Eigenschaft verfügen, `coulomb_repulsion` deren Wert ein einfaches Mengen Objekt ist.
Jedes Problem Beschreibungs Objekt muss über eine Eigenschaft verfügen, `energy_offet` deren Wert ein einfaches Mengen Objekt ist.
> Nebenbei Die Werte von und, die addiert werden, `coulomb_repulsion` `energy_offet` erfassen den Identitätsbegriff der hamiltonan.

##### <a name="one-electron-integrals-object"></a>One-Electron inteals-Objekt #####

Dieser Abschnitt ist normativ.

Die- `one_electron_integrals` Eigenschaft des hamiltonan-Objekts muss eine Array Menge mit geringer Dichte sein, deren Indizes zwei Ganzzahlen und deren Werte Ziffern sind.
Jeder Begriff muss über Indizes verfügen, `[i, j]` bei denen `i >= j` .

> Nebenbei Dies spiegelt die Symmetrie wider, die $h _ {IJ} = H_ {JI} $ liegt. Dies ist eine Folge der Tatsache, dass der hamiltonan hermitian ist.


###### <a name="example"></a>Beispiel ######

Dieser Abschnitt ist informativ.

Die folgende Menge an Sparse-Arrays repräsentiert die hamiltonan $ $ H = \left (-5,0 (a ^ \{ \dagger \} \_ {1, \uanrow} a \_ {1, \uparamerow} + a ^ \{ \dagger \} \_ {1, \downarrow} a \_ {1, \downarrow}) + 0,17 (a ^ \{ \dagger \} \_ {2, \uparamerow} a \_ {1, \uparamerow} + a ^ \{ \dagger \} \_ {1, \uanrow} a \_ {2, \uparamerow} + a ^ \{ \dagger \} \_ {2, \downarrow} a \_ {1, \downarrow} + a ^ \{ \dagger \} \_ {1, \downarrow} a \_ {2, \downarrow}) \right) \\ , \mathrm{ha}.
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
> Broombridge verwendet die 1-basierte Indizierung.


##### <a name="two-electron-integrals-object"></a>Two-Electron inteals-Objekt #####

Dieser Abschnitt ist normativ.

Die- `two_electron_integrals` Eigenschaft des hamiltonan-Objekts muss eine Array Menge mit geringer Dichte mit einer zusätzlichen Eigenschaft namens sein `index_convention` .
Jedes Element des Werts von `two_electron_integrals` muss über vier Indizes verfügen.

Jede `two_electron_integrals` Eigenschaft muss über eine `index_convention` Eigenschaft verfügen.
Der Wert der- `index_convention` Eigenschaft muss einer der zulässigen Werte sein, die in Tabelle 1 aufgeführt sind.
Wenn der Wert von `index_convention` auf festgestellt wird `mulliken` , `two_electron_integrals` muss ein Parser, der ein broombridge-Dokument lädt, für jedes Element der Menge an Sparse-Arrays einen "hamiltona"-Begriff instanziieren, der gleich dem zwei-Elektronen-Operator ist $h _ {i, j, k, l} a ^ \ dagger_i a ^ \ dagger_j a_k a_l $, wobei $i $, $j $, $k $ und $l $ ganzzahlige Werte von mindestens 1 sein müssen und wobei $h _ {i, j, k, l} $ das Element `[i, j, k, l, h(i, j, k, l)]` der Menge an geringer Dichte ist.

###### <a name="symmetries"></a>Symmetries ######

Dieser Abschnitt ist normativ.

Wenn die- `index_convention` Eigenschaft eines- `two_electron_integrals` Objekts gleich ist `mulliken` , dann, wenn ein Element mit Indizes `[i, j, k, l]` vorhanden ist, dürfen die folgenden Indizes nicht vorhanden sein, es sei denn, Sie sind gleich `[i, j, k, l]` :

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> Da die- `index_convention` Eigenschaft ein Objekt mit geringer Dichte ist, werden möglicherweise keine Indizes für verschiedene Elemente wiederholt.
> Insbesondere, wenn ein Element mit Indizes `[i, j, k, l]` vorhanden ist, kann kein anderes Element über diese Indizes verfügen.


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a>Beispiel #######

Dieser Abschnitt ist informativ.

Das folgende Objekt gibt den hamiltonan an.

$$ H = \frac12 \sum \_ {\sigma,\rho\in \\ {\uparrow,\downarrow \\ }}\Biggr( 1.6 a^{\dagger} \_ {1,\sigma} a^{\dagger} \_ {1,\rho} a \_ {1,\rho} a \_ {1,\sigma}- 0.1 a^{\dagger} \_ {6,\sigma} a^{\dagger} \_ {1,\rho} a \_ {3,\rho} a \_ {2,\sigma}- 0.1 a^{\dagger} \_ {6,\sigma} a^{\dagger} \_ {1,\rho} a \_ {2,\rho} a \_ {3,\sigma}- 0.1 a^{\dagger} \_ {1,\sigma} a^{\dagger} \_ {6,\rho} a \_ {3,\rho} a \_ {2,\sigma}- 0.1 a^{\dagger} \_ {1,\sigma} a^{\dagger} \_ {6,\rho} a \_ {2,\rho} a \_ {3,\sigma} $$ $$- 0.1 a^{\dagger} \_ {3,\sigma} a^{\dagger} \_ {2,\rho} a \_ {6,\rho} a \_ {1,\sigma}- 0.1 a^{\dagger} \_ {3,\sigma} a^{\dagger} \_ {2,\rho} a \_ {1,\rho} a \_ {6,\sigma}- 0.1 a^{\dagger} \_ {2,\sigma} a^{\dagger} \_ {3 , \rho} a \_ {6, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {2, \sigma} a ^ {\dagger} \_ {3, \rho} a \_ {1, \rho} a \_ {6, \sigma}\Biggr) \\ , \textrm{ha}.
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

### <a name="initial-state-section"></a>Abschnitt "Anfangszustand" ###

Dieser Abschnitt ist normativ.

Das `initial_state_suggestion` Objekt, dessen Wert ein JSON-Array ist, gibt die anfänglichen Quantum-Zustände an, die für die angegebene hamiltonan von Interesse sind. Jedes Element im Wert der- `initial_state_suggestion` Eigenschaft muss ein JSON-Objekt sein, das einen Quantenzustand beschreibt, wie im restlichen Teil dieses Abschnitts beschrieben.
Im restlichen Teil dieses Abschnitts verweist der Begriff "State Object" auf ein Element im Wert der- `initial_state_suggestion` Eigenschaft des broombridge-Objekts.

#### <a name="state-object"></a>State-Objekt ####

Dieser Abschnitt ist normativ.

Jedes Zustands Objekt muss über eine Eigenschaft verfügen, die `label` eine Zeichenfolge enthält. Jedes Zustands Objekt muss über eine- `method` Eigenschaft verfügen. Der Wert der- `method` Eigenschaft muss einer der zulässigen Werte sein, die in Tabelle 3 aufgeführt sind.
Jedes Zustands Objekt kann über eine Eigenschaft verfügen, `energy` deren Wert ein einfaches Mengen Objekt sein muss.

Wenn der Wert der- `method` Eigenschaft ist `sparse_multi_configurational` , muss das State-Objekt über eine-Eigenschaft verfügen, die `superposition` ein Array von Basis Zuständen und deren nicht normalisierte Verstärkung enthält.

Der anfängliche Status lautet z. b. $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) \ket $ $ $ {0} \ket{e} = \bruchteil {0,1 (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) + 0.2 (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {3, \uparrow}a ^ {\dagger} \_ {2, \downarrow})} {\sqrt{| 0,1 | ^ 2 + | 0,2 | ^ 2}} \ket {0} , $ $, wobei $ \ket{e} $ den Wert "Energy $0,987 \textrm{ha} $" hat, werden durch
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

Wenn der Wert der- `method` Eigenschaft ist `unitary_coupled_cluster` , muss das State-Objekt über eine-Eigenschaft verfügen, `cluster_operator` deren Wert ein JSON-Objekt ist.
Das JSON-Objekt muss über eine-Eigenschaft verfügen, `reference_state` deren Wert ein Basiszustand ist.
Das JSON-Objekt kann über eine `one_body_amplitudes` -Eigenschaft verfügen, deren Wert ein Array von Einzel Text Cluster-Operatoren und deren Verstärkung ist.
Das JSON-Objekt verfügt möglicherweise über eine `two_body_amplitudes` -Eigenschaft, deren Wert ein Array von zwei Text Cluster Operatoren und deren Verstärkung ist.
, das ein Array von Basis Zuständen und deren nicht normalisierte Verstärkung enthält.

Beispielsweise der Status $ $ \ket{\text{Reference}} = (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) \ket {0} , $ $

$ $ \ket{\text{UCCSD}} = e ^ {T-t ^ \dagger}\ket{\text{Reference}}, $ $

$ $ T = 0,1 a ^ {\dagger} \_ {3, \uparrow}a \_ {2, \downarrow} + 0,2 a ^ {\dagger} \_ {2, \uparrow}a \_ {2, \downarrow}-0,3 a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {3, \downarrow}a \_ {3, \uparrow}a \_ {2, \downarrow} $ $ wird dargestellt durch
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

#### <a name="basis-set-object"></a>Basis Objekt festlegen ####

Dieser Abschnitt ist normativ.

Jedes Problem Beschreibungs Objekt kann eine `basis_set` Eigenschaft aufweisen.
Falls vorhanden, muss der Wert der `basis_set` -Eigenschaft ein-Objekt mit zwei Eigenschaften, `type` und sein `name` .

Die Basisfunktionen, die durch den Wert der- `basis_set` Eigenschaft identifiziert werden, müssen einen echten Wert aufweisen.

> [!NOTE]
> Die Annahme, dass alle Basisfunktionen in Wirklichkeit sind, kann in zukünftigen Versionen dieser Spezifikation gelockert werden.

## <a name="tables-and-lists"></a>Tabellen und Listen ##

### <a name="table-1-allowed-physical-units"></a>Tabelle 1. Zulässige physische Einheiten ###

Dieser Abschnitt ist normativ.

Jede Zeichenfolge, die eine Einheit angibt, muss eine der folgenden sein:

- `hartree`
- `ev`

Parser und Producer müssen die folgenden einfachen Mengen Objekte als gleichwertig behandeln:

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a>Tabelle 2: Zulässige Index Konventionen ###

Dieser Abschnitt ist normativ.

Jede Zeichenfolge, die eine Index Konvention angibt, muss eine der folgenden sein:

- `mulliken`

Dieser Abschnitt ist informativ.

In zukünftigen Versionen dieser Spezifikation können zusätzliche Index Konventionen eingeführt werden.

#### <a name="interpretation-of-index-conventions"></a>Interpretation von Index Konventionen ####

Dieser Abschnitt ist informativ.

### <a name="table-3-allowed-state-methods"></a>Tabelle 3: Zulässige Zustands Methoden ###

Dieser Abschnitt ist normativ.

Jede Zeichenfolge, die eine Zustands Methode angibt, muss eine der folgenden sein:

- `sparse_multi_configurational`
- `unitary_coupled_cluster`

Dieser Abschnitt ist informativ.

Weitere Zustands Methoden können in zukünftigen Versionen dieser Spezifikation eingeführt werden.

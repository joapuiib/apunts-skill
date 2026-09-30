---
name: redaccio
description: Pràctiques d'escriptura per redactar o revisar apunts, exercicis i resums didàctics en valencià amb Markdown (MkDocs Material). Use when writing, rewriting or reviewing course notes, exercises or summaries, or when the user asks to "redactar", "reescriure" or make a text "més humà".
---

# Redacció d'apunts

## Llengua i to

Escriu en valencià normatiu i utilitza __sempre les formes occidentals o valencianes__:

| Utilitza                                            | En lloc de                          |
|-----------------------------------------------------|-------------------------------------|
| Subjuntiu en _-e_: _es connecte_, _estiga_, _puga_  | _es connecti_, _estigui_, _pugui_   |
| Primera persona en _-e_: _recomane_, _utilitze_     | _recomano_, _utilitzo_              |
| Incoatius en _-eix_: _defineix_, _serveix_         | _definix_, _servix_                 |
| Subjuntiu incoatiu en _-isca_: _oferisca_, _definisca_ | _ofereixi_, _defineixi_         |
| Possessius: _seua_, _teua_, _meua_                  | _seva_, _teva_, _meva_              |
| Infinitius: _tindre_, _vindre_, _vore_, _traure_    | _tenir_, _venir_, _veure_, _treure_ |
| Accentuació: _conéixer_, _anglés_, _francés_        | _conèixer_, _anglès_, _francès_     |
| Imperatius: _afig_, _llig_, _ix_                    | _afegeix_, _llegeix_, _surt_        |
| Participi de _ser_: _sigut_                         | _segut_                             |
| Lèxic: _eixida_, _hui_, _huit_, _xicotet_           | _sortida_, _avui_, _vuit_, _petit_  |

Adreça't a l'alumnat amb un to proper i didàctic. La persona verbal depén del tipus de text:

- __Apunts__: forma impersonal (_cal reiniciar_, _es pot consultar_, _s'observa que..._).
    Utilitza la primera persona del singular només per a opinions personals o experiències pròpies.
- __Enunciats d'exercicis__: imperatiu de segona persona del singular (_crea_, _comprova_, _afig_).

Escriu els termes en anglés en cursiva (_commit_, _loopback_). Si cal, afig la traducció
o l'original entre parèntesis: __Àrea de Preparació__ (_Staging Area_).

Utilitza sempre la mateixa paraula per a cada concepte:

| Utilitza      | En lloc de          |
|---------------|---------------------|
| _ordre_       | _comanda_           |
| _fitxer_      | _arxiu_             |
| _ferramenta_  | _eina_              |
| _només_       | _sols_              |

Utilitza llenguatge inclusiu, amb termes col·lectius o genèrics en lloc del masculí genèric:
_l'alumnat_ (no _els alumnes_), _el professorat_, _les persones usuàries_,
_l'equip de desenvolupament_ (no _els desenvolupadors_).

Escriu els números i les unitats en format català: espai entre el número i la unitat (_512 MB_,
_10 s_), coma decimal (_2,5_) i espai davant del percentatge (_25 %_). Dins del codi i de la
configuració, mantín el format que exigeix la ferramenta (`512MB`).

Declara les sigles com a abreviatures a l'inici del document perquè es mostre el significat:

```markdown
*[PR]: Pull Request
```

## Prosa

Redacta en prosa natural i explicativa. Evita els textos esquemàtics formats per fragments
d'una línia sense verbs.

Escriu paràgrafs curts, amb una sola idea per paràgraf (de 2 a 4 línies).

Explica el __perquè__ de les coses, no només el què.

Presenta cada concepte nou en negreta la primera vegada que apareix, seguit de la seua definició:
_Una __branca__ és una línia de desenvolupament independent._

Si un concepte es pot interpretar de més d'una manera, deixa clar a què es refereix.

Enllaça els paràgrafs amb connectors (_No obstant això_, _A més_, _Per tant_, _És a dir_,
_D'una altra banda_) perquè el text es llija de manera fluida.

No repetisques informació que ja apareix en una altra part del document: enllaça la secció
corresponent (_Vegeu [Canviar de branca](#canviar-de-branca)_).

Comença cada secció amb un paràgraf introductori abans de llistes, taules o blocs de codi.

Porta la informació tangencial o fora de l'abast del curs a una nota al peu (`[^1]`).

## Format

Ressalta en negreta les idees clau, els paràmetres i els valors importants.
Utilitza la sintaxi `__text__`, no `**text**`.

Escriu les ordres, fitxers, paràmetres i valors com a `codi`.

Limita les línies a uns 100-110 caràcters. Dins de les llistes, indenta les continuacions amb 4 espais.

Indica sempre el llenguatge dels blocs de codi (`bash`, `sql`, `ini`, `yaml`, `text`...).

Utilitza una cita (`>`) per a aclariments breus dins d'una llista o just després d'un bloc de codi:

```markdown
- Són creades a partir de la branca `develop`.

    > No necessàriament en el mateix punt de la història.
```

Acompanya els noms de productes i ferramentes amb la seua icona quan en tinga (`:simple-git: Git`).

## Blocs de codi

Escriu els comentaris del codi en valencià.

Quan mostres l'eixida d'una ordre, distingeix clarament l'ordre de l'eixida:

- Utilitza `shellconsole` amb el _prompt_ quan hi ha una seqüència d'ordres de terminal.
- Utilitza un bloc `/// html | div.result` just després de l'ordre per mostrar-ne el resultat,
    especialment per a consultes SQL o ordres amb una eixida extensa:

````markdown
```sql
SELECT current_user, current_database();
```
/// html | div.result
```text
 current_user | current_database
--------------+------------------
 postgres     | postgres
```
///
````

No incloguis mai contrasenyes, claus ni dades reals: utilitza valors d'exemple.

## Capçaleres

Divideix el contingut amb capçaleres `##`, `###` i `####` perquè la taula de continguts siga útil.
Un document amb una sola entrada a la taula de continguts està mal dividit.

Utilitza capçaleres curtes i descriptives. Si una secció explica una ordre, indica-la
entre parèntesis: `## Inicialització d'un repositori (`git init`)`.

## Llistes

Utilitza llistes quan cada element té una explicació real. Cada element comença amb el terme
en negreta, seguit de dos punts i la descripció. Després dels dos punts, escriu en __minúscula__
(excepte si és una cita textual), i mantín el mateix criteri en tot el document:

```markdown
- __Còpia de seguretat__: un repositori remot pot servir com a còpia de seguretat del projecte.
- __`parametre`__: explicació breu del paràmetre i del seu valor per defecte.
```

Per a procediments, utilitza una llista numerada amb un pas per element. Si un pas inclou
codi, posa'l dins de l'element, indentat.

## Paràmetres i opcions

No incloguis frases «Per exemple, ...» dins de la definició d'un paràmetre. Documenta els valors
possibles en una admonició desplegable just baix de l'element, amb una taula:

```markdown
- __`parametre`__: explicació breu.

    ??? info "Valors de `parametre`"

        | Valor    | Significat                      |
        |----------|---------------------------------|
        | `valor1` | Descripció amb la __idea clau__ |
        | `valor2` | Descripció amb la __idea clau__ |
```

Després de la llista, inclou un exemple de configuració real en un bloc de codi.

## Ordres

Explica cada ordre seguint aquest ordre:

1. Un paràgraf que explica què fa l'ordre i per a què serveix.
2. La sintaxi, amb `<argument>` per als valors obligatoris i `[opció]` per als opcionals.
3. Una llista amb cada opció o argument; indica els opcionals amb _(opcional)_.
4. Un enllaç a la documentació oficial en una admonició `docs`.
5. Un exemple desplegable.

````markdown
Per mostrar les branques d'un repositori, s'utilitza l'ordre:

```bash
ordre [-o | --opcio] <argument>
```

- `[-o | --opcio]`: (opcional) què fa l'opció.
- `<argument>`: què representa l'argument.

!!! docs "Documentació oficial: [:octicons-link-external-16: `ordre`](https://...) – :simple-git: Git"
````

Si l'admonició `docs` només té un enllaç, posa'l en el títol amb el format següent:

```markdown
!!! docs "Documentació [oficial]: [:octicons-link-external-16: Títol](https://...) – Font"
```

Afig _oficial_ només si l'enllaç apunta a la documentació oficial de la ferramenta o del tema.

Posa cada enllaç a la documentació en l'apartat que documenta (per exemple, `CREATE TABLESPACE`
en l'apartat de creació i `DROP TABLESPACE` en el d'eliminació), i no agrupes al final d'una secció
enllaços d'apartats diferents.

Si un mateix apartat té diversos enllaços, utilitza un títol genèric i una llista d'enllaços en el cos:

````markdown
!!! docs "Documentació oficial de :simple-git: Git"
    - [:octicons-link-external-16: `ordre1`](https://...)
    - [:octicons-link-external-16: `ordre2`](https://...)
````

Quan hi ha diverses alternatives equivalents (terminal o entorn gràfic, diverses tècniques),
presenta-les en pestanyes:

```markdown
=== ":octicons-terminal-24: Terminal"
    ...

=== ":material-microsoft-visual-studio-code: VS Code"
    ...
```

## Exemples

Escriu els exemples en una admonició desplegable amb el títol `Exemple: ...`.
Introdueix-los amb una frase, mostra el codi o el resultat i explica després què s'observa
(_S'observa que..._, _Es pot comprovar que..._):

````markdown
??? example "Exemple: Mostrar les branques"
    Es mostren les branques del repositori.

    ```shellconsole
    ...
    ```

    S'observa que només hi ha una branca, anomenada `main`.
````

Mantín els exemples consistents, almenys dins d'un mateix document: utilitza el mateix escenari
(el mateix repositori, base de dades, noms i valors) i dades realistes, de manera que cada exemple
continue l'anterior.

Per comentar línies concretes d'un bloc de codi, utilitza anotacions (`# (1)!`) amb una
llista numerada just després del bloc.

## Admonicions

Escriu admonicions per complementar la informació exposada.

No abuses de les admonicions: si gairebé cada paràgraf en porta una, deixen de destacar.
Utilitza-les només per a informació que complementa o adverteix; les explicacions principals
van en el text.

Si l'admonició és d'una sola línia, inclou el text en el títol i no escrigues cos:

```markdown
!!! important "Contingut de l'avís, amb __negreta__ i `codi` si cal."
```

No escrigues mai un títol genèric seguit d'una sola línia de cos. L'excepció són les solucions
desplegables (`??? solution`), on el cos amaga la resposta.

Si necessita més detall (codi, una consulta, una llista), posa el missatge principal
al títol i el detall al cos:

````markdown
!!! warning "Tingues en compte els següents aspectes:"
    - Primer aspecte.
    - Segon aspecte.
````

Si la mateixa informació afecta diversos elements, agrupa-la en una sola admonició
en lloc de repetir-la a cada element.

Tria el tipus segons la intenció:

| Tipus       | Ús                                                  |
|-------------|-----------------------------------------------------|
| `important` | Informació que no es pot passar per alt             |
| `info`      | Informació complementària o valors possibles        |
| `note`      | Matisos o aclariments                               |
| `tip`       | Trucs i dreceres                                    |
| `recommend` | Recomanacions i bones pràctiques                    |
| `warning`   | Errors habituals o comportaments inesperats         |
| `danger`    | Accions perilloses o irreversibles                  |
| `example`   | Exemples, amb el codi i una explicació del resultat |
| `prep`      | Preparació de l'entorn per als exemples             |
| `docs`      | Enllaços a la documentació oficial                  |
| `solution`  | Solucions dels exercicis                            |

Utilitza `???` (desplegable) per al contingut opcional o extens, com exemples, taules de valors,
preparacions o solucions, i `!!!` per al que s'ha de llegir sempre.

## Blocs d'una línia

Si un bloc `///` només té una línia de contingut, escriu-lo en una sola línia:

```markdown
/// figure-caption | #figure-id : Text de la llegenda.
```

en lloc de:

```markdown
/// figure-caption
Text de la llegenda.
///
```

## Figures

Acompanya cada imatge amb una llegenda (`figure-caption`). Si la imatge és una captura de pantalla,
utilitza `shadow-figure-caption`. Si és d'una altra autoria, indica-la amb `attribution`.

Escriu un text alternatiu que descriga la imatge. Normalment serà el mateix text que la llegenda.

Si la imatge té versió clara i fosca, inclou totes dues:

```markdown
![Descripció](img/nom.light.png#only-light)
![Descripció](img/nom.dark.png#only-dark)
/// figure-caption | #figure-nom : Descripció amb `codi` si cal.
```

Referencia les figures des del text amb el seu identificador: `[Figura 1](#figure-nom)`.

## Enllaços

Marca els enllaços externs amb la icona `:octicons-link-external-16:` i indica la font al final:

```markdown
[:octicons-link-external-16: Títol de l'article](https://...) – Nom de la font
```

Agrupa les lectures complementàries en una admonició `!!! info "Més informació"`.

Si un enllaç es repeteix o és molt llarg, utilitza enllaços de referència (`[text][ref]`)
i defineix `[ref]: url` just després del paràgraf.

## Exercicis

Escriu els enunciats en imperatiu de segona persona del singular.

Divideix l'exercici en passos numerats, amb un sol objectiu per pas.

Inclou les solucions en una admonició desplegable:

````markdown
1. Crea una base de dades anomenada `botiga`.

    ??? solution "Solució"
        ```sql
        CREATE DATABASE botiga;
        ```
````

## Revisió

Mantín el contingut tècnic original: no inventes paràmetres, valors ni comportaments.

Corregeix els errors ortogràfics i gramaticals, com les formes no valencianes (_seva_ per _seua_),
l'apostrofació (_de Incorporació_ per _d'Incorporació_) o els castellanismes.

En acabar, indica quins continguts nous has afegit perquè es puguen validar.

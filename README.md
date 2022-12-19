# Egyptian Arabic (arz)

This repo contains the inflection tables for Egyptian Arabic (ISO 639-3 `arz`)

## Contents
- `arz`: entries based on lemmas that appear in the Egyptian Penn Arabic
  Treebank (ARZATB).
- `arz.args`: a UniMorph 4.0 compatible verion of `arz`
- `arz.gloss`: English glosses for the lemmas in `arz`.
- `README.md`: this file.

#

## `arz`

### Generation of the lemma inflections
- The inflections of all the lemmas were generated through the CamelTools morphological generator component
  ([demo](https://calimastar.abudhabi.nyu.edu/generator),
  [API](https://camel-tools.readthedocs.io/en/latest/api/morphology/generator.html))
  ([Obeid et al., 2020](https://www.aclweb.org/anthology/2020.lrec-1.868v2.pdf)).
  The morphological database used is
  CALIMA-ARZ ([Habash et al., 2012](https://www.aclweb.org/anthology/W12-2301.pdf)). The
  CALIMA-ARZ database was designed as an analyzer and not a generator, and some
  portions of it came through imperfect automatic extensions. As a result, it
  over generated implausible forms. We used Morph/POS statistics from ARZATB to
  eliminate incorrect forms as much as possible.
- The POS and morphological features are then mapped to UniMorph according to
  the current [schema](https://unimorph.github.io/doc/unimorph-schema.pdf)
  (Sylak-Glassman 2016).
- The core POS of the lemmas are Verbs, Nouns, and Adjectives.
- The total number of lemmas is 6,347, with the following POS distribution:
    - `V`: 1,323 (20.8%) lemmas
    - `N`: 3,248 (51.2%) lemmas
    - `ADJ`: 1,776 (28.0%) lemmas

### Source
- Egyptian Penn Arabic
  Treebank (ARZATB): All the lemmas in both ARZATB ([Maamouri et al., 2014](http://www.lrec-conf.org/proceedings/lrec2014/pdf/1145_Paper.pdf))
      and in CALIMA-ARZ.

### Notes on Tokenization and Diacritization
- Clitics were not included or marked in the inflection tables. The only clitic
  included is the determiner `Al+` in order to be consistent with the ARZATB.
- All the lemmas and the inflected forms are fully diacritized following the
  same convention in the ARZATB. Removing all the diacritics is straightforward and
  can be done through a simple regex. Alternatively, CamelTools provides a
  dediacritization utility: an
  [API](https://camel-tools.readthedocs.io/en/latest/api/utils/dediac.html)
 and a [CLI](https://camel-tools.readthedocs.io/en/latest/cli/camel_dediac.html).

### Notes on POS decisions
  - All nominals with `Al+` will be tagged with `DEF` for definiteness. All
    nominals without `Al+` will be repeated twice: once as `INDF` and once as
    `PSSD`. That is because in most cases possession marking is not
    overt due to the orthography.
  - All verbs are by default in the active voice.

## Annotators
Salam Khalifa and Nizar Habash ([CAMeL Lab](www.camel-lab.com) @ NYU Abu Dhabi)

## Paradigm Samples

The complete inflection table for the verb lemma سِمِع _'listen'_
```
سِمِع	اَسْمَع	V;IPFV;SG;1
سِمِع	اِسْمَع	V;MASC;IMP;SG;2
سِمِع	اِسْمَعُوا	V;MASC;IMP;PL;2
سِمِع	اِسْمَعِي	V;FEM;IMP;SG;2
سِمِع	تِسْمَع	V;IPFV;MASC;SG;2
سِمِع	تِسْمَع	V;IPFV;FEM;SG;3
سِمِع	تِسْمَعُوا	V;IPFV;MASC;PL;2
سِمِع	تِسْمَعِي	V;IPFV;FEM;SG;2
سِمِع	سِمِع	V;PFV;MASC;SG;3
سِمِع	سِمِعت	V;PFV;SG;1
سِمِع	سِمِعت	V;PFV;MASC;SG;2
سِمِع	سِمِعتُوا	V;PFV;MASC;PL;2
سِمِع	سِمِعتِي	V;PFV;FEM;SG;2
سِمِع	سِمِعنا	V;PFV;PL;1
سِمِع	سِمْعُوا	V;PFV;MASC;PL;3
سِمِع	سِمْعِت	V;PFV;FEM;SG;3
سِمِع	نِسْمَع	V;IPFV;PL;1
سِمِع	يِسْمَع	V;IPFV;MASC;SG;3
سِمِع	يِسْمَعُوا	V;IPFV;MASC;PL;3
```


The complete inflection table for the adjective lemma كُوَيِّس _'good'_
```
كُوَيِّس	الكُوَيِّس	ADJ;DEF;MASC;SG
كُوَيِّس	الكُوَيِّسَة	ADJ;DEF;FEM;SG
كُوَيِّس	الكُوَيِّسِين	ADJ;DEF;MASC;PL
كُوَيِّس	كُوَيِّس	ADJ;INDF;MASC;SG
كُوَيِّس	كُوَيِّس	ADJ;MASC;SG;PSSD
كُوَيِّس	كُوَيِّسَة	ADJ;INDF;FEM;SG
كُوَيِّس	كُوَيِّسَة	ADJ;FEM;SG;PSSD
كُوَيِّس	كُوَيِّسِين	ADJ;INDF;MASC;PL
كُوَيِّس	كُوَيِّسِين	ADJ;MASC;PL;PSSD

```

## License
- [Creative Commons Attribution-ShareAlike 3.0 Unported (CC BY-SA 3.0)](https://creativecommons.org/licenses/by-sa/3.0/)

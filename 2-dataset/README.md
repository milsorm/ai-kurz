# Příprava cvičného datasetu

Vyšel jsem z jednoduché produktové brožury naší společnosti, abych získal nějaké marketingové texty.
Jsou málo kvalitní, plné zbytečných obrázků a referencí, které se pro účel datasetu nehodí, ale
mají rozumně malý rozsah pro cvičný dataset.

Při produkci bych si vzal raději firemní knowledgebase, vypracoval k tomu velký slovník faktů
a vztahů, terminologický slovníček a vnitřní popisy fungování. A to bych použil jako základ pro
přípravu nějakého datasetu, stejně jako třeba pro RAG.

## Zdrojová data

> 1-brozura.pdf

## Rozborka do textu

Nechal jsem ChatGPT vytáhnout relevantní pasáže textu, odstranit formátovací problémy (rozdělená
slova na konci řádků, zbytečné marketingové pasáže, reference, odkazy na firmu apod.). Ve výsledku
vznikl poměrně krátký faktový soubor.

> 2-prevod_do_textu.md

## Příprava datasetu

Nechal jsem ChatGPT postupně vytvářet dataset nad tímto zdrojovým souborem. Cílem bylo ptát se 
na jednotlivé věci několika různými způsoby. Postupně jsem nechal měnit způsob tvořených otázek
- chtěl jsem nejen dotazy na fakta, ale i na souvislosti a z pohledu různých typů uživatelů.
Cílem bylo si vyzkoušet, zda se dá LLM model použít pro generování datasetu z různých úhlů pohledu
a tím připravit kvalitnější vstupní páry.

Formát jsem ChatGPT předepsal na jednoduché dvojice v roli user a assistent a uložit jako JSONL.

Celkem 8 různých fragmentních souborů s jednotlivými pokusy jsem pak složil za sebe pomocí shellu.

> 3-zakladni_pary.jsonl

## Výsledek

Soubor se základními páry se dá použít jako fine tuning dataset. Není dokonalý, ale to vzhledem
k rozsahu vstupních dat je maximum, co lze z něj vytáhnout. Dále bych musel vzít větší rozsahy textů,
aby bylo možné vytvořit smysluplnější dialogy a otázky pro trénování.

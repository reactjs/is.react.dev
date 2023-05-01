---
title: Uppsetning á ritli
---

<Intro>

Það getur haft mikið að segja að hafa ritilinn sinn almennilega uppsettan, enda getur hann hjálpað við að finna villur jafnóðum og kóðinn er skrifaður. Við erum með nokkrar tillögur handa þeim sem hafa áhuga á að breyta stillingunum fyrir ritilinn sinn.

</Intro>

<YouWillLearn>

* Hvaða ritlar eru vinsælastir
* Hvernig er hægt að sníða kóðann sjálfvirkt

</YouWillLearn>

## Ritillinn þinn {/*your-editor*/}

[VS Code](https://code.visualstudio.com/) er á meðal allravinsælustu ritla í notkun. Margar viðbætur eru í boði og ritillinn samtengist vel vinsælum þjónustum eins og GitHub. Flest þau sérkenni sem útlistuð eru á þessari síðu eru studd og hann er auðstillanlegur.

Á meðal annarra vinsælla ritla við React þróun má nefna:

* [WebStorm](https://www.jetbrains.com/webstorm/) er samþætt þróunarumhverfi (e. IDE) sérhannað fyrir JavaScript.
* [Sublime Text](https://www.sublimetext.com/) er með innbyggðan stuðning fyrir JSX og TypeScript, [litakóðun fyrir málskipan](https://stackoverflow.com/a/70960574/458193), og sjálfvirkar útfyllingar á kóða.
* [Vim](https://www.vim.org/) er einstaklega stillanlegur ritill sem var upphaflega þróaður til að gera hvers lags textavinnslu skilvirka. Fyrirrennari þess, „vi“, er innifalinn í flestum UNIX stýrikerfum, m.a. macOS.

## Ritlasérkenni sem mælt er með {/*recommended-text-editor-features*/}

Sumir ritlar eru með þessi sérkenni innbyggð, en aðrir gætu karfist utanaðkomandi viðbótar. Athugaðu ritillinn þinn styður til að vera viss!

### Lóarar (e. linter) {/*linting*/}

Lóarar finna vandamál í kóðanum á meðan þú skrifar hann og hjálpa þér að leysa þau sem fyrst. [ESLint](https://eslint.org/) er lóari fyrir JavaScript sem er opinn hugbúnaður.

* [Innsettu ESLint með þeim stillingum sem mælt er með fyrir React](https://www.npmjs.com/package/eslint-config-react-app) (gakktu úr skugga um að [Node.js sé uppsett!](https://nodejs.org/en/download/current/))
* [Notaðu ESLint í VS Code með opinberu viðbótinni](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)

**Gakktu úr skugga um að allar reglurnar í [`eslint-plugin-react-hooks`](https://www.npmjs.com/package/eslint-plugin-react-hooks) séu í notkun.** Þær eru bráðnauðsynlegar og hjálpa þér að finna allar vandamestu villurnar strax.

### Forsnið {/*formatting*/}

Það síðasta sem flestir vilja standa í þegar unnið er að kóða í sameiningu með öðrum er að lenda í deilum um [dálkhök og bil](https://www.google.com/search?q=tabs+vs+spaces)! Sem betur fer erum við með [Prettier](https://prettier.io/) sem getur hreinsað kóðan þinn með því að sníða hann eftir ákveðnum stillingum. Keyrðu Prettier og það mun breyta öllum dálkhökum í bil–og inndrátturinn, gæsalappir, o.s.frv. verður breytt í samræmi við stillingarnar. Það er upplagt að stilla ritilinn þannig að Prettier keyri sjálfvirkt þegar þú vistar skrá.

Þú getur innset [Prettier viðbótina í VS Code](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) með því að fylgja þessum leiðbeiningum:

1. Ræstu VS Code
2. Notaðu flýtivalmynd (ýttu á `CTRL/CMD + P`)
3. Límdu `ext install esbenp.prettier-vscode`
4. Ýttu á færslulykil

#### Að sníða sjálfvirkt við vistun {/*formatting-on-save*/}

Það er ákjósanlegt að sníða kóða sjálfvirkt þegar hann er vistaður. VS Code er með stillingu til þess að gera þetta!

1. Í VS Code, ýttu á `CTRL/CMD + SHIFT + P`
2. Skrifaðu „settings“
3. Ýttu á færslulykil
4. Skrifaðu „format on save“ í leitinni
5. Hakaðu við „format on save“

> Ef þú ert með ESLint uppsett þá gætirðu lent í því að stillingar þess séu ekki í samræmi við stillingarnar á Prettier. Það er mælt með að afstilla allar sniðsstillingar í ESLint með því að nota [`eslint-config-prettier`](https://github.com/prettier/eslint-config-prettier) og þá kannar ESLint bara notkunarvillur. Notaðu [`prettier --check`](https://prettier.io/docs/en/cli.html#--check) í prófanaferlinu til að sjá um að allar skrár séu sniðnar sjálfvirkt áður en kóðagrein er tvinnuð.

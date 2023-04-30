---
title: Fyrstu skref
---

<Intro>

Velkomin í skjalbúnað Reacts! Þessi síða veitir innsýn í öll þau helstu hugtök sem þú þarft að kunna skil á til að geta notað React dagsdaglega.

</Intro>

<YouWillLearn>

- Að búa til og falda íhluti
- Að bæta við ívafi og stílum
- Að birta gögn
- Að ganga frá skilyrðum og listum
- Að bregðast við atburðum og uppfæra skjáinn
- Að deila gögnum á milli íhluta

</YouWillLearn>

## Gerð og földun íhluta {/*components*/}

React forrit eru gerð úr *íhlutum*. Íhlutur er hluti úr viðmótinu sem hefur sína eigin virkni og útlit. Íhlutur getur verið eins lítill og takki, eða eins stór og heil síða.

Íhlutir í React eru JavaScript föll sem skila ívafi:

```js
function TakinnMinn() {
  return (
    <button>
      Ég er takki
    </button>
  );
}
```

Nú þegar þú hefur skilgreint fallið `TakkinnMinn`, geturðu faldað hann inn í annan íhlut.

```js {5}
export default function Forrit() {
  return (
    <div>
      <h1>Velkomin í forritið mitt</h1>
      <TakkinnMinn />
    </div>
  );
}
```

Taktu eftir því að `<TakkinnMinn />` hefst á stórum staf. Það er þannig sem þú veist að þetta er React íhlutur. HTML merki eru alltaf í lágstöfum en React íhlutir verða alltaf að byrja á hástafi.

Sjáum nú hvað kemur út úr þessu:

<Sandpack>

```js
function TakkinnMinn() {
  return (
    <button>
      Ég er takki
    </button>
  );
}

export default function Forrit() {
  return (
    <div>
      <h1>Velkomin í forritið mitt</h1>
      <TakkinnMinn />
    </div>
  );
}
```

</Sandpack>

Setningin `export default` tilgreinir aðalíhlutinn í skrá. Ef þú kannast ekki við eitthvað í málskipan JavaScripts þá getur skjalbúnaðurinn á [MDN](https://developer.mozilla.org/en-US/docs/web/javascript/reference/statements/export) og [javascript.info](https://javascript.info/import-export) verið nytsamlegur.

## Gerð ívafs með JSX {/*writing-markup-with-jsx*/}

Ívafsmálskipanin sem þú kynntist að ofan heitir *JSX*. Notkun hennar er valkvæð, en langflest React verkefni nota JSX vegna þess að það er hentugra en að sleppa því. Öll [tólin sem við mælum með fyrir staðbundna þróun](/learn/installation) styðja JSX án frekari uppsetningar.

JSX er strangari en HTML. Þú verður að loka öllum merkjum eins og `<br />`. Íhlutirnir þínir geta ekki heldur skilað mörgum JSX merkjum. Þú verður að falda þeim í sameiginlegt yfirmerki, eins og `<div>...</div>` eða tómt `<>...</>` brot:

```js {3,6}
function UpplýsingaSíða() {
  return (
    <>
      <h1>Um okkur</h1>
      <p>Halló.<br />Hvað er títt?</p>
    </>
  );
}
```

Ef þú ert með mjög mikið HTML sem þarf að flytja yfir í JSX þá geturðu notað [vefþýðanda](https://transform.tools/html-to-jsx) til að einfalda verkið.

## Stílar {/*adding-styles*/}

Í React er klasi tilgreindur með `className`. Það virkar á sama máta og [klasaeigindið](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/class) í HTML:

```js
<img className="gengill" />
```

Þá geturðu skrifað CSS reglurnar í sér skrá:

```css
/* Í CSS skrá */
.gengill {
  border-radius: 50%;
}
```

React er ekki með neina tiltekna stefnu varðandi CSS skrár og skipar þér ekki fyrir hvernig skuli notar þær. Í einfaldasta tilfellinu bætirðu við [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link) merki í HTML kóðanum þínum. Ef þú notar tól til að smíða kóðann þinn, eða forritasafn, skaltu athuga skjalbúnað þess til að kynna þér hvernig sé best að bæta við CSS skrám í verkefnið þitt.

## Að birta gögn {/*displaying-data*/}

JSX gerir þér kleift að láta ívaf beint inn í JavaScript. Með slaufusvigum geturðu „sloppið aftur“ í JavaScript til að ívefja breytu úr kóðanum og sýna notandanum. Til dæmis birtir þetta gildi `notandi.nafn`:

```js {3}
return (
  <h1>
    {notandi.nafn}
  </h1>
);
```

Þú getur líka „sloppið inn í JavaScript“ í gegnum JSX eigind, en þú verður að nota slaufusviga *í stað* gæsalappa. Til dæmis flytur `className="gengill"` út `"gengill"` strenginn sem CSS klasa, en `src={notandi.gengilsVeffang}` les JavaScript gildið úr breytunni `notandi.gengilsVeffang` og flytur það svo inn í `src` eigindið.

```js {3,4}
return (
  <img
    className="gengill"
    src={notandi.gengilsVeffang}
  />
);
```

Þú getur látið flóknara segðamál inn í JSX slaufusvigana líka, til dæmis [strengjasamskeytingu](https://javascript.info/operators#string-concatenation-with-binary):

<Sandpack>

```js
const notandi = {
  nafn: 'Hedy Lamarr',
  gengilsVeffang: 'https://i.imgur.com/yXOvdOSs.jpg',
  gengilsStærð: 90,
};

export default function Umgjörð() {
  return (
    <>
      <h1>{notandi.nafn}</h1>
      <img
        className="gengill"
        src={notandi.gengilsVeffang}
        alt={'Ljósmynd af ' + notandi.nafn}
        style={{
          width: notandi.gengilsStærð,
          height: notandi.gengilsStærð
        }}
      />
    </>
  );
}
```

```css
.gengill {
  border-radius: 50%;
}

.stor {
  border: 4px solid gold;
}
```

</Sandpack>

Í dæminu að ofan er `style={{}}` ekki sérstök málskipan, heldur venjulegur `{}` hlutur innan `style={ }` JSX slaufusviga. Þú getur notað `style` eigindið þegar stíllinn veltur á JavaScript breytum.

## Skilyrt birting {/*conditional-rendering*/}

Í React er engin sérstök málskipan til að skrifa skilyrtar setningar. Þess í stað notarðu sömu aðferðir og í venjulegum JavaScript kóða. Til dæmis geturðu notað [`if`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else) setningu til að birta JSX skilyrt:

```js
let efni;
if (erInnskráður) {
  efni = <Mælaborð />;
} else {
  efni = <Innskráning />;
}
return (
  <div>
    {efni}
  </div>
);
```

Ef þér þykir styttri kóði betri þá geturðu notað [skilyrtan `?` virka.](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator) Ólíkt `if` setningunni má nota hann beint inni í JSX:

```js
<div>
  {erInnskráður ? (
    <Mælaborð />
  ) : (
    <Innskráning />
  )}
</div>
```

Þegar þú þarft á skilyrta stökkinu `else` að halda geturðu líka notað styttri [`&&` rökaðgerð](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_AND#short-circuit_evaluation):

```js
<div>
  {erInnskráður && <Mælaborð />}
</div>
```

Þessar nálganir virka líka til að tilgreina eigind skilyrt. Ef þú kannast ekki við þessa JavaScript málskipan þá geturðu byrjað á að nota alltaf `if...else`.

## Listar {/*rendering-lists*/}

Til að birta lista af einingum muntu geta notfært þér JavaScript eiginleika eins og [`for` lykkjur](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for) og [`map()` fallið](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map).

Gefum okkur að þú sért með vörulista:

```js
const vörur = [
  { nafn: 'Kál', kennimerki: 1 },
  { nafn: 'Hvítlaukur', kennimerki: 2 },
  { nafn: 'Epli', kennimerki: 3 },
];
```

Notaðu `map()` fallið inni í íhlutnum þínum til að umbreyta vörulistanum úr fylki af hlutum í fylki af `<li>` merkjum:

```js
const stök = vörur.map(vara =>
  <li key={vara.kennimerki}>
    {vara.nafn}
  </li>
);

return (
  <ul>{stök}</ul>
);
```

Taktu eftir því að `<li>` er með `key` eigind. Fyrir hvert stak í listanum þarftu að tilgreina streng eða númer sem lykil hlutsins í listanum. Venjulega kemur lykill beint úr gögnunum þínum, til dæmis kennimerki úr gagnagrunni.
React notar lyklana til að vita hvað gerðist ef þú síðar bætir við, eyðir, eða endurraðar stökum.

<Sandpack>

```js
const vörur = [
  { nafn: 'Kál', erÁvöxtur: false, kennimerki: 1 },
  { nafn: 'Hvítlaukur', erÁvöxtur: false, kennimerki: 2 },
  { nafn: 'epli', erÁvöxtur: true, kennimerki: 3 },
];

export default function Innkaupalisti() {
  const atriði = vörur.map(vara =>
    <li
      key={vara.kennimerki}
      style={{
        color: vara.erÁvöxtur ? 'magenta' : 'darkgreen'
      }}
    >
      {vara.nafn}
    </li>
  );

  return (
    <ul>{atriði}</ul>
  );
}
```

</Sandpack>

## Að bregðast við atburðum {/*responding-to-events*/}

Þú getur brugðist við atburðum með því að skilgreina *sýslaraföll* inni í íhlutunum þínum:

```js {2-4,7}
function TakkinnMinn() {
  function sýslaSmell() {
    alert('Þú smelltir á mig!');
  }

  return (
    <button onClick={sýslaSmell}>
      Smelltu á mig
    </button>
  );
}
```

Taktu eftir því að `onClick={sýslaSmell}` er ekki með sviga á endanum. Ekki _kalla_ á sýslarafallið: þú þarft aðeins að *senda það*. React mun sjá um að kalla á sýslarafallið þitt þegar notandinn smellir á takkann.

## Uppfærslur á skjánum {/*updating-the-screen*/}

Stundum vill maður uppfæra íhlut til að „muna“ einhverjar tilteknar upplýsingar og svo birta þær. Til dæmis gætirðu mögulega viljað telja hversu oft er smellt á einhvern takka. Til að gera þetta geturðu bætt *stöðu* við íhlutinn.

Fyrst skaltu flytja inn [`useState`](/reference/react/useState) úr React:

```js
import { useState } from 'react';
```

Þá geturðu skilgreint *stöðubreytu* inni í íhlutnum:

```js
function TakkinnMinn() {
  const [smellir, setjaSmelli] = useState(0);
  // ...
```

Þú færð tvö stök úr `useState`: núverandi stöðu (`smellir`) og fallið sem gerir þér kleift að uppfæra gildið (`setjaSmelli`). Þú getur notað hvaða breytunöfn sem er, en venjan er að skrifa `[eitthvað, setjaEitthvað]`.

Breytan `smellir` verður `0` í fyrsta skiptið sem takkinn er birtur vegna þess að þú sendir `0` í `useState()`. Kallaðu `setjaSmelli` þegar þú vilt breyta stöðu og sendu nýja gildið. Með því að smella á þennan takka uppfærist teljarinn:

```js {5}
function TakkinnMinn() {
  const [smellir, setjaSmelli] = useState(0);

  function sýslaSmell() {
    setjaSmelli(smellir + 1);
  }

  return (
    <button onClick={sýslaSmell}>
      Smellti í {smellir} skipti
    </button>
  );
}
```

React mun kalla á fallið þitt aftur. Breytan `smellir` mun í þetta sinn mun hafa gildið `1`, svo mun það vera `2`, og svo koll af kolli.

Ef þú birtir sama íhlut oftar en einu sinni þá mun hver birting hafa sína eigin stöðu. Prófaðu að smella á hvorn takkan:

<Sandpack>

```js
import { useState } from 'react';

export default function Forrit() {
  return (
    <div>
      <h1>Teljarar með aðskildri stöðu</h1>
      <TakkinnMinn />
      <TakkinnMinn />
    </div>
  );
}

function TakkinnMinn() {
  const [smellir, setjaSmelli] = useState(0);

  function sýslaSmell() {
    setjaSmelli(smellir + 1);
  }

  return (
    <button onClick={sýslaSmell}>
      Smellti í {smellir} skipti
    </button>
  );
}
```

```css
button {
  display: block;
  margin-bottom: 5px;
}
```

</Sandpack>

Taktu eftir því að hver takki „man“ stöðuna á eigin breytu (þ.e. `smellir`) og hefur ekki áhrif á hinn takkann.

## Notkun króka {/*using-hooks*/}

Föll með forskeytinu `use` (þ.e. „nota“) eru kölluð *krókar*. `useState` er innbyggður krókur frá React. Þú getur fundið fleiri innbyggða króka í [forritaskilum.](/reference/react) Þú getur einnig skrifað þína eigin króka frá grunni eða með því að sameina aðra króka.

Krókar eru háðir ákveðnum kvöðum í samanburði við venjuleg föll. Þú getur aðeins kallað í króka *efst* í íhlutunum þínum eða efst í öðrum krókum. Ef þú vilt nota `useState` í skilyrtri setningu eða lykkju skaltu þátta það í nýjan íhlut.

## Að deila gögnum á milli íhluta {/*sharing-data-between-components*/}

Í síðasta dæmi hafði hver `TakkinnMinn` sitt eigið gildi fyrir `smellir` breytuna og aðeins gildi þess takka sem smellt var á uppfærðist.

<DiagramGroup>

<Diagram name="sharing_data_child" height={367} width={407} alt="Skýringarmynd sem sýnir tré með þremur íhlutum, foreldri merkt MyApp og börn þess merkt MyButton. Hvor takkaíhlutur inniheldur fjölda smella með gildinu núll.">

Í upphafi er gildi beggja `MyButton` íhlutanna núllstillt.

</Diagram>

<Diagram name="sharing_data_child_clicked" height={367} width={407} alt="Sama skýringarmynd og á undan, með fjölda smella í fyrsta MyButton íhlutnum undirstrikað til að sýna að smellur hefur uppfært fjöldann í einn smell. Hinn takkinn er enn með gildið núll." >

Fyrri `MyButton` uppfærir `count` gildið í `1`.

</Diagram>

</DiagramGroup>

Oft muntu hins vegar þurfa að láta íhluti *deila gögnum og uppfærast saman*.

Til að láta báða `MyButton` íhlutina birta sama `count` gildið og uppfærast saman þarftu að hífa gildið upp úr takkaíhlutunum og yfir í næsta sameiginlega foreldrið sem inniheldur þá báða.

Í þessu tilfelli er það `MyApp` íhluturinn:

<DiagramGroup>

<Diagram name="sharing_data_parent" height={385} width={410} alt="Skýringarmynd sem sýnir tré þriggja íhluta, eitt foreldri merkt MyApp og tvo afkomendur merkta MyButton. Í MyApp er fjöldi smella núllstilltur, sem er svo fluttur niður í MyButton íhlutina, sem sýna líka gildið núll." >

Upphaflega er gildi `count` breytunnar í `MyApp` núllstillt og svo er það sent niður í takkana.

</Diagram>

<Diagram name="sharing_data_parent_clicked" height={385} width={410} alt="Sama skýringarmynd og á undan en með fjölda smella undirstrikaðan til að merkja að smellur hefur uppfært gildið úr núll yfir í einn. Flæðið til MyButton takkanna er líka undirstrikað, og gildi þeirra hefur verið uppfært til að merkja að það hefur flust úr foreldri." >

Þegar smellt er uppfærir `MyApp` gildið á `count` stöðunni í `1` og sendir til beggja afkomenda.

</Diagram>

</DiagramGroup>

Nú skiptir ekki lengur máli á hvorn takkann þú smellir, því að `smellir` staðan í `Forrit` mun breytast, sem uppfærir í leið gildin í íhlutnum `TakkinnMinn`.

Fyrst skaltu *hífa stöðuna upp* úr íhlutnum `TakkinnMinn` yfir í `Forrit`:

```js {2-6,18}
export default function Forrit() {
  const [smellir, setjaSmelli] = useState(0);

  function sýslaSmell() {
    setjaSmelli(smellir + 1);
  }

  return (
    <div>
      <h1>Teljarar með aðskildri stöðu</h1>
      <TakkinnMinn />
      <TakkinnMinn />
    </div>
  );
}

function TakkinnMinn() {
  // ... við hífðum kóðan upp úr þessum íhlut ...
}

```

Svo skaltu *senda gildið niður* úr `Forrit` í hvern `TakkinnMinn` íhlut ásamt sameiginlega sýslarafallinu. Þú getur sent íhlutnum `TakkinnMinn` gögn innan slaufusviga í JSX á sama máta og gert var áður með innbyggðum merkjum eins og `<img>`:

```js {11-12}
export default function Forrit() {
  const [smellir, setjaSmelli] = useState(0);

  function sýslaSmell() {
    setjaSmelli(smellir + 1);
  }

  return (
    <div>
      <h1>Teljarar með sameiginlegri stöðu</h1>
      <TakkinnMinn smellir={smellir} viðSmell={sýslaSmell} />
      <TakkinnMinn smellir={smellir} viðSmell={sýslaSmell} />
    </div>
  );
}
```

Upplýsingarnar sem þú sendir niður á þennan máta heita _eiginleikar_ (e. props). Nú inniheldur íhluturinn `Forrit` bæði stöðuna `smellir` og `sýslaSmell` sýslarafallið og *sendir þá báða niður sem eiginleika* til takkanna.

Að lokum skaltu uppfæra íhlutinn `TakkinnMinn` til að *lesa* eiginleikana sem þú sendir úr foreldri hans.

```js {1,3}
function TakkinnMinn({ smellir, viðSmell }) {
  return (
    <button onClick={viðSmell}>
      Smellti í {smellir} skipti
    </button>
  );
}
```

Þegar þú smellir á takkann tekur `viðSmell` sýslarafallið við. Í íhlutnum `Forrit` var eiginleikinn `viðSmell` stilltur á `sýslaSmell` til að kóðinn inni í því keyri. Sá kóði kallar á `setjaSmell(smellir + 1)`, sem eykur teljarastöðuna `smellir`. Nýja gildið á stöðunni `smellir` er sent niður sem eiginleiki til hvers takka svo að þeir innihaldi allir sama gildi. Við köllum þetta „að hífa stöðu“. Með því að flytja stöðuna upp um tréð ertu búinn að deila henni á milli íhluta.

<Sandpack>

```js
import { useState } from 'react';

export default function Forrit() {
  const [smellir, setjaSmelli] = useState(0);

  function sýslaSmell() {
    setjaSmelli(smellir + 1);
  }

  return (
    <div>
      <h1>Teljarar með sameiginlegri stöðu</h1>
      <TakkinnMinn smellir={smellir} viðSmell={sýslaSmell} />
      <TakkinnMinn smellir={smellir} viðSmell={sýslaSmell} />
    </div>
  );
}

function TakkinnMinn({ smellir, viðSmell }) {
  return (
    <button onClick={viðSmell}>
      Smellti í {smellir} skipti
    </button>
  );
}
```

```css
button {
  display: block;
  margin-bottom: 5px;
}
```

</Sandpack>

## Næstu skref {/*next-steps*/}

Nú ættirðu að kunna grundvallaratriðin í React!

Kíktu á [kennslusíðuna](/learn/tutorial-tic-tac-toe) til að byrja að notfæra þér þessa þekkingu og smíða þitt fyrsta smáforrit með React.

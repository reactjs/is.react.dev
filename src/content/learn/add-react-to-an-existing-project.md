---
title: Innsetning á React í tiltæku verkefni
---

<Intro>

Þú þarft ekki að endurskrifa tiltækt verkefni til að auka gagnvirknina. Þú getur bætt React við núverandi tæknistafla og birt React íhluti hvar sem er.

</Intro>

<Note>

**Þú verður að innsetja [Node.js](https://nodejs.org/en/) fyrir staðbundna þróun.** Þrátt fyrir að þú getir [prófað React](/learn/installation#try-react) á Netinu eða með einfaldri HTML síðu þá munu flest tólin sem þú þarft í þróunarumhverfinu þurfa á Node.js að halda.

</Note>

## Notkun á React fyrir undirsíðu á núverandi síðu {/*using-react-for-an-entire-subroute-of-your-existing-website*/}

Gefum okkur að þú sért með tiltæka vefþjónustu á `example.com` sem var skrifuð með bakendaþjónustu eins og Rails, og þú viljir útfæra allar beiningar sem byrja á `example.com/eitthvað-forrit` með React.

Þá mælum við með þessari nálgun:

1. **Smíðaðu React hlutann** með einhverju [React rammakerfi](/learn/start-a-new-react-project).
2. **Tilgreindu `/eitthvað-forrit` sem *grunnslóð*** í stillingum rammans sem þú valdir (sjá hér: [Next.js](https://nextjs.org/docs/api-reference/next.config.js/basepath) eða [Gatsby](https://www.gatsbyjs.com/docs/how-to/previews-deploys-hosting/path-prefix/)).
3. **Stilltu vefþjóninn eða vefselið** á þann veg að allar beiðnir sem hefjist á `/eitthvað-forrit/` séu birtar í React forritinu þínu.

Þetta tryggir að React hlutinn í vefsíðunni þinni [fylgi þróunarstöðlunum](/learn/start-a-new-react-project#can-i-use-react-without-a-framework) sem eru innbyggðir í þessum römmum.

Sum React rammakerfi eru heilstafla (e. full-stack) og gera þér kleift að skrifa bakendakóða líka. Hvort sem það er eitthvað sem þú vilt nýta þer eða ekki þá geturðu fylgt sömu nálgunum. Til dæmis er hægt að birta kyrrlegt HTML, CSS, og JS ([`next export` úttak](https://nextjs.org/docs/advanced-features/static-html-export) í Next.js, sjálfgefið í Gatsby) á síðunni `/eitthvað-forrit`.

## Notkun React á hluta vefsíðu {/*using-react-for-a-part-of-your-existing-page*/}

Gefum okkur að þú sért með vefsíðu sem er skrifuð í annarri tækni (annaðvort bakendatækni eins og Rails eða framendatækni eins og Backbone), og að þú viljir birta gagnvirka React íhluti einhvers staðar á síðunni. Þetta er tiltölulega algeng nálgun til að nota React--í raun var það á tímabili nákvæmlega þannig sem Meta notaði React!

Þú getur gert þetta í tveimur skrefum:

1. **Útbúðu JavaScript umhverfi** sem gerir þér kleift að nota [JSX málskipan](/learn/writing-markup-with-jsx), deila kóðanum þínum í einingar með [`import`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import) og [`export`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export) málskipan, og notaðu forritasöfn (til dæmis, React) frá [npm](https://www.npmjs.com/) pakkaskránni.
2. **Birtu React íhlutina þína** þar sem þú vilt hafa þá á síðunni.

Nákvæm útfærsla á þessu veltur á núverandi uppsetningu hjá þér, svo við skulum fara aðeins nánar út í smáatriðin.

### Fyrsta skref: Skiptu JavaScript umhverfinu þínu í einingar {/*step-1-set-up-a-modular-javascript-environment*/}

Með því að skipta JavaScript kóða í einingar er hægt að nota margar skrár í stað þess að skrifa allan kóðann í eina skrá. Það gerir þér líka kleift að nota öll forritasöfnin sem eru aðgengileg á [npm](https://www.npmjs.com/) pakkaskránni--þar á meðal React sjálft! Nálgunin veltur á núverandi uppsetningu:

* **Ef vefurinn þinn er nú þegar skiptur í mismunandi skrár sem nota `import` setningar** reyndu þá að halda áfram að nota sama kerfi. Athugaðu hvort það virki að skrifa `<div />` án þess að það komi málskipanvilla. Ef þetta veldur villu þá kann að vera að þú þurfir að [umbreyta JavaScript kóðanum með Babel](https://babeljs.io/setup), og virkja [Babel React forstillinguna](https://babeljs.io/docs/babel-preset-react) til að nota JSX.

* **Ef vefurinn þinn er ekki með neitt kerfi til að þýða JavaScript einingar** þá skaltu prófa að nota [Vite](https://vitejs.dev/) til þess. Vite samfélagið viðheldur [margs konar samtengingum við bakendaramma](https://github.com/vitejs/awesome-vite#integrations-with-backends), m.a. Rails, Django, og Laravel. Ef bakendaramminn þinn er ekki útlistaður þá skaltu [fylgja þessum leiðbeiningum](https://vitejs.dev/guide/backend-integration.html) til að tengja Vite við bakendann þinn handvirkt.

Til að kanna hvort kerfið þitt virki geturðu keyrt eftirfarandi skipun í aðalmöppu verkefnisins:

<TerminalBlock>
npm install react react-dom
</TerminalBlock>

Bættu svo þessum kóða efst í aðal JavaScript skránni (hún ætti að heita `index.js` eða kannski `main.js`):

<Sandpack>

```html index.html hidden
<!DOCTYPE html>
<html>
  <head><title>Vefurinn minn</title></head>
  <body>
    <!-- Núverandi efni (í þessu tilfelli skiptum við því algjörlega út) -->
  </body>
</html>
```

```js index.js active
import { createRoot } from 'react-dom/client';

// Fjarlægjum núverandi efni.
document.body.innerHTML = '<div id="app"></div>';

// Birtum React íhlut þess í stað.
const root = createRoot(document.getElementById('app'));
root.render(<h1>Halló, heimur!</h1>);
```

</Sandpack>

Ef efnið á síðunni hvarf og „Halló, heimur!“ kom þess í stað þá virkaði breytingin og þú getur haldið áfram að lesa þessar leiðbeiningar.

<Note>

Fyrst um sinn getur verið hálfógnvekjandi að reyna að útfæra einingamiðað JavaScript umhverfi, en það er þess virði! Prófaðu að skoða [efnið frá React samfélaginu](/community) eða [Vite Chat](https://chat.vitejs.dev/) ef þér finnst þú ekki ná árangri.

</Note>

### Annað skref: Birtu React íhluti hvar sem er á síðunni {/*step-2-render-react-components-anywhere-on-the-page*/}

Í skrefinu á undan settum við þennan kóða efst í aðalskránni:

```js index.js active
import { createRoot } from 'react-dom/client';

// Fjarlægjum núverandi efni.
document.body.innerHTML = '<div id="app"></div>';

// Birtum React íhlut þess í stað.
const root = createRoot(document.getElementById('app'));
root.render(<h1>Halló, heimur!</h1>);
```

En að sjálfsögðu viljum við ekki henda öllu efninu af síðunni!

Eyddu þessum kóða.

Instead, you probably want to render your React components in specific places in your HTML. Open your HTML page (or the server templates that generate it) and add a unique [`id`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/id) attribute to any tag, for example:
Þess í stað viltu sennilega birta React íhluti á ákveðnum stöðum. Opnaðu HTML síðuna (eða sniðmátið sem bakendinn útbýr) og bættu við einstöku [`id`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/id) eigindi við hvaða merki sem er á síðunni, til dæmis:

```html
<!-- ... einhvers staðar í skránni ... -->
<nav id="valmynd"></nav>
<!-- ... meira HTML ... -->
```

Með þessu móti geturðu fundið eininguna í HTML skránni með [`document.getElementById`](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById) og fært [`createRoot`](/reference/react-dom/client/createRoot) hana til að birta React íhlut inni í henni:

<Sandpack>

```html index.html
<!DOCTYPE html>
<html>
  <head><title>Vefurinn minn</title></head>
  <body>
    <p>Þessi efnisgrein er hluti af HTML skránni.</p>
    <nav id="valmynd"></nav>
    <p>Þessi efnisgrein er líka hluti af HTML skránni.</p>
  </body>
</html>
```

```js index.js active
import { createRoot } from 'react-dom/client';

function Valmynd() {
  // Síðar: útfærum raunverulegu valmyndina!
  return <h1>Halló frá React!</h1>;
}

const domHnútur = document.getElementById('valmynd');
const rót = createRoot(domHnútur);
rót.render(<Valmynd />);
```

</Sandpack>

Taktu eftir því að upprunalega HTML efnið í `index.html` er enn þar, en React íhluturinn `Valmynd` er nú innan í `<nav id="valmynd">` í HTML skránni. Lestu [skjalbúnaðinn fyrir `createRoot`](/reference/react-dom/client/createRoot#rendering-a-page-partially-built-with-react) til að kynna þér nánar hvernig hægt er að birta React íhluti inni í HTML síðu.

Það er algengt að byrja á að útfæra smærri gagnvirka íhluti eins og takka og hægt og rólega „færa sig ofar“ þar til öll síðan er útfærð í React. Ef þú nálgast það stig þá mælum við með því að flytja þig yfir í [React ramma](/learn/start-a-new-react-project) til að nýta React sem best.

## Notkun á React Native í tiltæku forriti á heimavangi {/*using-react-native-in-an-existing-native-mobile-app*/}

Það er einnig hægt að byrja að nota [React Native](https://reactnative.dev/) hægt og rólega. Ef þú ert með forrit fyrir Android (í Java eða Kotlin) eða iOS (í Objective-C eða Swift), [fylgdu þá þessum leiðbeiningum](https://reactnative.dev/docs/integration-with-existing-apps) til að bæta við virkni í React Native.

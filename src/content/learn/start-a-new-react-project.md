---
title: Byrjaðu á nýju React verkefni
---

<Intro>

Ef þig langar að smíða nýja vefsíðu með React frá grunni þá mælum við með að velja einn af þeim römmum (e. framework) sem byggja á React og eru vinsælir í React samfélaginu. Þessi forritasöfn veita þér aðgang að sérkennum sem flest forrit og vefsíður þurfa á endanum, til dæmis beiningu (e. routing), tól til að sækja og vinna með gögn, og verkfæri til að útbúa HTML.

</Intro>

<Note>

**Þú þarft að innsetja [Node.js](https://nodejs.org/en/) fyrir staðbundna þróun.** Þú getur *líka* valið að nota Node.js í rekstrarumhverfi, en þú þarft þess ekki. Mörg React forritasöfn styðja útflutning yfir í kyrrlega HTML/CSS/JS möppu.

</Note>

## React rammar sem hægt er að reiða sig á í rekstri {/*production-grade-react-frameworks*/}

### Next.js {/*nextjs*/}

**[Next.js](https://nextjs.org/) er svokallaður heilstafla (e. full-stack) React rammi.** Next.js er fjölhæfur rammi sem gerir þér kleift að smíða React forrit af hvaða stærð sem er--frá kyrrlegri pistlasíðu yfir í flókið og kviklegt forrit. Keyra má eftirfarandi skipun til að skapa nýtt Next.js verkefni frá grunni:

<TerminalBlock>
npx create-next-app@latest
</TerminalBlock>

Skoðaðu [Next.js inngangsleiðbeiningar](https://nextjs.org/learn/foundations/about-nextjs) ef þú hefur ekki notað Next.js áður.

<<<<<<< HEAD
[Vercel](https://vercel.com) sér um þróun og viðhald á Next.js. Þú getur getur [keyrt Next.js vef](https://nextjs.org/docs/deployment) á Node.js vefþjóni, miðlaralausri hýsingu, eða á þínum eigin netþjóni. [Kyrrlega Next.js](https://nextjs.org/docs/advanced-features/static-html-export) vefi má keyra á hvaða kyrrlegri (e. static) hýsingu sem er.
=======
Next.js is maintained by [Vercel](https://vercel.com/). You can [deploy a Next.js app](https://nextjs.org/docs/app/building-your-application/deploying) to any Node.js or serverless hosting, or to your own server. Next.js also supports a [static export](https://nextjs.org/docs/pages/building-your-application/deploying/static-exports) which doesn't require a server.
>>>>>>> 943e3ce4e52be56bcd75b679448847302f557da1

### Remix {/*remix*/}

**[Remix](https://remix.run/) er heilstafla React rammi með faldaðri beiningu.** Það gerir þér kleift að skipta vefnum þínum í faldaða hluta sem geta svo hlaðið gögnum samhliða og endurglætt samskiptasvar við aðgerðum notenda. Keyra má eftirfarandi skipun til að skapa nýtt Remix verkefni:

<TerminalBlock>
npx create-remix
</TerminalBlock>

Skoðaðu [þenann stutta kynningarpistil](https://remix.run/docs/en/main/tutorials/blog) og þennan [lengri pistil](https://remix.run/docs/en/main/tutorials/jokes) ef þú hefur ekki áður notað Remix.

[Shopify](https://www.shopify.com/) sér um þróun og viðhald á Remix. Þegar þú býrð til Remix verkefni þarftu að [velja þér hvers lags netþjón þú vilt keyra á](https://remix.run/docs/en/main/guides/deployment). Þú getur keyrt Remix vef á hvaða Node.js eða miðlaralausri hýsingu sem er með því að nota eða skrifa [millistykki](https://remix.run/docs/en/main/other-api/adapter).

### Gatsby {/*gatsby*/}

**[Gatsby](https://www.gatsbyjs.com/) er React rammi til að þróa hraðskreiðar síður sem byggja á gögnum úr CMS (e. content management system) kerfi.** Eitt höfuðmarkmið þess er að einfalda sameiningu efnis, forritaskila, og vefþjónustum í eina vefsíðu. Keyra má eftirfarandi skipun til að skapa Gatsby verkefni:

<TerminalBlock>
npx create-gatsby
</TerminalBlock>

Kíktu á [Gatsby kynninguna](https://www.gatsbyjs.com/docs/tutorial/) ef þú hefur ekki prófað Gatsby áður.

[Netlify](https://www.netlify.com) sér um þróun og viðhald Gatsby rammans. Þú getur [keyrt algjörlega kyrrlega Gatsby síðu](https://www.gatsbyjs.com/docs/how-to/previews-deploys-hosting) á hvaða kyrrlegri hýsingu sem er. Ef þú kýst að nota sérkenni sem krefjast þess að þú notir vefjón þá skaltu ganga úr skugga um að hýsingaraðilinn þinn styðji þær fyrir Gatsby.

### Expo (fyrir forrit á heimavangi) {/*expo*/}

**[Expo](https://expo.dev/) er React rammi sem gerir þér kleift að skapa alhliða forrit fyrir Android, iOS, og veraldarvefinn með viðmótum sem tilheyra í heimavangi.** Það veitir þér aðgang að SDK (e. software development kit) fyrir [React Native](https://reactnative.dev) sem gerir allt sem snertir inningu á heimavangi mun einfaldara í notkun. Keyra má eftirfarandi skipun til að skapa nýtt Expo verkefni:

<TerminalBlock>
npx create-expo-app
</TerminalBlock>

Skoðaðu [Expo kynninguna](https://docs.expo.dev/tutorial/introduction/) ef þú hefur aldrei notað Expo áður.

[Expo (fyrirtækið)](https://expo.dev/about) sér um þróun og viðhald á Expo. Þróun með Expo er ókeypis og þú getur sótt um að fá forritið þitt í Google og Apple forritaveiturnar án takmarkana. Expo býður einnig upp á valkvæðar skýjaþjónustur gegn greiðslu.

<DeepDive>

#### Get ég notað React án ramma? {/*can-i-use-react-without-a-framework*/}

Þú getur algjörlega notað React án ramma--það er þannig sem þú mundir [nota React á smærri hluta vefsíðu](/learn/add-react-to-an-existing-project#using-react-for-a-part-of-your-existing-page). **Þrátt fyrir það mælum við með því að þú notir ramma ef þú vilt notfæra þér það sem React hefur fram að færa til hins ýtrasta.**

Hér er nokkrar ástæður fyrir því:

Jafnvel þó að þú þurfir ekki á beiningu (e. routing) að halda eða að tengjast forritaskilum þá muntu þó sennilega þurfa að bæta við einhverjum forritasöfnum fyrir þessar aðgerðir. Eftir því sem tíminn líður stækkar JavaScript knippið með hverju nýju sérkenni og þú munt mögulega þurfa að finna út úr því hvernig þú getur skipt knippinu í smærri búta (e. code splitting). Þá flækist tengingin þín gagnvart forritaskilum með tímanum, og þú gætir lent í „fyrirspurnafossum“ fram og til baka á milli biðlara og vefþjóns sem gera kerfið þitt hægt. Í tíð og tíma kann notendahópurinn þinn að stækka og innihalda fleiri notendur með lélegar nettengingar og ódýrari tölvubúnað, og þú þarft þá kannski að útbúa kyrrlegt HTML út frá íhlutunum þínum til að birta efni hraðar--annaðhvort á netþjóninum eða við smíði. Breytingar af þessu tagi, þ.e. á því hvar kóðinn keyrir, til dæmis þannig að hluti hans keyri á netþjóni eða við smíði, geta verið mjög flóknar.

**Þetta eru ekki vandamál sem eiga bara við React. Þetta er ástæðan fyrir því að Svelte er með SvelteKit, Vue er með Nuxt, o.s.frv.** Til að leysa þessi vandamál þarf að skrifa kóða gagnvart knippiforriti (e. bundler), beiningu, og forritasafni til að sjá um samskipti við bakenda í gegnum forritaskil. Í upphafi er ekki erfitt að fá þessa hluti til að virka sæmilega saman, en það verður fljótt flóknara eftir því sem vefur vex og þarfir breytast. Þú gætir viljað senda minnsta mögulega kóðann en á sama tíma að gera það í einni brautartímaferð á milli framenda og bakenda, samhliða öðrum gögnum sem síðan þarf á að halda. Þá getur einnig verið mikilvægt að síðan sé nothæf áður en JavaScript kóðinn byrjar að keyra, til að styðja stighækkandi betrumbætur (e. progressive enhancement). Það kann að þurfa að útfæra möppu með kyrrlegum HTML skrám fyrir markaðssetningarsíðurnar sem er hægt að hýsa hvar sem er og virkar þó að JavaScript sé ekki leyft að keyra. Það tekur tíma að útfæra alla þessa virkni upp á eigin spýtur.

**React rammakerfi sem eru útlistuð á þessari síðu leysa þessi vandamál sjálfvirkt svo að þú þurfir ekki að endurskapa þessa virkni.** Þau gera þér kleift að byrja smátt og þau stækka með þörfum þínum. Hver rammi er með sitt eigið samfélag og það er auðveldara að finna svör og uppfæra tól. Rammakerfi veita verkefninu líka traust burðarvirki, sem hjálpar þér og öðrum að viðhalda samhengi og þekkingu á milli verkefna. Í samanburði er auðvelt að festast í því að þurfa að nota óstuddar útgáfur af forritasöfnum og þú endar í raun á að skapa þitt eigið rammakerfi--en þó ramma sem enginn annar notar og enginn mun uppfæra fyrir þig (og ef hann er eitthvað í líkingu við það sem við höfum þróað áður, verr skipulagðan).

Ef þetta er ekki nóg til að sannfæra þig, eða ef forritið þitt er með óvenjulegar kröfur sem þessir rammar leysa ekki vel og þig langar að útfæra þína eigin lausn, þá getum við ekki stöðvað þig--gerðu þetta bara! Gríptu `react` og `react-dom` frá npm, smíðaðu forritið þitt með knippikerfi eins og [Vite](https://vitejs.dev/) eða [Parcel](https://parceljs.org/), og bættu öðrum tólum við eftir þörf, þ.e. beiningu, kyrrlega útfærslu eða bakendavörpun (e. server-side rendering), o.fl.

</DeepDive>

## Nýjasta nýtt í React rammakerfum {/*bleeding-edge-react-frameworks*/}

React teymið hefur nýverið komist að því að nánari samhæfing á React og rammakerfum (sérstaklega í tengslum við beiningu, knippi og smíði, og bakendatækni) er okkar stærsta tækifæri til að hjálpa notendum að búa til betri vefsíður. Next.js teymið hefur samþykkt að starfa nánar með okkur í rannsóknum, þróun, sameiningu, og prófunum á nýjum sérkennum sem eru óháð einstökum rammakerfum eins og [React Server Components](/blog/2023/03/22/react-labs-what-we-have-been-working-on-march-2023#react-server-components).

Þessi virkni nálgast meir á hverjum degi að verða tilbúin í rekstrarumhverfi og við höfum rætt við önnur teymi sem stunda þróun á  knippikerfum og römmum til að sameina þau. Við vonumst til þess að eftir eitt eða tvö ár séu öll kerfin sem eru útlistuð hér með beinan stuðning fyrir þessa virkni. (Láttu okkur vita ef þú ert að þróa rammakerfi og hefur áhuga á að sameina krafta okkar og prófa þessa virkni!)

### Next.js (App Router) {/*nextjs-app-router*/}

<<<<<<< HEAD
**[App Router tæknin í Next.js](https://beta.nextjs.org/docs/getting-started) er endurhönnun á forritaskilunum í Next.js með það að leiðarljósi að uppfylla draumsýn React teymisins um heilstafla högun.** Hún gerir þér kleift að sækja gögn í ósamstillt íhlutum sem keyra á netþjóninum eða jafnvel á meðan á smíði stendur.

[Vercel](https://vercel.com) sér um þróun og viðhald á Next.js. Þú getur [keyrt Next.js vef](https://vercel.com/) á hvaða Node.js eða biðlaralausri hýsingu sem er, eða á þínum eigin netþjóni. Next.js styður einnig [kyrrlegan útflutning](https://beta.nextjs.org/docs/configuring/static-export) sem krefst ekki netþjóns.

<Pitfall>

App Router tæknin í Next.js er **í betaprófunum eins og stendur og ekki er mælt með notkun hennar í rekstri** (mars 2023). Til að prófa þessa tækni í tiltæku Next.js verkefni má [fylgja þessum leiðbeiningum að þrepaskiptum kerfaskiptum](https://beta.nextjs.org/docs/upgrade-guide#migrating-from-pages-to-app).

</Pitfall>
=======
**[Next.js's App Router](https://nextjs.org/docs) is a redesign of the Next.js APIs aiming to fulfill the React team’s full-stack architecture vision.** It lets you fetch data in asynchronous components that run on the server or even during the build.

Next.js is maintained by [Vercel](https://vercel.com/). You can [deploy a Next.js app](https://nextjs.org/docs/app/building-your-application/deploying) to any Node.js or serverless hosting, or to your own server. Next.js also supports [static export](https://nextjs.org/docs/app/building-your-application/deploying/static-exports) which doesn't require a server.
>>>>>>> 943e3ce4e52be56bcd75b679448847302f557da1

<DeepDive>

#### Hver er framtíðarsýn React teymisins í tengslum við heilstafla (e. full-stack) arkítektúr? {/*which-features-make-up-the-react-teams-full-stack-architecture-vision*/}

App Router knippikerfið í Next.js útfærir opinberu [React Server Components hönnunarlýsinguna](https://github.com/reactjs/rfcs/blob/main/text/0188-server-components.md). Þetta gerir þér kleift að blanda inningu við smíði, á netþjóni, og gagnvirkum íhlutum í sama React trénu.

Þú getur til dæmis skrifað React íhlut sem keyrir aðeins á netþjóninum sem `async` fall sem les beint úr gagnagrunni eða skrá. Þá geturðu flutt þessi gögn niður tréð í gagnvirka íhluti:

```js
// Þessi íhluti keyrir *aðeins* á vefþjóninum (eða við smíði).
async function Fyrirlestrar({ kennimerkiRáðstefnu }) {
  // 1. Þú ert á vefþjóninum, svo þú getur talað við gagnagrunninn beint. Forritaskil eru óþarfi.
  const fyrirlestrar = await db.Fyrirlestrar.findAll({ kennimerkiRáðstefnu });

  // 2. Bættu hvaða virkni við sem þörf er á. Það hefur ekki áhrif á stærð JavaScript knippisins.
  const myndskeið = fyrirlestrar.map(fyrirlestur => fyrirlestur.myndskeið);

  // 3. Flyttu gögnin niður í gegnum íhlutina sem inntir eru í vafranum.
  return <LeitanlegurMyndskeiðalisti myndskeið={myndskeið} />;
}
```

App Router kerfið í Next.js sameinar einnig [gagnaflutning og Suspense](/blog/2022/03/29/react-v18#suspense-in-data-frameworks). Þetta gerir þér kleift að tilgreina tímabundna hleðslustöðu (e. loading state) fyrir mismunandi hluta af viðmótinu beint í React trénu:

```js
<Suspense fallback={<Hleðslustaða />}>
  <Fyrirlestrar kennimerkiRáðstefnu={ráðstefna.kennimerki} />
</Suspense>
```

Server Components og Suspense eru ekki Next.js sérkenni heldur React sérkenni. Á móti kemur að það er ekkert smáræði að útfæra þessa virkni í rammakerfi og krefur mikillar vinnu. Eins og staðan er nú þá er App Router útfærslan í Next.js sú sem er lengst komin. React teymið starfar náið með forriturunum sem vinna að knippiforritinu til að gera þessi sérkenni auðveldari að útfæra í síðari rammakerfum.

</DeepDive>

---
title: Þróunartól fyrir React
---

<Intro>

Notaðu React þróunartól til að kanna innri stöðu React [íhluta](/learn/your-first-component), breyta [eiginleikum](/learn/passing-props-to-a-component) og [stöðu](/learn/state-a-components-memory), og bera kennsl á frammistöðuvandamál.

</Intro>

<YouWillLearn>

* Hvernig skal innsetja þróunartólin

</YouWillLearn>

## Vafraviðbót {/*browser-extension*/}

The easiest way to debug websites built with React is to install the React Developer Tools browser extension. It is available for several popular browsers:
The easiest way to debug websites built with React is to install the React Developer Tools browser extension. It is available for several popular browsers:
Einfaldasta leiðin til að kemba vefsíður skrifaðar í React er að nota vafraviðbót með React þróunartólum. Viðbótin er aðgengileg nokkrum af helstu vöfrunum:

* [Innsettu í **Chrome**](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=en)
* [Innsettu í **Firefox**](https://addons.mozilla.org/en-US/firefox/addon/react-devtools/)
* [Innsettu í **Edge**](https://microsoftedge.microsoft.com/addons/detail/react-developer-tools/gpphkfbcpidddadnkolkpfckpihlkkil)

Þegar viðbótin er uppsett geturðu séð flipa merkta „_Components_“ og „_Profiler_“.

![React þróunartól sem viðbót](/images/docs/react-devtools-extension.png)

### Safari og aðrir vafrar {/*safari-and-other-browsers*/}

Hægt er að innsetja npm pakkan [`react-devtools`](https://www.npmjs.com/package/react-devtools) í öðrum vöfrum (t.d. Safari):
```bash
# Yarn
yarn global add react-devtools

# npm
npm install -g react-devtools
```

Næst skaltu opna þróunartólin úr skipanalínunni:
```bash
react-devtools
```

Þá geturðu tengst vefsíðunni með því að bæta eftirfarandi `<script>` merki efst í `<head>` merki vefsíðunnar:
```html {3}
<html>
  <head>
    <script src="http://localhost:8097"></script>
```

Endurglæddu vefsíðuna í vafranum til að sjá þróunartólin.

![React þróunartól án vafraviðbótar](/images/docs/react-devtools-standalone.png)

## Farandtæki (React Native) {/*mobile-react-native*/}

Þróunartólin fyrir React má líka nota til að kanna forrit sem eru byggð með [React Native](https://reactnative.dev/).

Einfaldasta leiðin til að nota þróunartólin er að innsetja þau í allsherjarumhverfinu:
```bash
# Yarn
yarn global add react-devtools

# Npm
npm install -g react-devtools
```

Næst skaltu opna þróunartólin úr skipanalínunni:
```bash
react-devtools
```

Tólin ættu þá að tengjast staðbundnu React Native forriti sem er í keyrslu.

> Prófaðu að endurglæða forritið ef þróunartólin eru ekki aðgengileg eftir nokkrar sekúndur.

[Nánar varðandi kembun React Native forrita](https://reactnative.dev/docs/debugging).

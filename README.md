# HEAD

Uma lista de tudo que poderia ir na `<head>` do seu documento

**Índice:**
- [Mínimo Recomendado](#mínimo-recomendado)
- [Elementos](#elementos)
- [Elementos Meta](#elementos-meta)
  - [Elementos Meta: Não Recomendado](#elementos-meta-não-recomendado)
- [Elementos Link](#elementos-link)
  - [Elementos Link: Não Recomendado](#lelementos-link-não-recomendado)
  - [Favicons](#favicons)
- [Social](#social)
  - [Facebook / Open Graph](#facebook--open-graph)
  - [Facebook / Instant Articles](#facebook--instant-articles)
  - [Twitter](#twitter)
  - [Google+ / Schema.org](#google--schemaorg)
  - [OEmbed](#oembed)
- [Navegador / Plataforma](#navegador--plataforma)
  - [Apple iOS](#apple-ios)
  - [Apple Safari](#apple-safari)
  - [Google Android](#google-android)
  - [Google Chrome](#google-chrome)
  - [Microsoft Internet Explorer](#microsoft-internet-explorer)
  - [Microsoft Internet Explorer: Legacy, Não Use!](#microsoft-internet-explorer-legacy-do-not-use)
  - [360 Browser](#360-browser)
  - [UC Mobile Browser](#uc-mobile-browser)
  - [QQ Mobile Browser](#qq-mobile-browser)
- [App Links](#app-links)
- [Notas](#notas)
  - [Performance](#performance)
- [Outros Recursos](#outros-recursos)
- [Projetos Relacionados](#projetos-relacionados)
- [Contribuindo](#contribuindo)

## Mínimo Recomendado

Abaixo estão as *tags* essenciais para, sites minimalistas básicos:

```html
<meta charset="utf-8">
<meta http-equiv="x-ua-compatible" content="ie=edge">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Título da Página</title>
```

## Elementos

``` html
<!-- Título do documento -->
<title>Título da página</title>

<!-- URL base para todas as URLs relativas contidas no documento -->
<base href="https://example.com/page.html">

<!-- CSS externo -->
<link rel="stylesheet" href="styles.css">

<!-- CSS no documento -->
<style>
  /* ... */
</style>

<!-- JavaScript -->
<script src="script.js"></script>
```

## Elementos Meta

``` html
<meta charset="utf-8">
<meta http-equiv="x-ua-compatible" content="ie=edge">
<meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
<!-- As 3 meta tags acima *devem* vir em primeiro lugar na head; qualquer outro conteúdo na head deve vir *após* estas tags  -->

<!-- Nome de aplicação web (só deve ser usado se o site é usado como um app) -->
<meta name="application-name" content="Application Name">

<!-- Descrição curta do site com 3 ou 4 frases: incluída nos resultados do motor de busca -->
<meta name="description" content="150 chars">

<!-- Breve descrição do assunto do seu site -->
<meta name="subject" content="your website's subject">

<!-- Controle de que páginas são permitidas a serem indexedas pelos robôs de busca -->
<meta name="robots" content="index,follow,noodp">

<!-- Mesmo esquema acima porém exclusivamente para o Google -->
<meta name="googlebot" content="index,follow">

<!-- Diz o motor de busca Google não mostrar a caixa de pesquisa de sitelinks  -->
<meta name="google" content="nositelinkssearchbox">

<!-- Verifica a propriedade do Console de Pesquisa para o Google -->
<meta name="google-site-verification" content="verification_token">

<!-- Usado para nomear o programa usado para construir o site (I.S. - Wordpress, Dreamweaver) -->
<meta name="generator" content="program">

<!-- Frase muito curta descrevendo o propósito do site -->
<meta name="abstract" content="">

<!-- Descreve o tema do website -->
<meta name="topic" content="">

<!-- Breve resumo da empresa ou do propósito do site -->
<meta name="summary" content="">

<!-- A tag obsoleta que faz o mesmo que a tag keywords -->
<meta name="classification" content="business">

<!-- Domínio completo ou o endereço web -->
<meta name="url" content="https://example.com/">

<!-- Faz o mesmo que URL, mais velho e não é suportado -->
<meta name="identifier-URL" content="https://example.com/">


<meta name="directory" content="submission">

<!-- Faz o mesmo que a tag keywords -->
<meta name="category" content="">

<!-- Garante que o seu site aparece em todos os países e idiomas -->
<meta name="coverage" content="Worldwide">

<!-- Faz o mesmo que a tag coverage -->
<meta name="distribution" content="Global">

<!-- Dá uma classificação de idade geral com base em sites de conteúdo -->
<meta name="rating" content="General">

<!-- Permite o controle sobre como a informação de referência é passada -->
<meta name="referrer" content="never">

<!-- Permite o controle sobre de onde os recursos são carregados -->
<meta http-equiv="Content-Security-Policy" content="default-src 'self'">

<!-- Desativar a detecção automática e formatação de possíveis números de telefone -->
<meta name="format-detection" content="telephone=no">

<!-- Geo tags -->
<meta name="ICBM" content="latitude, longitude" />
<meta name="geo.position" content="latitude;longitude" />
<meta name="geo.region" content="country[-state]" /><!-- Código do país (ISO 3166-1): obrigatório, código do estado (ISO 3166-2): opcional; por exemplo: content="US" / content="US-NY" -->
<meta name="geo.placename" content="city/town" /><!-- por exemplo: content= "New York City" -->
```

- [ICBM on Wikipedia](https://en.wikipedia.org/wiki/ICBM_address#Modern_use)
- [Geotagging on Wikipedia](https://en.wikipedia.org/wiki/Geotagging#HTML_pages)

### Elementos Meta: Não Recomendado

A seguir estão os atributos *meta* que não são recomendados para uso:

```html
<!-- Usado para declarar o idioma do documento, mas não é bem suportado. Melhor usar <html lang = ""> -->
<meta name="language" content="en">

<!-- Google ignora & Bing considera um indicador do spam -->
<meta name="keywords" content="your,keywords,here,comma,separated,no,spaces">

<!-- Não há evidência de uso corrente em todos os motores de busca -->
<meta name="revised" content="Sunday, July 18th, 2010, 5:15 pm">

<!-- Fornece uma maneira fácil para que robôs de spam colham endereços de e-mail -->
<meta name="reply-to" content="email@example.com">

<!-- Melhor usar <link rel = "autor"> ou arquivo humans.txt -->
<meta name="author" content="name, email@example.com">
<meta name="designer" content="">
<meta name="owner" content="">

<!-- Diz para robôs de pesquisa para voltarem na página depois de um período. Isto não é suportado porque a maioria dos motores de busca agora usar intervalos aleatórios para re-rastreamento de uma página web -->
<meta name="revisit-after" content="7 days">

<!-- Google strongly advises not to use this. Better to set up server-side (e.g. Apache, nginx) redirects instead -->
<!-- Google aconselha a não usar isso. Melhor configurar no lado do servidor (por exemplo, Apache, nginx) redirecionamento como alternativa -->
<meta http-equiv="refresh" content="300;url=https://example.com/">

<!-- Controle de Cache  -->
<!-- Better to configure cache control server side -->
<!-- Melhor configurar no lado do servidor o controle do cache -->
<meta http-equiv="Expires" content="0">
<meta http-equiv="Pragma" content="no-cache">
<meta http-equiv="Cache-Control" content="no-cache">
```

## Elementos Link

``` html
<link rel="copyright" href="copyright.html">
<link rel="stylesheet" href="https://example.com/styles.css">
<link rel="alternate" href="https://feeds.feedburner.com/martini" type="application/rss+xml" title="RSS">
<link rel="alternate" href="https://example.com/feed.atom" type="application/atom+xml" title="Atom 0.3">
<link rel="alternate" href="https://es.example.com/" hreflang="es">
<link rel="me" href="https://google.com/profiles/thenextweb" type="text/html">
<link rel="me" href="mailto:name@example.com">
<link rel="me" href="sms:+15035550125">
<link rel="archives" href="https://example.com/2003/05/" title="May 2003">
<link rel="index" href="https://example.com/" title="DeWitt Clinton">
<link rel="start" href="https://example.com/photos/pattern_recognition_1_about/" title="Pattern Recognition 1">
<link rel="prev" href="https://example.com/opensearch/opensearch-and-openid-a-sure-way-to-get-my-attention/" title="OpenSearch and OpenID? A sure way to get my attention.">
<link rel="search" href="/open-search.xml" type="application/opensearchdescription+xml" title="Search Title">
<link rel="self" type="application/atom+xml" href="https://example.com/atomFeed.php?page=3">
<link rel="first" href="https://example.com/atomFeed.php">
<link rel="next" href="https://example.com/atomFeed.php?page=4">
<link rel="previous" href="https://example.com/atomFeed.php?page=2">
<link rel="last" href="https://example.com/atomFeed.php?page=147">
<link rel="shortlink" href="https://example.com/?p=43625">
<link rel="canonical" href="https://example.com/2010/06/9-things-to-do-before-entering-social-media.html">
<link rel="amphtml" href="https://www.example.com/url/to/amp-version.html">
<link rel="EditURI" href="https://example.com/xmlrpc.php?rsd" type="application/rsd+xml" title="RSD">
<link rel="pingback" href="https://example.com/xmlrpc.php">
<link rel="webmention" href="https://example.com/webmention">
<link rel="manifest" href="manifest.json">
<link rel="author" href="humans.txt">
<link rel="import" href="component.html">

<!-- Prefetching, pré-carregamento, pré-navegação -->
<link rel="dns-prefetch" href="//example.com/">
<link rel="preconnect" href="https://www.example.com/">
<link rel="prefetch" href="https://www.example.com/">
<link rel="prerender" href="https://example.com/">
<link rel="subresource" href="styles.css">
<link rel="preload" href="image.png">
<!-- Mais informações: https://css-tricks.com/prefetching-preloading-prebrowsing/ -->
```

### Elementos Link: Não Recomendado
Below are the link relations which are not recommended for use:

```html
<link rel="shortcut icon" href="path/to/favicon.ico">
```

### Favicons

``` html
<!-- Para o IE 10 e abaixo -->
<!-- Sem link, basta colocar um arquivo chamado favicon.ico no diretório raiz -->

<!-- Para IE11, Chrome, Firefox, Safari, Opera -->
<link rel="icon" href="path/to/favicon-16.png" sizes="16x16" type="image/png">
<link rel="icon" href="path/to/favicon-32.png" sizes="32x32" type="image/png">
<link rel="icon" href="path/to/favicon-48.png" sizes="48x48" type="image/png">
<link rel="icon" href="path/to/favicon-62.png" sizes="62x62" type="image/png">
<link rel="icon" href="path/to/favicon-192.png" sizes="192x192" type="image/png">
<!-- Mais informações: https://bitsofco.de/all-about-favicons-and-touch-icons/ -->
```

- [Tudo sobre Favicons (E ícones *touch*)](https://bitsofco.de/all-about-favicons-and-touch-icons/)

## Social

### Facebook / Open Graph

``` html
<meta property="fb:app_id" content="123456789">
<meta property="og:url" content="https://example.com/page.html">
<meta property="og:type" content="website">
<meta property="og:title" content="Content Title">
<meta property="og:image" content="https://example.com/image.jpg">
<meta property="og:description" content="Description Here">
<meta property="og:site_name" content="Site Name">
<meta property="og:locale" content="en_US">
<meta property="article:author" content="">
<!-- Facebook: https://developers.facebook.com/docs/sharing/webmasters#markup -->
<!-- Open Graph: http://ogp.me/ -->
```

- [Facebook Open Graph - Marcação](https://developers.facebook.com/docs/sharing/webmasters#markup)
- [Open Graph - Protocolo](http://ogp.me/)

### Facebook / Instant Articles

``` html
<meta charset="utf-8">
<meta property="op:markup_version" content="v1.0">

<!-- A URL da versão web do seu artigo -->
<link rel="canonical" href="http://example.com/article.html">

<!-- O estilo que deve ser utilizado para este artigo -->
<meta property="fb:article_style" content="myarticlestyle">
```

- [Facebook Instant Articles: Criando de artigos](https://developers.facebook.com/docs/instant-articles/guides/articlecreate)
- [Instant Articles: Reference de Formatação](https://developers.facebook.com/docs/instant-articles/reference)

### Twitter

``` html
<meta name="twitter:card" content="summary">
<meta name="twitter:site" content="@site_account">
<meta name="twitter:creator" content="@individual_account">
<meta name="twitter:url" content="https://example.com/page.html">
<meta name="twitter:title" content="Content Title">
<meta name="twitter:description" content="Content description less than 200 characters">
<meta name="twitter:image" content="https://example.com/image.jpg">
<!-- Mais informações: https://dev.twitter.com/cards/getting-started -->
<!-- Valide: https://dev.twitter.com/docs/cards/validation/validator -->
```

- [Twitter Cards: Guia de Introdução](https://dev.twitter.com/cards/getting-started)
- [Twitter Card: Validador](https://dev.twitter.com/docs/cards/validation/validator)

### Google+ / Schema.org

``` html
<link href="https://plus.google.com/+YourPage" rel="publisher">
<meta itemprop="name" content="Content Title">
<meta itemprop="description" content="Content description less than 200 characters">
<meta itemprop="image" content="https://example.com/image.jpg">
```

### OEmbed

``` html
<link rel="alternate" type="application/json+oembed"
  href="http://example.com/services/oembed?url=http%3A%2F%2Fexample.com%2Ffoo%2F&amp;format=json"
  title="oEmbed Profile: JSON">
<link rel="alternate" type="text/xml+oembed"
  href="http://example.com/services/oembed?url=http%3A%2F%2Fexample.com%2Ffoo%2F&amp;format=xml"
  title="oEmbed Profile: XML">
```

- [oEmbed format](http://oembed.com/)

## Navegador / Plataforma


### Apple iOS

``` html
<!-- Smart App Banner -->
<meta name="apple-itunes-app" content="app-id=APP_ID,affiliate-data=AFFILIATE_ID,app-argument=SOME_TEXT">

<!-- Desativar a detecção automática e formatação de possíveis números de telefone -->
<meta name="format-detection" content="telephone=no">

<!-- Adicionar na Tela Inicial  -->
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black">
<meta name="apple-mobile-web-app-title" content="App Title">

<!-- Ícones Touch -->
<link rel="apple-touch-icon" href="path/to/apple-touch-icon.png">
<link rel="apple-touch-icon-precomposed" href="path/to/apple-touch-icon-precomposed.png">
<!-- Na maioria dos casos, um ícone touch de 180×180px é suficiente -->
<!-- Se você quer ter um conteúdo diferente para cada dispositivo, você pode adicionar mais ícones touch -->

<!-- Imagem Inicial -->
<link rel="apple-touch-startup-image" href="path/to/startup.png">

<!-- Mais informações: https://developer.apple.com/safari/library/documentation/appleapplications/reference/safarihtmlref/articles/metatags.html -->
```

- [Apple Meta Tags](https://developer.apple.com/library/safari/documentation/AppleApplications/Reference/SafariHTMLRef/Articles/MetaTags.html)

### Apple Safari

```html
<!-- Site Fixado -->
<link rel="mask-icon" href="path/to/icon.svg" color="red">
```

### Google Android

``` html
<meta name="theme-color" content="#E64545">

<!-- Adicionar à tela inicial -->
<meta name="mobile-web-app-capable" content="yes">
<!-- Mais informações: https://developer.chrome.com/multidevice/android/installtohomescreen -->
```

### Google Chrome

``` html
<link rel="chrome-webstore-item" href="https://chrome.google.com/webstore/detail/APP_ID">

<!-- Desabilitar prompt de tradução -->
<meta name="google" value="notranslate">
```

### Microsoft Internet Explorer

``` html
<meta http-equiv="x-ua-compatible" content="ie=edge">
<meta http-equiv="cleartype" content="on">
<meta name="skype_toolbar" content="skype_toolbar_parser_compatible">

<!-- Desativar link destacado no IE 10 do Windows Phone(https://blogs.windows.com/buildingapps/2012/11/15/adapting-your-webkit-optimized-site-for-internet-explorer-10/) -->
<meta name="msapplication-tap-highlight" content="no">

<!-- Sites fixados (https://msdn.microsoft.com/en-us/library/dn255024(v=vs.85).aspx) -->
<meta name="application-name" content="Contoso Pinned Site Caption">
<meta name="msapplication-tooltip" content="Example Tooltip Text">
<meta name="msapplication-starturl" content="/">

<meta name="msapplication-config" content="http://example.com/browserconfig.xml">

<meta name="msapplication-allowDomainApiCalls" content="true">
<meta name="msapplication-allowDomainMetaTags" content="true">
<meta name="msapplication-badge" content="frequency=30; polling-uri=http://example.com/id45453245/polling.xml">
<meta name="msapplication-navbutton-color" content="#FF3300">
<meta name="msapplication-notification" content="frequency=60;polling-uri=http://example.com/livetile">
<meta name="msapplication-square150x150logo" content="path/to/logo.png">
<meta name="msapplication-square310x310logo" content="path/to/largelogo.png">
<meta name="msapplication-square70x70logo" content="path/to/tinylogo.png">
<meta name="msapplication-wide310x150logo" content="path/to/widelogo.png">
<meta name="msapplication-task" content="name=Check Order Status;action-uri=./orderStatus.aspx?src=IE9;icon-uri=./favicon.ico">
<meta name="msapplication-task-seperator" content="1">
<meta name="msapplication-TileColor" content="#FF3300">
<meta name="msapplication-TileImage" content="path/to/tileimage.jpg">
<meta name="msapplication-window" content="width=1024;height=768">
```

### Microsoft Internet Explorer: Legacy, Do Not Use!

``` html
<!-- Desativar a barra de ferramentas de imagem quando você passa o mouse sobre as imagens em IE 6 (https://msdn.microsoft.com/en-us/library/ms532986(v=vs.85).aspx) -->
<meta http-equiv="imagetoolbar" content="no">

<!-- Desativar o Windows theming para formar entradas / botões (https://support.microsoft.com/en-us/kb/322240) -->
<meta name="MSThemeCompatible" content="no">

<!-- Desativar um recurso que só apareceu no IE 6 beta (https://stackoverflow.com/q/2167301) -->
<meta name="MSSmartTagsPreventParsing" content="true">

<!-- Transições Interpage  (https://msdn.microsoft.com/en-us/library/ms532847(v=vs.85).aspx) -->
<meta http-equiv="Page-Enter" content="revealtrans(duration=2,transition=2)">
<meta http-equiv="Page-Exit" content="revealtrans(duration=3,transition=12)">
<meta http-equiv="Site-Enter" content="revealtrans(duration=2,transition=2)">
<meta http-equiv="Site-Exit" content="revealtrans(duration=3,transition=12)">
```

### 360 Browser

``` html
<!-- selecione motor de renderização, na ordem -->
<meta name="renderer" content="webkit|ie-comp|ie-stand">
```

### UC Mobile Browser

``` html
<!-- Bloqueia a tela para a orientação especificada -->
<meta name="screen-orientation" content="landscape/portrait">
<!--Mostrar esta página em tela cheia -->
<meta name="full-screen" content="yes">
<!-- Navegador UC irá exibir imagens mesmo em "modo texto" -->
<meta name="imagemode" content="force">
<!-- A página será exibida no "modo de aplicação" (tela cheia, gesto proibido, etc.) -->
<meta name="browsermode" content="application">
<!-- Desativada navegador UC "modo noturno" nesta página -->
<meta name="nightmode" content="disable">
<!-- Simplificar a página para reduzir a transferência de dados -->
<meta name="layoutmode" content="fitscreen">
<!-- Desativar o recurso do navegador da UC "dimensionamento de fontes para cima quando há muitas palavras esta página" -->
<meta name="wap-font-scale" content="no">
```

- [UC Browser Docs](http://www.uc.cn/download/UCBrowser_U3_API.doc)

### QQ Mobile Browser

``` html
<!-- Bloqueia a tela para a orientação especificada -->
<meta name="x5-orientation" content="landscape/portrait">
<!-- Mostrar esta página em tela cheia -->
<meta name="x5-fullscreen" content="true">
<!-- A página será exibida em "application mode"(fullscreen,etc.) -->
<meta name="x5-page-mode" content="app">
```

## App Links

``` html
<!-- iOS -->
<meta property="al:ios:url" content="applinks://docs">
<meta property="al:ios:app_store_id" content="12345">
<meta property="al:ios:app_name" content="App Links">
<!-- Android -->
<meta property="al:android:url" content="applinks://docs">
<meta property="al:android:app_name" content="App Links">
<meta property="al:android:package" content="org.applinks">
<!-- Web Fallback -->
<meta property="al:web:url" content="http://applinks.org/documentation">
<!-- Mais informações: http://applinks.org/documentation/ -->
```

- [App Links Docs](http://applinks.org/documentation/)

## Notas

### Performance

Movendo o atributo `href` para o início de um elemento melhora a compressão quando GZIP é ativado, porque o atributo` href` é usado nas tags `a`, `base` e `link`.

Exemplo:
```
<link href="https://fonts.googleapis.com/css?family=Open+Sans:400,700" rel="stylesheet">
```

## Outros Recursos

- [HTML5 Boilerplate Docs: The HTML](https://github.com/h5bp/html5-boilerplate/blob/master/dist/doc/html.md)
- [HTML5 Boilerplate Docs: Extend and customize](https://github.com/h5bp/html5-boilerplate/blob/master/dist/doc/extend.md)

## Projetos Relacionados

- [head-it](https://github.com/hemanth/head-it) uma interface simples para usar `head`.

## Contribuindo

Abra uma *issue* ou um *pull request* para sugerir alterações ou adições.

Por favor, siga estes passos para fazer o *pull request*:
- Modificar apenas uma *tag*, ou um conjunto relacionado de *tags* de cada vez;
- Use aspas duplas nos atributos;
- Não inclua uma barra final em elementos de fecho automático - a especificação HTML5 diz que eles são opcionais. Exemplo: `<img ... >`;
- Considerar a inclusão de um *link* para a documentação que suporte a sua mudança.

## Autor

**[Josh Buchea](http://joshbuchea.com/)**

### Tradutor

**[Suissa](https://github.com/suissa)**

## Licença

[CC0 License](LICENSE)

![CC0](http://i.creativecommons.org/p/zero/1.0/88x31.png "CC0")

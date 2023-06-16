<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

# xxAI.art

Një pjesë e kodit të faqes së internetit është me burim të hapur, të mirëpritur për të ndihmuar në optimizimin e përkthimit.

## kodi i pjesës së përparme

* [kodi i pjesës së përparme](https://github.com/xxai-art/web)
* [Paketa gjuhësore për sitin në tërësi](https://github.com/xxai-art/web/tree/main/i18n)
* [Paketa gjuhësore për modulet e hyrjes](https://github.com/wacpkg/user/tree/main/ui.i18n)
* [Dokumentacioni shumëgjuhësh i faqes në internet](https://github.com/xxai-doc)

Gjuha e programimit të përparme është [@w5/coffee_plus](http://npmjs.com/@w5/coffee_plus) , e cila shton disa veçori bazuar në sintaksën e coffeescript, shih [./coffee_plus.md](./coffee_plus.md) .

## Ndërkombëtarizimi i faqeve të internetit dhe dokumenteve

Ndërtoni mbi 3 projektet e mëposhtme

* [@w5/mdt](https://www.npmjs.com/package/@w5/mdt)

  Prapashtesa është `.mdt` , ju mund të përdorni sintaksën e ngjashme me `<+ ./coffee_plus/import.js>` për t'iu referuar skedarëve të jashtëm dhe për të gjeneruar shënime me prapashtesën `.md` .

* [@w5/trmd](https://www.npmjs.com/package/@w5/trmd)

  Përkthimi i Markdown nuk do të përkthejë kodet dhe lidhjet dhe do të fshehë fjalitë e përkthyera. Nëse përkthimi është modifikuar, por teksti origjinal nuk është modifikuar, ekzekutimi i tij përsëri nuk do të mbishkruajë modifikimin e përkthimit.

* [@w5/i18n](https://www.npmjs.com/package/@w5/i18n)

  Skedarët e gjuhës për përkthimin e faqeve të internetit të krijuara nga `yaml` .

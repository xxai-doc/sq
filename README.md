<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

Rekomandohet që fillimisht të instaloni nodejs, [direnv](https://direnv.net) , [bun](https://github.com/oven-sh/bun) dhe më pas `direnv allow` pasi të keni hyrë në direktorium ( [.envrc](https://github.com/xxai-art/doc/blob/main/.envrc) do të ekzekutohet automatikisht pas hyrjes në drejtori).

Kuptimi është: përkthimi kinez në japonisht, koreanisht, anglisht, përkthim anglisht në të gjitha gjuhët e tjera. Nëse dëshironi të mbështesni vetëm gjuhën kineze dhe angleze, thjesht mund të shkruani `zh: en` .

Kuptimi është: përkthimi kinez në japonisht, koreanisht, anglisht, përkthim anglisht në të gjitha gjuhët e tjera. Nëse dëshironi të mbështesni vetëm gjuhën kineze dhe angleze, thjesht mund të shkruani `zh: en` .

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

### Udhëzime për automatizimin e përkthimit të dokumenteve

Shikoni depon e kodit [xxai-art/doc](https://github.com/xxai-art/doc)

Rekomandohet që fillimisht të instaloni nodejs, [direnv](https://direnv.net) , [bun](https://github.com/oven-sh/bun) dhe më pas `direnv allow` pasi të keni hyrë në direktorium ( [.envrc](https://github.com/xxai-art/doc/blob/main/.envrc) do të ekzekutohet automatikisht pas hyrjes në drejtori).

Për të shmangur bazën e madhe të kodit të përkthyer në qindra gjuhë, krijova një bazë të veçantë kodi për secilën gjuhë dhe krijova një organizatë për të ruajtur bazën e kodit

Vendosja e variablit të mjedisit `GITHUB_ACCESS_TOKEN` dhe më pas ekzekutimi [i create.github.coffee](https://github.com/xxai-art/doc/blob/main/create.github.coffee) do të krijojë automatikisht depon e kodit.

Sigurisht, mund ta vendosni edhe në një bazë kodi.

[Drejtimi i](https://github.com/xxai-art/doc/blob/main/run.sh) referencës së skenarit të përkthimit.sh

Kodi i skriptit interpretohet si më poshtë:

[Bunx](https://bun.sh/docs/cli/bunx) është një zëvendësim për npx, i cili është më i shpejtë. Sigurisht, nëse nuk keni të instaluar bun, në vend të kësaj mund të përdorni `npx` .

`bunx mdt zh` jep `.mdt` në direktorinë zh si `.md` , shikoni 2 skedarët e lidhur më poshtë

* [kafe_plus.mdt](https://github.com/xxai-doc/zh/blob/main/coffee_plus.mdt)
* [kafe_plus.md](https://github.com/xxai-doc/zh/blob/main/coffee_plus.md)

`bunx i18n` është kodi bazë për përkthim (nëse keni të instaluar vetëm `nodejs` , por `bun` dhe `direnv` nuk janë instaluar, mund të ekzekutoni gjithashtu `npx i18n` për të përkthyer).

Ai do të analizojë [i18n.yml](https://github.com/xxai-art/doc/blob/main/i18n.yml) , konfigurimi i `i18n.yml` në këtë dokument është si më poshtë:

```
en:
zh: ja ko en
```

Kuptimi është: përkthimi kinez në japonisht, koreanisht, anglisht, përkthim anglisht në të gjitha gjuhët e tjera. Nëse dëshironi të mbështesni vetëm gjuhën kineze dhe angleze, thjesht mund të shkruani `zh: en` .

E fundit është [gen.README.coffee](https://github.com/xxai-art/doc/blob/main/gen.README.coffee) , e cila nxjerr përmbajtjen midis titullit kryesor dhe nëntitullit të parë të `README.md` të secilës gjuhë për të gjeneruar një hyrje `README.md` . Kodi është shumë i thjeshtë, mund ta shikoni vetë.

Google API përdoret për përkthim falas. Nëse nuk mund të hyni në Google, ju lutemi konfiguroni dhe caktoni një përfaqësues, si p.sh.

```
export https_proxy=http://127.0.0.1:7890 http_proxy=http://127.0.0.1:7890 all_proxy=socks5://127.0.0.1:7890
```

Skripti i përkthimit do të gjenerojë një memorie të përkthyer në drejtorinë `.i18n` , ju lutemi kontrolloni atë me `git status` dhe shtojeni në depon e kodit për të shmangur përkthimet e përsëritura.

Ju lutemi, ekzekutoni `bunx i18n` sa herë që modifikoni përkthimin për të përditësuar cache.

Nëse teksti origjinal dhe përkthimi modifikohen në të njëjtën kohë, cache do të ngatërrohet, kështu që nëse dëshironi të modifikoni, mund të modifikoni vetëm një dhe më pas ekzekutoni `bunx i18n` për të përditësuar cache.

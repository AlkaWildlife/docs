# Typy správcovských účtů

Weby jsou hostovány na platformě [Netlify][netlify] a obsah je spravován systémem [Netlify CMS][netlify-cms] a [GitHub][github]. I přes podobné jméno mají oba systémy rozdílné účty.

## Účet pro správu hostingu

Drtivá většina věcí zde je technického charakteru a ty, které nejsou, jsou zajištěny i jinou metodou. Nicméně pro zastupitelnost administrátorů je dobré vědět i o této vrstvě celého řešení.

Nové administrátory je možné přidat po přihlášení přidat výběrem konkrétního webu a přechodem na Settings v horní navigační nabídce. Poté navigační nabídce vlevo na stránce výběrem volby Site administrators.

## Účet pro správu obsahu

Obsah je uložený na platformě GitHub sloužící ke sdílení kódu. Pro uživatelský přívětivější správu je možné použít Netlify CMS.

Správce obsahu lze po přihlášení na GitHub přidat ze [správy členů organizace ALKA Wildlife][github-people] a aktivací tlačítka „Invite member“.

# Správa obsahu

Administrace pomocí Netlify CMS je na každém webu dostupná na adrese `/admin/`, která se připojí za doménové jméno webu.

Při první přihlášení je nutné potvrdit přístup CMS k datům na GitHubu. Poté se už otevře samotné CMS.

V horním liště je možné přepínat v levé části otevřít správu obrázků. V pravé část je možnost rychlé přidání různých typů obsahu nebo odhlášení z administrace.

## Položky v navigační nabídce webu

Při správě stránek v Content pages a Special pages je možné si všimnout přepínače „Show in the navigation menu“. Tento přepínač určuje, zda se stránka objeví v navigační nabídce spravovaného webu. Hierarchie stránek je daná strukturou jejich adresy, kde je jako oddělovač úrovní použit znak lomeno, tj. `/`. Například stránka „O nás“ může mít adresu `/o-nas` a její podstránka „Projekty“ by poté měla adresu `/o-nas/projekty`. Special pages mají adresy neměnné nicméně v jejich případě nemá smysl, aby měly podstránky.

Pořádí položek v navigační nabídce je dané hodnotou v poli „Position among siblings in the navigation menu“, která by měla být hned za přepínačem.

## Obtékání obrázku textem

Na webu jsou obrázky, které jsou součástí odstavce, bez dalších úprav zobrazeny na jednom řádku textu. Nicméně většinou jsou obrázky vyšší než jeden řádek a proto je žádoucí toto standardní chování upravit.

Bohužel Netlify CMS neumožňuje toto chování měnit přes své nástroje a je potřeba použít zvláštní syntaxi.

Ihned za obrázek (bez odřádkování a bez mezer) je potřeba vložit text `{: .wysiwyg-float-left}` pro obtékání textu zprava (obrázek plave textem vlevo) nebo `{: .wysiwyg-float-right}` pro obtékání textu zleva (obrázek plave textem vpravo).

Někdy je zároveň vhodné obtékání ukončit dříve a nenechat veškerý následující text obrázek obtékat. K tomu složí tzv. clearfix. Ten je možné vložit z doplňkové nabídky v panelu nástrojů textového editoru.

## Nahrání a odkazování na PDF a jiné neobrázkové typy souborů

Netlify CMS momentálně dokáže z multimediálního obsahu spravovat pouze obrázky. Pro jiné typy souborů je momentálně nutné jít na [organizační účet na GitHub][github-org], vybrat spravovaný web, přejít do adresáře `media` a aktivovat tlačítko „Upload files“.

Pro hypertextové odkazy se poté použije adresa začínající `/media/` a následovaná názvem nahraného souboru. Pokud tedy nahraju soubor „Skvělé PDF.pdf“, jeho adresa bude `/media/Skvělé PDF.pdf`.

[netlify]: https://www.netlify.com
[netlify-cms]: https://www.netlifycms.org
[github]: https://github.com
[github-people]: https://github.com/orgs/AlkaWildlife/people
[github-org]: https://github.com/AlkaWildlife
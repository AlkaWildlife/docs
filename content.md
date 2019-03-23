---
title: Správa obsahu webů ALKA Wildlife
---
Obsah je uložený na platformě [GitHub][] spolu se zdrojovým kódem webu. Přímo zde je možné obsah i vytvářet a editovat. Pro uživatelsky přívětivější správu je možné použít [Netlify CMS][netlify-cms] (dále jen „CMS“). Formátování textu je zajištěno značkovacím jazykem [Markdown][], resp. jeho rozšířením [kramdown][].

# Přidání nového uživatele

Po přihlášení na GitHub je možné nového uživatele přidat ze [správy členů organizace ALKA Wildlife][github-people] přes tlačítko „Invite member“. Uživateli přijde email s pozvánkou do organizace, ve které je postup, jak své zapojení provede.

# Správa obsahu pomocí CMS

CMS má každý web svůj a lze jej najít na adrese `/admin/`, která se připojí za doménové jméno.

Při první přihlášení je nutné potvrdit přístup CMS k datům na GitHubu. Poté se už otevře samotné CMS.

V horní liště je v levé části možné přepínat mezi cílenou správou různých typů obsahu. Hlavní je komplexní správa obsahu, lze ale spravovat i obrázky. V pravé části je možné rychlé přidání různých typů obsahu nebo odhlášení z administrace.

Správa obsahu, dělí rozděluje obsah do kolekcí, které obsahují jednotlivé položky, které většinou odpovídají jedné samostatné stránce na web.

## Formátovaný text a vizuální editor

Hlavní text stránky a někdy i další texty použité třeba pro odkazování na tuto stránku lze editovat ve vizuálním editoru bez nutnosti zabývat se značkami Markdown značkami. CMS bohužel používá odlišné rozšiření Markdownu než kramdown a pro některé specifické operace je nutné přepnout z vizuálního režimu „**Rich Text**“ do režimu „**Markdown**“. V tomto řežimu je pouze čistý text bez doplňující funkcionality a značky je nutné vkládat ručně.

Obecně lze doporučit sžít se alespoň s nejčastěji používanou syntaxí námi používaného rozšíření [kramdown][] a vizuálnímu editoru se spíše vyhnout. Často jde o efektivnější úpravu textu nabízející více možností než vizuální editor, když je potřeba.

## Náhledy stránek

Běžně CMS otevře editovaný obsah v režimu, kdy levou půlku prohlížeče zabírají prvky pro editaci a pravou půlku zabírá náhled, kde jsou změny okamžitě vidět.

Většina obsahu má takové množství voleb pro editaci, že se tento režim nechová použitelně – posouvání se po stránce podivně skáče, někdy se stránka posouvá i sama apod. V takovém případě je nejlepší náhled vypnout pomocí tlačítka se symbolem oka v pravém horní rohu a zobrazit jej pouze pro kontrolu.

# Přidání položky do navigační nabídky webu

Stránky v kolekcích *Content pages* a *Special pages* mají přepínač „**Show in the navigation menu**“. Tento přepínač určuje, zda se stránka objeví v navigační nabídce spravovaného webu.

Hierarchie navigační nabídky je daná strukturou adresy stránek. Jako oddělovač různých úrovní slouží znak lomeno, tj. `/`. Například stránka „O nás“ může mít adresu `/o-nas` a její podstránka „Projekty“ by poté měla adresu `/o-nas/projekty`. Special pages mají adresy neměnné nicméně v jejich případě nemá smysl, aby měly podstránky.

Pořadí položek na stejné úrovni v navigační nabídce je dané hodnotou volby „**Position among siblings in listings**“. Tato volba zároveň určuje pořadí i na jiných výpisech – např. v pravém bočním panelu na stránkách s dvou sloupcovým rozvržením.

# Obtékání obrázku textem

Na webu jsou obrázky, které jsou součástí odstavce, bez dalších úprav zobrazeny na jednom řádku textu. Nicméně většinou jsou obrázky vyšší než jeden řádek a proto je žádoucí toto standardní chování upravit.

CMS bohužel neumožňuje toto chování měnit přes své nástroje a je potřeba použít zvláštní značky v „Markdown“ režimu editoru.

Ihned za obrázek (bez odřádkování a bez mezer) je potřeba vložit text `{: .wysiwyg-float-left}` pro obtékání textu zprava (obrázek plave textem vlevo) nebo `{: .wysiwyg-float-right}` pro obtékání textu zleva (obrázek plave textem vpravo).

Někdy je zároveň vhodné obtékání ukončit dříve a nenechat veškerý následující text obrázek obtékat. K tomu složí tzv. clearfix. Ten je možné vložit z doplňkové nabídky v panelu nástrojů textového editoru („+“ na jejím konci).

# Nahrání a odkazování na neobrázkové soubory

CMS momentálně nedokáže spravovat jiný multimediální obsah než obrázky. Pro jiné typy souborů jako **PDF** je tak nutné jít na [organizační účet na GitHub][github-org], vybrat spravovaný web, přejít do adresáře `media` a soubor nahrát pomocí tlačítka „**Upload files**“.

Pro hypertextové odkazy se poté použije adresa začínající `/media/` následovaná názvem nahraného souboru. Pokud tedy nahraju soubor „Skvělý dokument.pdf“, jeho adresa bude `/media/Skvělý%20dokument.pdf`. Z příkladu je vidět, že mezery v názvu souboru je vhodné nahradit kódem `%20`, nebo nepoužívat soubory s mezerami v názvu.

# Nový řádek, nikoli nový odstavec – odřádkování

CMS bohužel používá jinou syntaxi pro nový řádek než očekává náš web. Proto je potřeba použít zvláštní značku v „Markdown“ režimu editoru.

Na konec řádku, který chceme explicitně ukončit, vložíme dvě mezery. Bez nich Markdown odřádkování ignoruje a drží standardní tok textu v odstavci jakoby tam nebyly.

# Správa obsahu ve vztahu k přidruženým typům obsahu

Některé typy obsahu, jako například publikace na prezentačním webu ALKA Wildlife, jsou ve vztahu k jiným typům obsahu (např. **typ**, **kategorie** nebo stránky ve vztahu ke galeriím), které jsou spravovány odděleně. Poté často mohou nastat dva scénáře: je potřeba typ nebo kategorii přejmenovat, nebo přidat nový.

## Přidání nového typu přidruženého obsahu

Před vytvořením hlavního obsahu, je potřeba nejdříve vytvořit obsah, na který budeme odkaz (přidružený obsah). Například nejdříve vytvořím nový typ publikace a až poté vytvářím samotnou publikaci, která do tohoto typu patří.

## Změna názvu přidruženého obsahu

V situaci kdy se na přidružený název odkazujeme, je bohužel potřeba změnit tento název všude tam, kde se na něj odkazujeme. Například pokud změním název kategorie, musím najít všechen obsah v této kategorii (články v poradně a projekty) a tam změnit název na odkazovanou kategorii.

# Stránky na vícejazyčných webech

Mezi různými jazykovými mutacemi vícejazyčných webů lze přepínat. V případě, kdy má nějaká stránka ekvivalent ve druhé mutaci, je vhodné zadat volitelnou volbu „**Localized alternatives**“. Vlajka vedle hlavní navigační nabídky webu potom nebude odkazovat na úvodní stránku druhé jazykové mutace, ale přímo na svůj ekvivalent v jiném jazyce.

Využití této funkce je prospěšné i pro porozumění vztahu mezi námi spravovaným obsahem ze strany vyhledávačů.

[github]: https://github.com
[netlify-cms]: https://www.netlifycms.org
[markdown]: https://daringfireball.net/projects/markdown/syntax/
[kramdown]: https://kramdown.gettalong.org/syntax.html
[github-people]: https://github.com/orgs/AlkaWildlife/people
[github-org]: https://github.com/AlkaWildlife

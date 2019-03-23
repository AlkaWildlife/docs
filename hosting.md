---
title: Správa hostingu webů ALKA Wildlife
---
Služba [Netlify][] pro správu hostovaných používá webovou aplikaci dostupnou na [app.netlify.com][netlify-app]. Pokud není řečeno jinak, tak se veškeré úkony provádí po přihlášení v této aplikaci po výběru konkrétního webu.

Drtivá většina věcí zde je technického charakteru. Nicméně pro zastupitelnost administrátorů je dobré vědět i o této vrstvě celého řešení.

# Přidání nového uživatele

*Settings* v horní navigační nabídce → *General* v navigační nabídce vlevo → *Site administrators* v navigační nabídce v sekci General.

# Změna emailové adresy pro příjem dotazů z poradny

*Settings* v horní navigační nabídce → *Build & deploy* v navigační nabídce vlevov → *Continuous Deployment* v navigační nabídce v sekci Build & deploy → sekce *Build environment variables* níže na stránce.

Pokud je na webu aktivní poradna (v době psaní pouze česká mutace webu Vydry online), tak jsou v seznamu proměnné začínající `QUESTION_FORM_`. Proměnná `QUESTION_FORM_TO` potom obsahuje adresu, kam se dotazy zasílají.

Hodnota lze změnit přes tlačítko *Edit variables*, které je pod seznamem. Po úpravě hodnoty je potřeba změny uložit tlačítkem *Save* a provést nové nasazení. Nové nasazení lze provést buď změnou obsahu, nebo je potřeba říct vývojovému týmu, aby vytvořil prázdný commit.

[netlify]: https://www.netlify.com
[netlify-app]: https://app.netlify.com

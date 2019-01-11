Laddningstid
=======================

Denna uppgift handlar om att analysera webbplatsers laddningstid och användbarhet samt vad som kan förbättras med tanke på laddningstid och användbarhet.

Urval
-----------------------

Jag har valt att arbeta med tre webbplatser;
<a href="https://www.aftonbladet.se/">Aftonbladet</a>,
<a href="https://tinkerwatches.com/">Tinker</a> och
<a href="https://www.dailymotion.com">Dailymotion</a>.

Aftonbladet var ett självklart förstaval då jag alltid irriterat mig över hur seg och fullsmäckad med reklam deras webbplats är. Tinker valde jag för att jag personligen gillar sidan samt använde den i förra veckans rapport om färgscheman. Slutligen så valde jag Dailymotion, då det ytterligare verkar vara en webbplats som inte hade mått dåligt av en uppsnabbning.

Metod
-----------------------

När det kommer till metod så har jag valt att arbeta med PageSpeed Insights samt Google Chrome Devtools för att mäta laddningshastigheter och resurserna som laddas in. Utöver detta så har jag använt mig av Google Spreadsheets för att hålla koll och räkna på informationen jag kommer fram till.

Resultat
-----------------------
<h5>Aftonbladet</h5>
<figure class="figure right">
    <img src="image/snapshots/aftonbladet.png?w=450"></img>
</figure>

När jag körde Aftonbladets hemsida genom PageSpeed Insights så fick den 70 i desktop och 55 i mobilt läge. Jag kan tänka mig att dom inte lagt jättemycket kraft på att optimera deras hemsida för mobila användare eftersom dom flesta troligtvis använder sig av deras app då istället för att besöka hemsidan i webbläsaren. Aftonbladet skulle kunna snabba upp sin webbplats genom att leverera kritisk JavaScript och CSS direkt för att kunna börja rita ut sidan och skjuta upp på mindre viktig JS/CSS, detta skulle enligt PageSpeed spara dem 1,26 sekunder, vilket hade varit en 12% förbättring. Något annat dom hade kunnat göra för att förbättra prestandan på deras hemsida hade varit att använda färre DOM noder, i min mätning fick jag fram att dom använde 3349 noder när det rekommenderade antalet är under 1500.

Genom mina tester så fick jag reda på att det tar Aftonbladet i snitt 10,28 sekunder att ladda fullt, vilket jag tror beror till stor del på mängden bilder samt självklart alla annonser och reklamer, då jag gjorde alla dessa tester utan AdBlock. Det går dock att börja använda sidan innan den är fullt laddad, det sista som laddas in är annonser och reklamer. Mängden data som behövdes läsas in var 2,77 MB, vilket gör den till den största hemsida av dom jag undersökt. Bilderna i sig är små och lagom anpassade, men den stora mängden bilder och animerade annonser är det som höjer resurserna och ger Aftonbladet förstaplatsen.

<h5>Tinker</h5>
<figure class="figure right">
    <img src="image/snapshots/tinker.png?w=450"></img>
</figure>

Tinker tar ledningen med sitt desktopresultat 89 på PageSpeed. Dock när det kommer till mobilt läge så får den endast en klen 17. Något Tinker skulle kunna göra för att spara tid för både desktop- och mobilanvändare är att anpassa bildstorleken ordentligt. Desktop skulle spara 1,75 sekunder medans en mobilanvändare skulle spara 7,38! Något annat som görs väldigt dåligt i mobilversionen av Tinker är renderingen av bilder. Det verkar som hemsidan laddar in alla bilder först, även dom som inte visas på skärmen, det uppskattas att detta skulle spara dem hela 11,28 sekunder! Något annat intressant som jag inte sett i någon annan undersökning är rekommendationen att dom använder ett nyare bildformat istället för PNG och JPEG, till exempel JPEG 2000 eller WebP då dessa två get mycket bättre komprimeringsmöjligheter.

Efter DevTools-testerna så har jag kommit fram till att Tinker tar i snitt 2,01 sekunder att ladda fullt i sin desktopversion, vilket utan tvekan är det snabbaste resultatet av alla tester jag gjort. Resursmässigt så tar hemsidan upp 2,77 MB, vilket beror på dom högupplösta och felanpassade bilderna. Något annat intressant jag fick reda på var att Tinker har med en del oanvänd CSS, vilket faktiskt förlänger laddningsprocessen med 0,39 sekunder.

<h5>Dailymotion</h5>
<figure class="figure right">
    <img src="image/snapshots/dailymotion.png?w=450"></img>
</figure>

I sin desktopversion så hänger Dailymotion med någorlunda med 70 poäng på PageSpeed, dock så sitter hemsidan även på ett rekorddåligt resultat för sina mobilanvändare, ett fantastiskt 17. Enligt PageSpeed så hade Dailymotion kunnat spara in sammanlagt 14,8 sekunder på att optimera sitt JavaScript, både genom att minimera "main-thread work", samt reducera tiden det tar för JS att exekvera. Dom skulle kunna förbättra detta genom att lägga mindre tid på att kompilera samt exekvera, och istället dela upp och skicka JS i mindre grupperingar. Precis som med dom andra hemsidorna så är Dailymotion dåliga på att skjuta upp renderingen av bilder som inte visas på skärmen, detta hade kunnat spara dem ytterligare 1,14 sekunder. När det kommer till desktopversionen så finns det mycket andra saker dom kan förbättra. För och främst så skulle dom kunna spara 3.04 sekunder på att använda rätt bildstorlekar och bra komprimerade bilder. Utöver det så skulle dom verkligen kunna arbeta på att minska mängden DOM noder, som jag skrev ovan är under 1500 idealt, under denna mätning använde Dailymotion 8134 stycken.

Efter att ha undersökt Dailymotion i DevTools så har jag kommit fram till att webbplatsen tar i snitt 10,77 sekunder att ladda fullt, vilket är den längsta tiden av alla sidor jag testat. När det kommer till mängd resurser som behövdes laddas så var Dailymotion minst med endast 1,5 MB, vilket tyder på att deras mobilversion använder sig av en lämplig bildstorlek.

Analys
-----------------------
Ett problem som kan uppstå när en hemsida vill använda sig av mycket annonser eller reklam som jag lade märke till på Dailymotion är då hemsidan är utformad för att ladda in reklamfönstren först, innan innehållet på hemsidan. Detta fördröjer informationen användaren kom dit för att se och segar ner hemsidan som helhet avsevärt eftersom användaren då måste vänta på att dom icke-intressanta reklamerna ska laddas in först. Detta problem var väldigt tydligt på Dailymotion, där var reklamen det första man såg, och sen efter det ploppade alla relevanta bilder in samtidigt. Detta märkte jag inte lika tydligt på Aftonbladets hemsida då innehållet laddas in först så man kan börja läsa, och sen eftersom laddas även reklamen in.

Ett genomgående tema bland dessa webbplatsers mobilversioner verkar vara att ladda bilder i tokig ordning. Detta är något jag personligen aldrig reflekterat över men det är ju väldigt logiskt, eftersom skärmen är mindre så omplaceras bilder, några kanske utanför skärmen. Varför ska dom då laddas in samtidigt som det som faktiskt visas på skärmen? Ett annat vanligt problem var bildkomprimering och bildstorlekar, detta var något som alla hade mer eller mindre problem med. Konstigt nog så verkade det ge mest problem på desktopversioner, vilket förvånar mig en del då jag hade gissat att det varit tvärt om. Kanske det är så att dom inte använder någon anpassning alls för olika storlekar av datorskärmar, men när skärmarna krymper ända ner till mobilstorlek så har alla med någon form av nödvändig anpassning.

Om jag skulle rangordna webbplatserna efter deras mätvärden så skulle jag ge medaljen till Tinker med Aftonbladet på en andraplats och Dailymotion en bra bit där bakom. Tinker känns som den självklara vinnaren då den sopar banan med dom andras desktopversioner, men även hänger med dugligt på den mobila fronten. Tinkers stora svaghet var deras bildstorlekar och missanpassningar, vilket jag personligen kan ha lite överseende med då deras mål är att visa upp sina klockor, och självklart vill dom visa dom i bästa möjliga kvalitet. Om jag skulle sätta en siffra på vilken laddningstid jag själv klassar som snabb eller långsam så skulle jag säga att allting under 2 sekunder är snabbt, medans om det börjar gå upp över 5 så blir det långsamt. Med detta i åtanke så skulle jag klassa Tinker som en snabb hemsida och dom andra två som väldigt långsamma, vilket komiskt nog är exakt den uppfattningen jag hade redan innan jag satte mig in i detta arbete.

Övrigt
-----------------------

Uppgiften utfördes av mig, Max Assermark 12/12-18.

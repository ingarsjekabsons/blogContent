---
title: Vai nesarežģītas programmas var risināt sarežģītas problēmas?
---
Jūs taču piekritīsiet, ka lielāka problēma mūsdienās ir programmatūru uzturēt nekā to sākotnēji piegādāt, vai ne? Nu vismaz tikpat liela problēma.<!--more-->

Lai programmatūru uzturētu, lai tai pierakstītu klāt jaunu funkcionalitāti, šī programmatūra ir jāsaprot. Loģiski? Loģiski.
Realitātē bieži šīs funkcijas ir jāveic cilvēkam, kas nav piedalījies pie programmatūras tapšanas. Tieši tāpēc spēja saprast kāda cita uzrakstītu kodu ir tik svarīga.

Kādā veidā tad tiek mēģināts saprast šo kodu?
Klasiski tie ir divi veidi:
- "black-box" testing. Programmatūra tiek pētīta "no ārpuses" - t.i. - kā programma uzvedās pie kādiem konkrētiem ieejas datiem. Šādus testus vēl mēdz saukt arī par "exploratory" testiem.
- t.s. "informal reasoning". Programma tiek pētīta "no iekšpuses", citiem vārdiem - lasītas specifikācijas un kods.

Grūtības saprast kodu rada koda sarežģītība.

Bet tomēr, kas ir tā "sarežģītība" un kas to rada?
Ir daži veidi, kā ir pieņemts mērīt sarežģītību, visizplatītākais veids laikam ir ciklomātiskā kompleksitātes metrika (_**cyclomatic complexity metric**_), kas, tā īpaši neiedziļinoties detaļās, ir skaitlis, kas norāda izpildes ceļu skaitu kādā koda gabalā (funkcijā, modulī utt.). Ļoti vienkārši - jo lielāka šī metrika, jo kods ir sarežģītāks. Ir vēl arī citas mērīšanas metodes, kur tiek skaitīti dažādi lielumi kodā - operatoru skaits, operandu skaits u.c. Šādas metodes man personiski liekas šarlatāniskas, jo tām formulām es neredzu nekādu pamatu, kā tikai to, ka tās ir iegūtas empīriskā veidā uz kaut kādiem vēsturiskiem datiem.

Secinājums - jo vairāk koda un vairāk operatoru un operandu, jo kods potenicāli ir sarežģītāks. Nedod Dievs vēl ir zarošanās kodā, tas sarežģītību palielina vēl vairāk. Hmm. It kā ļoti vienkārši, bet tai pašā laikā paliek tāda nolemtības pēcgarša - nesarežģīts kods nav iespējams?

Ok, mēģināsim saprast, kas rada sarežģītību, abstrahējoties no koda rindiņu skaita un zarošanās.

Kāpēc vispār tiek rakstīts kods? Tāpēc, ka ir kāda problēma, kas ir jāatrasina. Risināmās problēmas ir dažādas - no vienkāršākām izdrukāt "hello world" uz ekrāna līdz sarežģītām finanšu uzskaites sistēmām vai orbītas aprēķināšas un kalibrēšanas programmām kosmosa izpētes zondēm.
Tātad, pilnīgi loģiski, ka programmatūras sarežģītība ir atkarīga no risināmās problēmas sarežģītības.

Bet vai tas ir viss? Vai nav citu sarežģītības cēloņu? Protams, ir. Vienkārši runājot, tie ir visi apkārtējie apstākļi, kas rodas risinot pamatproblēmu. Tādi kā - integrācijas ar citām sistēmām, lēnas datubāzes, diski utt.

Datorzinātņu literatūrā daudz kur šiem abiem sarežģītības veidiem ir savi pieņemtie nosaukumi - _**Essential complexity**_ un _**Accidental complexity**_.
No _**Essential complexity**_ nav iespējams izvairīties (izņemot, protams, nerisināt problēmu vispār :)). Savukārt no _**Accidental complexity**_ gan var. Tas gan nav ne vienkārši un ne vienmēr iespējami.

Jau labāk, esam apzinājušies sarežģītības, no kurām ir iespējams izvairīties un no kurām nevar.

Nu labi. Bet varbūt ir veidi kā minimizēt programmu sarežģītību vēl tālāk? **Varbūt ir iespējams risināt sarežģītas problēmas rakstot nesarežģītas programmas?**

Meklējot atbildi uz šādu jautājumu es atradu labu lasāmgabalu - tādu man nezināmu cilvēku kā Ben Moseley un Peter Marks sarakstītu papīru _**"Out of the Tar Pit"**_. Pieļauju, ka neesmu dikti unikāls, ka esmu lasījis šo papīru, ticu, ka šis ir populārs lasāmgabals.

Šis papīrs nav dikti sens, tas ir sarakstīts 2006. gadā, tātad vēl diezgan svaigs. Šeit tiek apsktatīts tuvāk, kas tieši kodā veicina tā sarežgītību, tiek apskatīts imperatīvs kods. Ņemot vērā, ka šobrīd izplatītākās valodas un programmēšanas paradigmas tomēr ir imperatīvas, tad var uzskatīt, ka kods _in general_.

Trīs galvenās lietas - _**complexity caused by state**_, _**complexity caused by control**_, _**complexity caused by code volume**_.

## Complexity caused by state

Imperatīvs kods nevar pastāvēt bez stāvokļiem. Tieši tāpēc tas ir imperatīvs. Cikliem ir vajadzīgs skaitītājs; mainīgajiem mainās vērtība; globālie mainīgie lai gan tiek uzskatīti par sliktiem, tomēr tiek plaši lietoti. Šie visi ir stāvokļi ("steiti").
Un šī, manuprāt, ir lielākā imperatīva koda problēma - šādu kodu ir grūti izprast. Jo vairāk stāvokļi vienlaicīgi tiek menedžēti, jo sarežģitāk ir izprast un izsekot programmas izpildei. (šī pēc būtības ir manis augstāk pieminētā ciklomātiskā kompleksitāte).

## Complexity caused by control

Imperatīvā kodā mēs kontrolējam komandu izpildes secību. Precīzāk - mēs esam spiesti to darīt. Šo, iespējams, ir grūti uztvert kā reālu problēmu, lielākā daļa no mums kopš pamatskolas laikiem ir programmējuši imperatīvi, tas ir asinīs. Mēs esam mācīti, ka programmēt nozīmē datoram teikt precīzi ko un tieši kā darīt. Tomēr nē, deklaratīvās un funkcionālās valodās tas nav jādara, tas nav obligāti. Faktistki tas nozīmē, ka lasot kodu ir jāspēj emulēt dators. Reizēm tas īpašas grūtības var nesagādāt, reizēm tas sagādā lielas grūtības.

## Complexity caused by code volume

Visvienkāršākā sarežģītība - koda daudzums, šo var vienkārši izmērīt. Tomēr šis ir nemazāk svarīgs aspekts, it īpaši apvienojumā ar diviem iepriekšējiem aspektiem. Gala kompleksitātē koda daudzums ir reizinātājs stāvokļa un secības kompleksitātēm.

Varbūt šīs problēmas var risināt savādāk? Laba dokumentācija, precīzas specifikācijas, plašs testu pārklājums kodam? Atļaušos nepiekrist. Neviena no šīm lietām nevar atsvērt labu un viegli lasāmu kodu. Daudz testi un liels to pārklājums arī ir vājš mierinājums, kā teicis Djikstra - testēšana ļoti efektīvi parāda kļūdu klātbūtni, nekad to neklātbūtni.

Vai vispār ir iespējams programmēt cilvēkiem derīgas programmas nedarot nevienu no trim minētajiem grēkiem?. Es esmu pārliecināts, ka var, tikai paradigmu šifts nenotiek ātri.
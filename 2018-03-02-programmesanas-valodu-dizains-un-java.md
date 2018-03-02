---
title: Programmēšanas valodu dizains un Java
---

Šodien noskatījos lielisku **_Guy Steele_** 1998. gada uzstāšanos. Šis video man jau labu laiku stāvēja _"skatīties vēlāk"_ sarakstiņā, un ilgāku laiku nevarēju atrast motivāciju noskatīties tik smadzeņietilpīgu video. Šis video ir jau pieminētā džentelmeņa uzstāšanās ar nosaukumu **"Growing a language"**. Šajā runā Gaijs stāsta par programmēšanas valodu dizainu; kā to veidot, lai valoda izaugtu; veidus kā veicināt valodas izaugsmi un dažādi temati ap šo. Ir dažas lietas, kas man ļoti piesaistīja uzmanību tieši kontekstā ar **Java** valodas dizainu kā to aprakstīja Gaijs 1998. gadā, un kāds tas ir šodien.
<!--more-->
Šis video tiešām ir labs, es pat teikšu vēl vairāk - viens no labākajiem par valodu dizainu. Silti iesaku noskatīties - [video atrodas te](https://www.youtube.com/watch?v=_ahvzDzKdB0). Video ir gandrīz stundu garš un mentāli ļoti ietilpīgs, tāpēc, pirms skataties, sagatavojiet krūzi ar ko dzeramu.

Principā, video jau tagad 20 gadus vēlāk joprojām ir aktuāls, un es domāju, ka vēl pēc 20 gadiem viņš savu aktualitāti nebūs zaudējis.

Tie, kam video liekas garš un negrib to skatīties, es varu ieteikt tikai vienu - skatieties!

Veids, kā Gaijs pasniedz savu sakāmo ir leģendārs, runas sākumā viņš nodefinē dažu vārdu nozīmi pakāpienveidā - t.i. - ar jau zināmu vārdu palīdzību nodefinē nākamos. Tālāk, runas gaitā viņš turpina nodefinēt jaunu vārdu nozīmi, tiklīdz tāds ir vajadzīgs, lai izteiktu savu nākamo domu.
Nevarētu teikt, ka tiem definētajiem vārdiem ir ļoti kritiska loma viņa teiktajai domai, taču tas vienreizēji precīzi ilustrē programmēšanas valodas dizaina problēmas.
Jeb kā latviski saka - _"proves the point"_.

Viena no lietām, kas tiek uzsvērta, ir kļūda mēģināt uzdizainēt lielu valodu uzreiz (kādreiz tas nebija pašsaprotami), jo tam ir vajadzīgs daudz laika, to nevar izdarīt ātri. Ar "_lielu_" šeit kontekstā tiek saprasts ar "daudz _vārdiem_" un ar _vārdiem_, savukārt, šeit tiek saprastas valodā iebūvētās izteiksmes, metodes utt.

Lielisks bija salīdzinājums valodu dizainā, kur "lietotāji" spēj bagātināt valodu ar savām definīcijām un tādām, kur to nevar izdarīt, ar katedrāles un tirgus būvēšanu. Vienā gadījumā ir "māsterplāns", kur lielākā daļa svarīgie lēmumi jau ir pieņemti, pretstatā otram, kur tas notiek pakāpeniski, nepārtraukti.

Christopher Alexander citāts, kas tiek piesaukts runā:

> Master plans have two additional unhealthy characteristics. To begin with, the existence of a master plan alienates the users . . . After all, the very exis- tence of a master plan means, by definition, that the members of the community can have little impact on the future shape of their community, because most of the important decisions have already been made. In a sense, under a master plan people are living with a frozen future, able to affect only relatively trivial details. When people lose the sense of responsibility for the environment they live in, and realize that they are merely cogs in someone else’s machine, how can they feel any sense of identification with the community, or any sense of purpose there?

Tomēr šī ideja tiek attīstīta tālāk, ir nepieciešams plāns kā augt - nevis izstrādāt māsterplānu augšanai, bet plānu kā veicināt augšanu turpmāk. 

Un tam seko lieliska definīcija jēdzienam **"meta"**, es centīšos šo definīciju tagad uzrakstīt latviski:

> Meta nozīmē pakāpties soli augstāk no vietas, kur tu atrodies. <br />
> Tas ko tu līdz šim darīji, tagad ir tas, ko tu redzi. <br />
> Tas, kas tu biji, tagad ir tas, ar ko tu strādā. <br />
> Darbības vārdi kļūst par lietvārdiem. <br />
> Tas, kas bija paterns, tagad ir lieta, ko var ielikt kāda paterna vietā.

Vai šis nav **lie-li-ski**?

Un, ja tā padomā, šis ir lielisks veids kā pastāstīt kādam, kas ir higher-order funkcijas :)
Manuprāt, šis skaidrojums arīdzan lieliski ilustrē robežu starp funkcijām un datiem izzušanu. 

Kad mēs esam meta, funkcijas ir dati.

Šim seko doma, ka līdzšinējie valodu dizaini ir jālieto kā paterni programmām.
Ka programmēšanas valodu dizainiem tagad ir jākļūst par patterniem programmēšanas valodu dizainiem. Ka programmēšanas valodas vairs nevar būt lieta, tām ir jābūt paterniem.

> We need now to go meta.

Viscaur runai, tiek pieminēta Java. Un tas ir pašsaprotami, Gaijs tobrīd strādāja **_Sun Microsystems_** (tagad **_Oracle_**, kur starpcitu, strādā joprojām) un atradās diezgan tuvu Goslingam un pārjiem Java dizaineriem.

Viena no vairāk izceltām īpašībām valodai ir tas, ka valodai ir jāsatur tikai ļoti vienkāršus "vārdus". Tiek piesaukts salīdzinājums ar angļu valodu, kur _primitīvi_ ir lietvārdi ar vienu patskani. Pārējie ir definēti ar šo primitīvu palīdzību.

Man, personīgi, Java asociējas ir tādiem klašu nosaukumiem kā **AbstractConnectorFactoryBaseObserver** vai - **SimpleBeanFactoryAwareAspectInstanceFactory**. Un otro es neizdomāju, tāda klase tiešām eksistē.

Toreiz Gaijs teica, ka viņaprāt Javai pietrūkst _Generic Types_ un operatoru overloudošana (kas C++ jau toreiz bija), neko stipri vairāk nevajag. Gaijs Stīls pirms 20 gadiem lika likmi, ka Java būs izdevusies valoda, ja piedāvās "meta-programmēšanu", un, man personīgi liekas, ka viņam būs bijusi taisnība. Tas viss, pluss "write once, run everywhere".

Tas, vai Java nav kļuvusi pārāk izdevusies, ka tā sāk lūst pati zem sava svara - tas ir cits jautājums :)

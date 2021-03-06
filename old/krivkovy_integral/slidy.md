% Křivkový integrál
% Robert Mařík
% 2014–2019

# Křivkový integrál

Jedná se o rozšíření Riemannova integrálu, kdy množinou přes kterou
integrujeme není úsečka, ale křivka. Pro jednoduchost budeme uvažovat
dvourozměrnou křivku v rovině $x$, $y$.

Rozeznáváme dva druhy křivkových integrálů. První z nich používáme,
pokud pracujeme se skalárními veličinami, jako například kvadratický
moment. Druhý z nich používáme pokud pracujeme ve vektorovém poli,
například při výpočtu práce vykonané po křivce.

<div class="sloupce">

![Křivkový integrál prvního druhu](krivkovy_integral_prvniho_druhu_1.png)

![Křivkový integrál druhého druhu](krivkovy_integral_druheho_druhu_1.png)

</div>
# Parametrické rovnice křivky

<div class="sloupce">


Nejprve představíme matematický aparát pro popis křivek.  Rovinné
křivky nejčastěji popisujeme vektorovou funkcí jedné proměnné,
resp. dvojicí skalárních funkcí.

* $\vec r: \mathbb{R}\to \mathbb{R}^2$
* $\vec r(t)=[\varphi(t),\psi(t)]=\varphi(t) \vec i + \psi(t)\vec j$, $t\in [\alpha,\beta]$
* Skalární popis křivky: $$C=\begin{cases}
    x=\varphi(t)\\y=\psi(t), \quad t\in[\alpha,\beta]
  \end{cases}$$
* Graf křivky dostaneme tak, že pro každé $t$ z intervalu $[\alpha, \beta]$ kreslíme ve 2D bod $[\varphi(t), \psi(t)]$.
* Funkce $\varphi(t)$, $\psi(t)$ nazýváme *parametrizace* křivky $C$
* Pro danou křivku $C$ v rovině $xy$, nejsou její parametrické rovnice dány jednoznačně. [Nakreslit online.](https://sagecell.sagemath.org/?z=eJxtkcFugzAMhu9IvEMEhyRbpC1o2i3nXfMERR5Nu4iQoGAx0qcfgY5DVd8s-_v_3_IMkdGFJMrLoizquiYxzN52howxkD7auU9l4ZUsi4UhV12YGJ78up1yO1l_b3d4MLedHCHCYDCWBQ7WCxxgUe-CNS-j5Scm33Zkg55UnmipRheQZVvBUBw6XBBnrsafWwffximaN3L-ldDydYPSE6gLLkRFoznTR4V0V5h-wi_TUpCLvU72ZhT7FB8rihadUdVXhEsi2Y4ASSzxartCN-r_XNu1m_-eOss-xDhMGgHTaDpsI6ANSh4m-pDqYX8AVPwPID58GQ==&lang=sage)
* Parametrizace kružnice, úsečky a grafu funkce jedné proměnné: viz [seznam vzorců](http://user.mendelu.cz/marik/am/cheatsheet.pdf)

![Dvě různé parametrizace jednotkové kružnice](parametricke_krivky.png)

</div>

# Křivkový integrál prvního druhu

<div class="sloupce">
Pokud uvažujeme drát o lineární hustotě $f$ a délce $s$, je hmotnost
drátu rovna součinu $m=fs$. Uvažujme drát, který není homogenní, leží
podél rovinné křivky $C$ a jeho specifická hmotnost se mění a bodě
$(x,y)$ je dána funkcí $f(x,y)$. Celkovou hmotnost můžeme odhadnout
takto: 

* Myšlenkově rozdělíme drát na malé kousíčky a každém z nich
odhadneme lineární hustotu konstantou. Můžeme například použít
minimální hodnotu hustoty v tomto kousíčku. 
* Vynásobením délkou každého
kousíčku obdržíme jeho hmotnost a sečtením přes všechny kousky
dostaneme dolní odhad pro hmotnost drátu. Tento odhad bude tím
přesnější, čím jemnější dělení použijeme. 
* Zjemňováním dělení se tyto odhady zpřesňují. 

V limitním procesu, kdy se délka všech kousíčků blíží k nule,
dostáváme objekt, který se nazývá *křivkový integrál prvního druhu*,
označuje $$ \int_C f\;\mathrm{d} s $$ a fyzikálně vyjadřuje hmotnost
drátu z výše uvažované úlohy.  Pokud počáteční a koncový bod křivky
$C$ splývají, píšeme též $$ \oint_C f\;\mathrm{d} s $$ a integrál
nazýváme *integrálem po uzavřené křivce*.

\iffalse

![Křivkový integrál prvního druhu. Výška plochy je určena zadanou skalární funkcí.](krivkovy_integral_prvniho_druhu_1.png)


<a href="animation.gif" rel="facebox" alt="Nahrava se ...">Animace</a>

\fi

</div>

## Převod na Riemannův integrál (rovinná křivka)

<div class="sloupce">

Mějme parametrické rovnice křivky $C$ ve vektorovém tvaru
$$\vec r(t)=\varphi(t) \vec i + \psi(t)\vec j,$$
kde $t\in[\alpha,\beta]$.
Derivováním křivky dostaneme
$$\frac{\mathrm{d} \vec r(t)}{\mathrm{d}t}=\varphi'(t) \vec i + \psi'(t)\vec j$$
a výpočtem délky vektoru (a formálním vynásobením výrazem $\mathrm{d}t$) dále
$$\mathrm{d}s=|\mathrm{d}\vec r(t)|=\sqrt{(\varphi'(t))^2 + (\psi'(t))^2}\mathrm{d}t.$$
Tím se křivkový integrál prvního druhu funkce $f(x,y)$ po křivce $C$
transformuje na Riemannův integrál
$$
\int_C f\;\mathrm{d} s=\int_\alpha^\beta f(\varphi(t),\psi(t))\sqrt{\varphi'^2(t)+\psi'^2(t)}\;\mathrm{d} t.
$$


\iffalse
\def\maxfactor{0.4}

![Aproximace délky oblouku křivky pomocí funkcí z parametrického vyjádření křivky](delkovy_element.png)

\def\maxfactor{0.6}
\fi

</div>


## Převod na Riemannův integrál (prostorová  křivka)

Podobně jako v rovině převádíme na Riemannův integrál i křivkový integrál prvního druhu po prostorové křivce 
$$
  C:\quad \varphi(t)\vec i + \psi(t)\vec j + \xi(t) \vec k, \quad t\in[\alpha,\beta].
$$
Délkový element je
$$
\mathrm{d}s=\sqrt{\varphi'^2(t)+\psi'^2(t)+\xi'^2(t)}\mathrm{dt}
$$
a integrál má tvar
$$
\int_C f\;\mathrm{d} s=\int_\alpha^\beta f(\varphi(t),\psi(t),\xi(t))\sqrt{\varphi'^2(t)+\psi'^2(t)+\xi^2(t)}\;\mathrm{d} t.
$$


## Aplikace křivkového integrálu prvního druhu

<style>
table, th, td {
   border: 2px solid green;
} 
table {width:97%;}
td {padding:10px}
tr td:first-child {color:green; background: #E9E9E9;}
table {
    border-collapse: collapse;
}
</style>

<style>
table, th, td {
   border: 2px solid green;
} 
table {width:97%;}
td {padding:10px}
tr td:first-child {color:green; background: #E9E9E9;}
table {
    border-collapse: collapse;
}

th {
    background-color: green;
    color: white;
    border-color: gray;
}

th {text-align: center;}
</style>


|Funkce $f(x,y)$        |Integrál $\int_C f\;\mathrm{d}s$                                                                         |
|----------------|-----------------------------------------|
|$1$ | délka křivky $C$|
|lineární hustota $\tau(x,y)$ | hmotnost $m_C$ křivky $C$|
|$\frac {1}{m_C}[x\tau(x,y),y\tau(xy)]$| souřadnice těžiště křivky $C$ |
|$x^2\tau(x,y)$| moment setrvačnosti křivky $C$ vzhledem k  ose $y$|
|$y^2\tau(x,y)$| moment setrvačnosti křivky $C$ vzhledem k  ose $x$|
|$\rho^2(x,y)\tau(x,y)$| moment setrvačnosti křivky $C$ vzhledem k obecné ose, kde $\rho(x,y)$ je vzdálenost bodu $[x,y]$ od osy otáčení.|



## Vlastnosti křivkového integrálu prvního druhu

* Křivkový integrál prvního druhu nezávisí na konkrétní parametrizaci
  křivky $C$. Pro různé parametrizace stejné křivky má integrál
  stejnou hodnotu.
* Křivkový integrál prvního druhu je lineární vzhledem k funkci a aditivní vzhledem k oboru integrace. Přesněji, pro funkce $f$ a $g$ a konstantu $k$ platí následující.
$$
\begin{aligned}
\int_C f+g\;\mathrm{d}s & = \int_C f\;\mathrm{d}s + \int_C g\;\mathrm{d}s \\
\int_C kf\;\mathrm{d}s & = k\int_C f\;\mathrm{d}s\\
\end{aligned}
$$
Je-li křivka $C$ rozdělena na dvě disjunktní (až na koncové body) křivky $C_1$ a $C_2$, platí
$$
\int_{C} f\;\mathrm{d}s = \int_{C_1} f\;\mathrm{d}s + \int_{C_2} f\;\mathrm{d}s .
$$


# Křivkový integrál druhého druhu

<div class="sloupce">

Pokud působíme na těleso silou $F$ a přemísťujeme toto těleso ve směru
působící síly po dráze délky $s$,
[konáme práci](http://cs.wikipedia.org/wiki/Mechanická\_práce)
$W=Fs$. Pokud přemísťování neprobíhá ve směru působící síly a má-li
síla směr $\vec F$ a posunutí $\vec s$, je práce rovna skalárnímu
součinu $\vec F\cdot\vec s$.

Předpokládejme, že na těleso působí (obecně nekonstantní) síla $\vec
F$ a těleso se pohybuje podél křivky $C$ určené polohovým vektorem
$\vec r(t)$. Pro výpočet práce můžeme použít stejný trik jako u
křivkového integrálu prvního druhu. Rozdělíme dráhu na malé kousíčky a
v rámci těchto kousíčků považujeme $\vec F$ i $\Delta \vec r$ za
konstantu. Tato aproximace bude tím přesnější, čím jemnější dělení
použijeme.

V limitě dostáváme veličinu, která se nazývá *křivkový integrál
druhého druhu* funkce $\vec F$ po křivce $C$ a zapisujeme $$
\int_C\vec F\;\mathrm{d}\vec r .$$ Je-li $$ \vec F(x,y)=P(x,y)\vec
i+Q(x,y)\vec j, $$ zapisujeme někdy křivkový integrál
 ve složkách $$ \int_C P(x,y)\mathrm{d}
x+Q(x,y)\mathrm{d} y.  $$

Protože při pohybu tělesa po křivce jedním směrem se práce koná a při
pohybu opačným směrem spotřebovává, je nutné, aby křivka figurující v
křivkovém integrálu druhého druhu byla orientovaná
- tj. abychom prohlásili, který bod je *počáteční* a který
*koncový*. Vždy budeme předpokládat, že křivka je *orientovaná v
souladu se svým parametrickým vyjádřením*, tj. že počáteční bod křivky
 odpovídá hodnotě parametru $t=\alpha$ a koncový bod
odpovídá hodnotě parametru $t=\beta$.

\iffalse
![Křivkový integrál druhého druhu. Výška plochy je v každém bodě
 křivky určena skalárním součinem tečného vektoru jednotkové délky a
 vektorem zadaného vektorového
 pole.](krivkovy_integral_druheho_druhu_1.png)
\fi

</div>


# Převod na Riemannův integrál

<div class="sloupce">


Známe-li parametrické rovnice
$$\vec r = \varphi(t)\vec i + \psi(t) \vec j,\quad t\in[\alpha,\beta],$$
křivky $C$, je možno křivkový integrál
druhého druhu funkce
$$\vec F(x,y)=P(x,y)\vec i + Q(x,y)\vec j$$
po křivce $C$ zapsat
následovně 
$$
\begin{aligned}
\int_C\vec F\;\mathrm{d}\vec r&=
\int_\alpha^\beta\Bigl[ P(\varphi(t),\psi(t))\varphi'(t)\\ &\qquad +Q(\varphi(t),\psi(t))\psi'(t)\Bigr]\;\mathrm{d}t
\end{aligned}
$$ 


\def\maxfactor{0.4}
\iffalse

![Aproximace posunutí pomocí funkcí z parametrického vyjádření křivky](element_posunuti.png)

\fi
\def\maxfactor{0.6}

</div>

# Vlastnosti křivkového integrálu druhého druhu


\iffalse

<div class='obtekat'>

![Narozdíl od prvního druhu, u křivkového integrálu druhého druhu záleží na orientaci křivky.  Zdroj: pixabay.com](smer.jpg)

</div>

\fi

* Křivkový integrál druhého druhu nezávisí na konkrétní parametrizaci
  křivky $C$. Pro různé parametrizace stejné křivky má integrál
  stejnou hodnotu.
* Změnou orientace křivky křivkový integrál druhého druhu mění znaménko. 
* Křivkový integrál druhého druhu je lineární vzhledem k funkci a
  aditivní vzhledem k oboru integrace. Přesněji, pro funkce $\vec F$ a $\vec G$
  a konstantu $k$ platí následující.
$$
\begin{aligned}
\int_C \vec F+\vec G\;\mathrm{d}\vec {r} & = \int_C \vec F\;\mathrm{d}\vec {r} + \int_C \vec {G}\;\mathrm{d}\vec{r} \\
\int_C k\vec {F}\;\mathrm{d}\vec{r} & = k\int_C \vec{F}\;\mathrm{d}\vec{r}\\
\end{aligned}
$$
Je-li křivka $C$ rozdělena na dvě disjunktní (až na koncové body) křivky $C_1$ a $C_2$, platí
$$
\int_{C} \vec F\;\mathrm{d}\vec{r} = \int_{C_1} \vec F\;\mathrm{d}\vec{r} + \int_{C_2} \vec F\;\mathrm{d}\vec{r} .
$$
Tato vlastnost je stejná jako u křivkového integrálu prvního druhu.



# Aplikace křivkového integrálu druhého druhu

<div class="sloupce">

* Integrál
  $$
  \int_C\vec F\;\mathrm{d}\vec r
  $$
  vyjadřuje **práci** kterou vykoná síla $\vec F$ při přemístění tělesa podél orientované křivky $C$.
* Je-li křivka $C$ uzavřená, píšeme
  $$
  \oint_C\vec F\;\mathrm{d}\vec r.
  $$
  Fyzikálně se jedná o **práci** kterou vykoná síla $\vec F$ při přemístění
  tělesa po uzavřené orientované křivce. Tato práce se též nazývá *cirkulace
  vektorového pole po orientované křivce $C$*. Pokud je možno v poli zavést
  potenciální energii a pokud tedy práce závisí jenom na počáteční a
  koncové poloze, musí tato práce být nulová. To je důsledkem věty
  kterou si uvedeme později.
* Při odvození křivkového integrálu druhého druhu jako vykonané práce hraje roli vlastně jenom ta
  složka silového pole, která při posunu ve směru křivky koná práci, tj. složka, která je tečná ke křivce. Pokud použijeme naopak
  normálovou komponentu, dostaneme veličinu vyjadřující **tok
  vektorového pole orientovanou křivkou $C$**. Výsledný vzorec vyjadřující tok vektorového pole $\vec F(x,y)=P(x,y)\vec
i+Q(x,y)\vec j,$
  je
  $$
  \int_{C}-Q(x,y)\mathrm{d}x+P(x,y)\mathrm{d}y.
  $$
* Je-li množina $\Omega$ "dostatečně pěkná" (např. souvislá, bez děr, s počástech hladkou hranicí $\partial \Omega$ která se nikde neprotíná, detaily uvedeme později u Greenovy věty), potom každý z\ integrálů
  $$\oint_{\partial\Omega}x\mathrm{d}y\qquad\text{a}\qquad\oint_{\partial\Omega}y\mathrm{d}x$$
  udává (až na případné znaménko) obsah množiny $\Omega$. Na tomto principu fungují planimetry.

\iffalse

  <div class="sloupce3">
  ![](planimetr_1.jpg)       
  ![](planimetr_2.jpg)
  ![](planimetr_3.jpg)
  </div>

\fi

</div>


\iffalse

# Vodní potenciál

<div class='obtekat'>

![Nejvýkonnější klimatizační jednotka. Funguje na principu odpařování
 vody. Proudění vody je popsáno vodním potenciálem.  Zdroj: pixabay.com](strom.jpg)

</div>

Ve fyzice se většinou s křivkovým integrálem druhého druhu setkáváme
při výpočtu práce silového pole, nebo ekvivalentně (pokud uvažujeme
práci vztaženou na jednotkové množství) při výpočtu potenciální
energie.

Ve fyziologii rostlin pracujeme při popisu hospodaření s vodou s
veličinou podobnou potenciální energii, s [vodním
potenciálem](https://en.wikipedia.org/wiki/Water_potential)
$\psi$. Jedná se o veličinu charakterizující tendenci vody přemisťovat
se z jednoho místa na druhé. Je definována jako práce, nutná pro
přemístění (infinitezimálně) malého množství z referenční hladiny
nulového potenciálu do daného místa a daných podmínek. Tato práce je
ještě přepočtena na jednotkové množství vody. Protože na pohyb vody má
vliv mnoho faktorů (gradient teploty, gradient tlaku, kapilarita,
rozdíl nadmořských výšek, osmóza, koncentrace solí), je tato veličina
poměrně těžce kvantifikovatelná. Nicméně jedná se o druh potenciální
energie a formálně je vyjádřena křivkovým integrálem. Můžeme s ní
pracovat tedy analogicky, jako pracujeme s potenciální energií v
homogenním tíhovém poli. Například příspěvky různé povahy můžeme
reprezentovat pomocí ekvivalentního výškového rozdílu. Tím je,
například v pedologii, definována piezometrická hladina. Velmi
užitečná veličina usnadňující pochopení proudění vody, protože
použitím této veličiny se podněty různého původu vyajdřují jako
ekvivalentní výškový rozdíl.


# Filtrační koeficient půdy a čerpací zkouška

<div class='obtekat'>

![Voda v půdě. Nesmí jí být moc, ale když jí je málo, je to teprve problém.  Zdroj: pixabay.com](puda.jpg)

</div>

Proudění vody v půdě je popsáno Darcyho zákonem, kdy rychlost proudění
vody je úměrná tlakovému gradientu (nebo obecněji gradientu vodního
potenciálu). Tato závislost se nazývá Darcyho zákon a koeficient
úměrnosti se nazývá filtrační koeficient.

Pro pochopení toho, jak voda proudí půdou v oblasti našeho zájmu, je
znalost filtračního koeficientu zásadní. Přímo v terénu je možné tento
koeficient určit pomocí čerpací zkoušky. V daném místě je
vyvrtána studna až po nepropustnou horninu a z této studny se čerpá voda. Tím
se stahuje voda z okolní půdy. Pokles hladiny v okolí hlavního vrtu
se sleduje v menších vrtech.

Pokud si v okolí studny myslíme kružnici, můžeme celou situaci
promítnout na hladinu terénu a jedná se vlastně o dvourozměrnou úlohu
a tok uzavřenou křivkou. Navíc se jedná o jednoduchý případ, kdy
vektorové pole rychlosti je v každém bodě křivky kolmé ke křivce a má
v každém bodě stejnou velikost. Proto se křivkový integrál zjednoduší
na součin intenzity proudění a délky křivky. Toto je však velké
zjednodušení a máme-li ambice dosáhnout přesnější popis, musíme
pracovat s tím, že konstanta v Darcyho zákoně je tenzorového
charakteru. (Voda může proudit jiným směrem, než kterým ji tlačí
gradient vodního potenciálu. Rozhodují i fyzikální vlastnosti
prostředí a anizotropie, tj. odlišné vlastnosti v jiných směrech.)
Potom již tok určujeme křivkovým integrálem nebo jeho vícerozměrným zobecněním, plošným integrálem.

\fi



# Shrnutí: vlastnosti křivkových integrálů


* Oba integrály jsou **aditivní vzhledem k oboru integrace**. Pokud je nutné při parametrizaci křivku rozdělit na konečný počet navzájem disjunktních částí, můžeme vypočítat integrál na každé části   samostatně a výsledky sečíst.  
* Křivkový integrál prvního ani druhého druhu **nezávisí na konkrétní  parametrizaci křivky**.
* Křivkový integrál prvního druhu **nezávisí na orientaci** křivky.
* Křivkový integrál druhého druhu **při změně orientace křivky mění znaménko**.

# Steinerova věta

<div class="sloupce">

Nechť je dána křivka $C$ s lineární hustotou $\tau(x,y)$.
Nechť křivka $C$ splňuje $\int_C x \tau(x,y)\;\mathrm{d}s=0$, tj. nechť
osa $y$ prochází těžištěm křivky $C$. Určete moment setrvačnosti
křivky vhledem k ose $o$ rovnoběžné s $y$ ve vzdálenosti $d$ od osy $y$.

*Řešení*
Podle toho zda osa $o$ je nalevo nebo napravo od osy $y$ dostáváme jednu z následujících variant.
$$\begin{aligned}
J_o&=\int_C(x\pm d)^2\tau \;\mathrm{d}s\\
&=\int_C(x^2\pm 2xd+d^2)\tau \;\mathrm{d}s\\
&=\int_C x^2\tau \;\mathrm{d}s \pm 2d\int_C x\tau \;\mathrm{d}s + d^2 \int_C \tau \;\mathrm{d}s.
\end{aligned}
$$
Na pravé straně vidíme, že prvním členem je moment otáčení vzhledem k ose $y$
$$J_{yT}=\int_C x^2\tau \;\mathrm{d}s$$ a ve třetím členu je obsažena hmotnost křivky
$$m=\int_C \tau \;\mathrm{d}s.$$
Dále ze zadání vidíme, že prostřední člen je roven nule.
V označení výše náš vztah dostává tvar
$$J_o=J_{yT}+m d^2.$$
Tento vztah se nazývá Steinerova věta. Ukazuje, že moment setrvačnosti
je nejmenší vzhledem k ose otáční procházející těžišťěm (člen $m
d^2$ je vždy nezáporný) a umožňuje přepočet momentu setrvačnosti pro
rovnoběžné osy.

</div>

# Závěrečné informace

## Parametrizace úsečky

* Hledáme parametrické rovnice orientované úsečky $AB$, kde je dán počáteční bod $A=[x_A,y_A]$ a koncový bod $B=[x_B,y_B]$.
* Leží-li bod $X$ na úsečce $AB$, potom vektor $\vec {AX}$ má stejný směr (včetně orientace) jako vektor $\vec {AB}$ a nejvýše stejnou délku.
* Platí tedy $\vec {AX}=t\vec {AB}$ pro nějaké $t\in[0,1]$, tj. $X-A=t(B-A)$ a odsud $X=A+t(B-A)$.
* V souřadnicích zapsáno, parametrické rovnice úsečky jsou $$\begin{aligned}x&=x_A+t(x_B-x_A)\\y&=y_A+t(y_B-y_A), \quad t\in[0,1]\end{aligned}$$
* Pro úsečku v prostoru platí totéž, pouze přibývá třetí souřadnice.

\iffalse

## Online výpočet křivkového integrálu

* Křivkový integrál prvního druhu. [numericky pomocí Sage](https://sagecell.sagemath.org/?z=eJxtjsEKgzAQRO-B_EPAg4nNQbznS0otQWNZNNGuUUy-vkaxUOhclsfMsLNq5LnPBSVZlrGoW-2AdYvrG0NJxzcZZBRqqytKzgiOq4PGsAlH1iOsfaBk416oZpz3Q0lIMIM7ICYor6418SxOGrU1HinxFpz0Vm-qlFUxQYoe4T9KjlusQWj08ATnzQv1wNk-U6UJMqj0XEaV3gpWsPmNnrfQ7YlkeFFXtwPDL8YLhWS7vqPEvXx8AHukUPY=&lang=sage)
* Křivkový integrál druhého druhu, [numericky pomocí Sage](https://sagecell.sagemath.org/?z=eJxtkMFuwyAQRO-W_A8r5RBIaepGOVXi6p-o2ogaUiEbcDGxgK8v2CFqoywXntjRzDAzi7Zui-tqs9lAZJxpCeeL7jtRV61HngQSMX0OiUIhnyAWaOoqnyy3ZtayEzBaA72Vc59UHjlMD7vOTOlSVyHjJPUCMUNT1ErEVToyy5Rwtq6ckpo4xTxtyOvLcTfKm9mDWV70RQkrOzacpHbi27IBwRl5mnOQQLM_iTQ7Y9jB9GMd4vKcNvKDw5-HpwXDf4wFMYE0t1z4vfnIttxMLAotT2ttqtiIYGDqizMY38biD9cAcE1AALWetIFAG3H6kBSXS6HdvX6_hMjCNefaYumAs_2D0rPonLHoLhjec-NO6ZP5pXNlp7jiP-WgtPsFHlShKA==&lang=sage)


\fi

<style>
.sloupce4{-moz-column-count:4; /* Firefox */
-webkit-column-count:4; /* Safari and Chrome */
column-count:4;}
.sloupce6{-moz-column-count:6; /* Firefox */
-webkit-column-count:6; /* Safari and Chrome */
column-count:6;}
.sloupce5{-moz-column-count:5; /* Firefox */
-webkit-column-count:5; /* Safari and Chrome */
column-count:5;}
.sloupce3{-moz-column-count:3; /* Firefox */
-webkit-column-count:3; /* Safari and Chrome */
column-count:3;}
.sloupce4 ul li {display:inline-block; max-width:100%;}
</style>


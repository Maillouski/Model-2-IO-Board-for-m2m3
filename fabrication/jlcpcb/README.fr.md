# Commander chez JLCPCB (carte + assemblage des CMS)

[English](README.md) | **Français**

JLCPCB fabrique la carte et soude 124 composants CMS. Vous soudez vous-même les pièces traversantes.

| Fichier | Où le charger |
|---|---|
| [`../m2-io-emulator-board-gerbers.zip`](../m2-io-emulator-board-gerbers.zip) | « Add gerber file » |
| [`m2-io-emulator-board-BOM-jlcpcb.csv`](m2-io-emulator-board-BOM-jlcpcb.csv) | PCB Assembly → « Add BOM File » |
| [`m2-io-emulator-board-CPL-jlcpcb.csv`](m2-io-emulator-board-CPL-jlcpcb.csv) | PCB Assembly → « Add CPL File » |

> Lisez d'abord les [points ouverts](../../README.fr.md#points-ouverts).

## Options de commande

- **PCB :** 2 couches, 180 × 190 mm (la taille est lue dans les Gerbers), 1,6 mm. La couleur et la finition sont au choix. Le
  bloc HDMI utilise des pistes de 0,15 mm (0,2 mm minimum ailleurs), 0,2 mm d'isolement, et des vias jusqu'à 0,45 / 0,20 mm (0,6 / 0,3 mm ailleurs) ;
  les trous de composants font 0,8 mm au minimum. 27 vias font
  0,45 / 0,20 mm, pile à la taille que JLCPCB surtaxe : à confirmer au devis.
  design utilise des pistes de 0,2 mm au minimum avec 0,2 mm d'isolement, des vias de 0,7 / 0,3 mm et 0,8 / 0,4 mm et des trous
  de composants de 0,8 mm au minimum : tout est dans les règles standard de JLCPCB.
  - **Via-in-pad :** la pastille centrale de U9 porte 16 vias. Sous Via Covering, choisissez **Epoxy Filled & Capped** (pas « Plugged » :
    le bouchage à l'encre ne couvre pas les trous situés dans une pastille) pour que la brasure ne fuie pas par les trous. Le
    2026-10-16, l'option était proposée en 2 couches et ajoutait environ 62 $ US pour 5 cartes. Sans cette option, mettez moins de pâte sur cette pastille (U9 est
    posé par JLCPCB : demandez-le dans les notes de commande).
- **PCB Assembly :** **dessus** seulement, 2 cartes ou plus. Economic accepte de 2 à 50 cartes et ne demande pas de repères
  optiques. La pastille CMS la plus proche du bord est à 7,85 mm (J15, la prise HDMI, posée au bord) ; toutes les autres sont à
  10 mm ou plus. JLCPCB pourrait quand même demander des bords de manutention à cause de J15.
- **Avant de payer,** vérifiez l'aperçu de placement :
  - **SOIC et TSSOP (U2, U3, U6, U7, U8) :** le point de la broche 1 de chaque pièce doit tomber sur la broche 1 de son empreinte.
    Le CPL les tourne de −90° par rapport à KiCad, pour suivre les empreintes EasyEDA dont JLCPCB se sert pour placer.
  - **U10 (SOT-223) :** le CPL le tourne de 180° par rapport à KiCad : sa languette est la broche 4 dans l'empreinte EasyEDA et la broche 2 dans celle de KiCad.
    La languette doit être du même côté que la grande pastille dessinée sur la carte.
  - **J15 (HDMI) :** le CPL déplace son centre de 2,05 mm vers ses broches (loin du bord de la carte), car l'empreinte EasyEDA de C427307 a son
    origine à cet endroit ; pastilles et orientation sont par ailleurs celles de KiCad. L'ouverture de la prise doit faire face
    au bord de la carte.
  - **Résistances, condensateurs, FB1 :** ils ne sont pas polarisés et n'ont besoin d'aucune correction de rotation.

## Pièces posées par JLCPCB

Numéros, types, stocks et prix vérifiés en direct sur jlcpcb.com le 2026-10-16, en dollars US la pièce à la plus petite quantité.
Les quatre lignes ajoutées par la V5 (L1, R69, U9, U10) ont été vérifiées le 2026-11-14 (stock seulement).

| LCSC | Pièce | Repères | Qté / carte | Type | Stock | Prix |
|---|---|---|---:|---|---:|---:|
| C49678 | YAGEO CC0805KRX7R9BB104, 100 nF 50 V X7R | C1-C16, C18, C20-C22, C24, C33, C43, C44, C46 | 25 | Basic | 21 M | 0,020 |
| C15850 | Samsung CL21A106KAYNNNE, 10 µF 25 V X5R | C19, C23, C25, C32, C41, C42, C45, C49, C51-C53 | 11 | Basic | 6,6 M | 0,044 |
| C1710 | Samsung CL21B103KBANNNC, 10 nF 50 V X7R | C39, C40 | 2 | Basic | 1,6 M | 0,012 |
| C45783 | Samsung CL21A226MAQNNNE, 22 µF 25 V X5R | C47, C48 | 2 | Basic | 3,8 M | 0,193 |
| C1017 | Sunlord GZ2012D601TF, 600 Ω à 100 MHz | FB1 | 1 | Basic | 679 k | 0,020 |
| C427307 | Amphenol 10029449-111RLF, HDMI type A | J15 | 1 | Extended | 1 514 | 0,62 |
| C503307 | Bourns SRN4018-100M, inductance de puissance 10 µH | L1 | 1 | Extended | 5 217 | — |
| C17673 | UNI-ROYAL 0805W8F4701T5E, 4,7 kΩ 1 % | R1-R13 | 13 | Basic | 4,2 M | 0,005 |
| C17513 | UNI-ROYAL 0805W8F1001T5E, 1 kΩ 1 % | R14-R37, R46 | 25 | Basic | 44 M | 0,004 |
| C17414 | UNI-ROYAL 0805W8F1002T5E, 10 kΩ 1 % | R38-R45, R61-R65, R68, R70 | 15 | Basic | 57 M | 0,003 |
| C17710 | UNI-ROYAL 0805W8F4700T5E, 470 Ω 1 % | R47, R71, R72 | 3 | Basic | 2,3 M | 0,005 |
| C141697 | YAGEO RC0805FR-0775RL, 75 Ω 1 % | R48-R50, R75-R77 | 6 | Extended | 123 k | 0,008 |
| C228933 | YAGEO AC0805FR-07604RL, 604 Ω 1 % | R51-R53 | 3 | Extended | 4 446 | 0,007 |
| C17540 | UNI-ROYAL 0805W8F2000T5E, 200 Ω 1 % | R54-R56 | 3 | Basic | 1,2 M | 0,007 |
| C17634 | UNI-ROYAL 0805W8F330JT5E, 33 Ω 1 % | R57-R59 | 3 | Basic | 1,4 M | 0,005 |
| C17520 | UNI-ROYAL 0805W8F2201T5E, 2,2 kΩ 1 % | R66, R67 | 2 | Basic | 3,7 M | 0,005 |
| C28636 | UNI-ROYAL 0805W8F5600T5E, 560 Ω 1 % | R69 | 1 | Basic | 414 k | — |
| C6005 | Nexperia 74HCT86D,653, SOIC-14 | U2 | 1 | Extended | 911 | 0,36 |
| C2652730 | Texas Instruments OPA3355EA/2K5, TSSOP-14 | U3 | 1 | Extended | **11** | 6,02 |
| C6203 | Microchip AT24C02C-SSHM-T, SOIC-8 | U6 | 1 | Extended | 113 k | 0,21 |
| C2652470 | Texas Instruments TS5V330CPWR, TSSOP-16 | U7 | 1 | Extended | 6 599 | 0,42 |
| C6771 | Texas Instruments SN74HCT157DR, SOIC-16 | U8 | 1 | Extended | 155 | 0,41 |
| C2874140 | Macrosilicon MS9292, QFN-48 6 × 6 mm | U9 | 1 | Extended | **91** | — |
| C26537 | onsemi NCP1117ST33T3G, régulateur 3,3 V, SOT-223 | U10 | 1 | Extended | 89 k | — |

- **Le stock de U9 est bas aussi :** 91 pièces au 2026-11-14 ; vérifiez-le avant de commander plusieurs cartes.
- **Stock de U3 très faible :** il n'y en avait que 11. S'il s'épuise, achetez-le d'avance dans votre bibliothèque de pièces
  JLCPCB, ou attendez un réassort. U3 n'a pas de remplaçant direct.
- **Pièces Extended :** il y en a 11, et JLCPCB facture des frais de mise en place pour chaque pièce Extended. Les pièces Basic
  n'en ont pas.
- **Condensateurs de 10 µF :** la BOM JLCPCB utilise un X5R 25 V, une pièce Basic, au lieu du X7R 16 V de la BOM DigiKey ; le
  X5R est garanti jusqu'à 85 °C. Pour garder du X7R, prenez plutôt C95841 (Samsung CL21B106KOQNNNE, Extended, 268 k en stock).
- **U2 :** si C6005 s'épuise, C527451 le remplace directement (TI CD74HCT86M96, même boîtier SOIC-14, Extended, 10 826 en
  stock).
- **Non posés par JLCPCB :** les pièces DNP C50, R60, R73 et R74 (voir [`../../bom/BOM.fr.md`](../../bom/BOM.fr.md#non-posés-dnp)), et TP1-TP4.
- **Valeurs :** toutes les autres valeurs et tous les boîtiers correspondent à [`../../bom/BOM.fr.md`](../../bom/BOM.fr.md)
  (FB1 : la BOM DigiKey prend un équivalent Murata ; C47, C48 : Samsung ici, Murata dans la BOM DigiKey, même valeur). La BOM, le CPL et le fichier de
  placement de KiCad donnent les mêmes 124 repères CMS ; positions identiques sauf J15 (voir plus haut).

## Pièces à souder vous-même

- **Pièces traversantes :** C17, D1, J1-J14, J16, J17, J18, JP1-JP10, U1, SW1 et SW2, plus les cavaliers SH1-SH10. TP1-TP4 ne sont pas posés. Commandez-les
  avec la [BOM DigiKey](../../bom/BOM-digikey.csv), sans les lignes CMS (J18 n'y est pas : LCSC C160360).

JLCPCB peut aussi souder les pièces traversantes, contre supplément. Pour J16, LCSC a la Lian Xin XDJK-0271-1650 (C7527522),
qui va dans la même empreinte. LCSC a en stock les embases JST NH de 10 et 12 broches
(C160365 : 3 292 pièces ; C160367 : 133 pièces, au 2026-10-16) et celle de 4 broches (J18, C160360 : 24 302 pièces, au 2026-11-14).

# Liste des pièces (BOM) — M2 IO Emulator Board

[English](BOM.md) | **Français**

Quantités **par carte**. 175 repères, vérifiés un par un contre le schéma (V5.1, 2026-11-15) : 164 dans le fichier DigiKey, U9 et J18
de chez LCSC, J19 pas encore approvisionnée, et 8 non posés (DNP).

**Import DigiKey :** [`BOM-digikey.csv`](BOM-digikey.csv) (Quantity, Digi-Key Part Number, Manufacturer Part Number,
Manufacturer, Customer Reference). Le charger dans le gestionnaire de BOM de DigiKey ou dans une myList, puis multiplier par le
nombre de cartes.

**Assemblage JLCPCB :** pour faire souder les CMS par JLCPCB, voir
[`../fabrication/jlcpcb/`](../fabrication/jlcpcb/README.fr.md) (numéros LCSC, fichiers BOM et CPL).

Chaque numéro DigiKey ci-dessous a été vérifié en direct sur digikey.ca le 2026-10-16 (U10, L1, R69 et J17 : 2026-10-26), en dollars canadiens, bande coupée, à la
quantité 1, sans taxes ni livraison. Prix et stocks changent : revérifier avant de commander.

## Pièces sur la carte

| Qté | Repères | Valeur | Pièce du fabricant | DigiKey | Remarque |
|---:|---|---|---|---|---|
| 25 | C1-C16, C18, C20-C22, C24, C33, C43, C44, C46 | 100 nF 50 V X7R 0805 | YAGEO CC0805KRX7R9BB104 | 311-1140-1-ND | |
| 11 | C19, C23, C25, C32, C41, C42, C45, C49, C51-C53 | 10 µF 25 V X5R 0805 | Samsung CL21A106KAYNNNE | 1276-2891-1-ND | même pièce que l'assemblage JLCPCB (C15850) ; tout 10 µF ≥ 16 V X5R/X7R 0805 convient |
| 2 | C39, C40 | 10 nF 50 V X7R 0805 | YAGEO CC0805KRX7R9BB103 | 311-1136-1-ND | filtre audio (V3) |
| 2 | C47, C48 | 22 µF 16 V X5R 0805 | Samsung CL21A226MOCLRNC | 1276-6780-1-ND | moyenne des synchros (synchro composite) ; tout 22 µF ≥ 10 V X5R/X7R 0805 convient |
| 1 | C17 | 100 µF 16 V, Ø 6,3 mm, pas 2,5 mm | Panasonic EEU-FC1C101H | P19632CT-ND | même série FC que l'EEU-FC1C101, en bande ; tout 100 µF ≥ 16 V Ø 6,3 / pas 2,5 convient |
| 1 | D1 | DEL verte 3 mm | Kingbright WP710A10GD | 754-1603-ND | « CAB PWR LED » |
| 1 | FB1 | ferrite 600 Ω, 0805 | Murata BLM21PG601SN1D | 490-BLM21PG601SN1DCT-ND | V3 ; le schéma indique Sunlord GZ2012D601TF (600 Ω à 100 MHz, la pièce JLCPCB), absente chez DigiKey |
| 1 | J1 (CN1) | embase IDC 2 × 25 | 3M N2550-6002-RB | MHC50K-ND | voir « Points ouverts » |
| 1 | J2 (CN2) | embase IDC 2 × 13 | 3M N2526-6002-RB | MHC26K-ND | voir « Points ouverts » |
| 1 | J3 (CN3) | JST NH 10 broches, pas 2,5 mm | JST B10P-SHF-1AA | 455-B10P-SHF-1AA-ND | ⚠️ ni chez DigiKey (minimum 250) ni chez Mouser : acheter chez LCSC (C160365), voir [plus bas](#embases-jst-nh-j3-j4-j5) |
| 2 | J4 (CN5), J5 (CN6) | JST NH 12 broches, pas 2,5 mm | JST B12P-SHF-1AA | 455-B12P-SHF-1AA-ND | ⚠️ ni chez DigiKey (minimum 6 500) ni chez Mouser : acheter chez LCSC (C160367), voir [plus bas](#embases-jst-nh-j3-j4-j5) |
| 5 | J6-J10 | barrette 1 × 8 | Würth 61300811121 | 732-5321-ND | vers l'Arduino Mega |
| 1 | J11 | barrette 1 × 10 | Würth 61301011121 | 732-2670-ND | vers l'Arduino Mega |
| 1 | J12 | barrette 2 × 18 | Würth 61303621121 | 732-5309-ND | vers l'Arduino Mega |
| 1 | J13 | VGA (DE-15 HD) femelle, coudée | Amphenol L77HDE15SD1CH4F | L77HDE15SD1CH4F-ND | entrée VGA 24 kHz |
| 1 | J14 | JST NH 5 broches, pas 2,5 mm | JST B5P-SHF-1AA | 455-B5P-SHF-1AA-ND | VIDEO OUT |
| 1 | J15 | prise HDMI type A, coudée | Amphenol 10029449-001RLF | 609-1010-1-ND | entrée HDMI (V3) ; l'assemblage JLCPCB utilise la 10029449-111RLF (C427307), épuisée chez DigiKey ; la -001RLF est celle pour laquelle l'empreinte KiCad est dessinée |
| 1 | J16 | double prise RCA superposée (rouge / blanche), coudée | Same Sky RCJ-2223 | CP-1435-ND | sortie stéréo (V3) : en haut = gauche, en bas = droite (sur la RCJ-2223, rouge = gauche). Même empreinte : Lian Xin XDJK-0271-1650 (LCSC C7527522), blanche en haut |
| 1 | J17 | entrée AUDIO, JST PH 3 broches, 2,00 mm | JST B3B-PH-K-S | 455-1705-ND | câble droit depuis la sortie ligne de l'hôte (1 gauche, 2 masse, 3 droite) |
| 1 | J18 | AUDIO OUT, JST NH 4 broches, 2,5 mm | JST B4P-SHF-1AA | — | pas vérifié chez DigiKey ; LCSC C160360, voir [plus bas](#embases-jst-nh-j3-j4-j5) ; reprend J17 tout droit vers le préampli de la borne |
| 1 | J19 | prise USB-A, 5 V de la borne seulement (D+ / D− non connectés) | type Molex 67643, selon l'empreinte (référence exacte non confirmée) | — | pas vérifié chez DigiKey ni LCSC ; à souder à la main, absente des fichiers JLCPCB ; pas de fusible |
| 1 | L1 | inductance de puissance 10 µH, 4 × 4 mm | Bourns SRN4018-100M | SRN4018-100MCT-ND | convertisseur abaisseur 1,2 V de U9 (doit être une inductance de puissance) |
| 5 | JP1, JP2-JP4, JP10 | barrette 1 × 3 | Würth 61300311121 | 732-5316-ND | JP1 = alim. drive board, JP2-JP4 = ampli vidéo, JP10 = 5 V de la puce HDMI |
| 5 | JP5-JP9 | barrette 1 × 2 | Würth 61300211121 | 732-5315-ND | JP5-JP7 = terminaison VGA 75 Ω, JP8 = choix d'écran, JP9 = source vidéo |
| 10 | SH1-SH10 | cavalier | TE 382811-8 | A26228-ND | vendu par 10 |
| 13 | R1-R13 | 4,7 kΩ 1 % 0805 | YAGEO RC0805FR-074K7L | 311-4.70KCRCT-ND | rappels des entrées |
| 25 | R14-R37, R46 | 1 kΩ 1 % 0805 | YAGEO RC0805FR-071KL | 311-1.00KCRCT-ND | |
| 15 | R38-R45, R61-R65, R68, R70 | 10 kΩ 1 % 0805 | YAGEO RC0805FR-0710KL | 311-10.0KCRCT-ND | R61 = rappel du choix de source, R62-R65 = tirages à la masse des entrées de synchro, R68 = REXT de U9, R70 = tirage du reset de U9 |
| 3 | R47, R71, R72 | 470 Ω 1 % 0805 | Stackpole RMCF0805FT470R | RMCF0805FT470RCT-ND | R47 = résistance série de la synchro composite, R71, R72 = résistances série de l'audio |
| 6 | R48-R50, R75-R77 | 75 Ω 1 % 0805 | YAGEO RC0805FR-0775RL | 311-75.0CRCT-ND | R48-R50 = terminaison VGA (par JP5-JP7), R75-R77 = sorties du DAC de U9 vers la masse |
| 3 | R51-R53 | 604 Ω 1 % 0805 | YAGEO RC0805FR-07604RL | 311-604CRCT-ND | contre-réaction de l'ampli vidéo |
| 3 | R54-R56 | 200 Ω 1 % 0805 | YAGEO RC0805FR-07200RL | 311-200CRCT-ND | gain de l'ampli vidéo (gain = 4,02) |
| 3 | R57-R59 | 33 Ω 1 % 0805 | YAGEO RC0805FR-0733RL | 311-33.0CRCT-ND | sortie de l'ampli vidéo |
| 2 | R66, R67 | 2,2 kΩ 1 % 0805 | YAGEO RC0805FR-072K2L | 311-2.20KCRCT-ND | moyenne des synchros (avec C47, C48) |
| 1 | R69 | 560 Ω 1 % 0805 | YAGEO RC0805FR-07560RL | 311-560CRCT-ND | DACREF de U9 |
| 2 | SW1, SW2 | bouton tactile 6 × 6 mm | TE 1825910-6 | 450-1650-ND | TEST, SERVICE |
| 1 | U1 | ULN2803A, DIP-18 | STMicroelectronics ULN2803A | 497-2356-5-ND | lampes, compteurs, relais ; soudé directement, sans support |
| 1 | U2 | 74HCT86, SOIC-14 | Nexperia 74HCT86D,653 | 1727-6360-1-ND | synchro composite, négative quelle que soit la polarité de H et V (voir le [README](../README.fr.md#synchro-composite)) |
| 1 | U3 | OPA3355EA, TSSOP-14 | Texas Instruments OPA3355EA/2K5 | 296-29279-1-ND | triple ampli vidéo (R, V, B) |
| 1 | U6 | AT24C02, SOIC-8 | Microchip AT24C02C-SSHM-T | AT24C02C-SSHM-TCT-ND | EEPROM d'EDID sur les lignes DDC du HDMI (adresse 0x50, protection en écriture à la masse), alimentée par le +5 V du HDMI ; arrive vierge |
| 1 | U7 | TS5V330, TSSOP-16 | Texas Instruments TS5V330CPWR | 296-27548-1-ND | choix de source R/V/B (V3) |
| 1 | U8 | 74HCT157, SOIC-16 | Texas Instruments SN74HCT157DR | 296-31835-1-ND | choix de source des synchros H/V (V3) |
| 1 | U9 | MS9292, QFN-48 6 × 6 mm, pas 0,4 mm | Macrosilicon MS9292 | — | convertisseur HDMI → VGA avec DAC audio ; ni chez DigiKey ni chez Mouser, LCSC C2874140, voir [plus bas](#u9-ms9292) |
| 1 | U10 | régulateur 3,3 V, 1 A, SOT-223 | onsemi NCP1117ST33T3G | NCP1117ST33T3GOSCT-ND | 3,3 V de U9 (le MS9292 n'a aucune broche 5 V) |

Éléments propres à la carte, hors BOM : H1-H4 (trous de fixation), LOGO1 (logos Creative Commons), MEGA1 (modèle 3D du Mega).

## Non posés (DNP)

Ces empreintes sont sur la carte mais restent vides. Elles ne sont ni dans le fichier DigiKey ni dans les fichiers JLCPCB.

| Repère | Pièce | Rôle |
|---|---|---|
| C50 | 100 nF 0805 | filtre sur la broche RSTN (15) de U9 ; un ajout, absent du circuit du fabricant |
| R60 | 1 kΩ 0805 | rappel du HPD de la V3 ; HDRXHPD (broche 43) de U9 est une sortie et entrerait en conflit avec le +5 V |
| R73, R74 | 0 Ω 0805 | relieraient les broches DDC de U9 (45, 46) au DDC du HDMI ; U6 reste le seul répondeur EDID |
| TP1-TP4 | points de test Keystone 5002 | laissés vides ; les empreintes restent pour mesurer |

## Hors carte

| Qté | Article | Pièce du fabricant | DigiKey | Remarque |
|---:|---|---|---|---|
| 1 | Arduino Mega 2560 Rev3 | Arduino A000067 | 1050-1018-ND | s'enfiche sur J6-J12 (inclus dans le CSV) |

Pas d'adaptateur HDMI → VGA externe : U9 fait la conversion sur la carte.

## U9 (MS9292)

DigiKey et Mouser ne listent pas le MS9292. LCSC le vend sous la référence **C2874140** (pièce « Extended » de JLCPCB, environ 1,20 USD ; 91 en stock le
2026-11-14, 101 le 2026-10-26) : JLCPCB peut donc le souder pour vous, il est dans la BOM et le CPL JLCPCB.

U9 est un QFN à pastille centrale, au pas de 0,4 mm. Sa pastille centrale a 9 vias vers le plan de masse ; demander à JLCPCB des vias « Epoxy Filled &
Capped » (pas « Plugged ») à la commande du PCB, ou réduire la pâte sur cette pastille, sinon la brasure peut fuir par les trous.

## Coût

Pas recalculé pour la V5. L'estimation de la V3.2 était d'environ 77 $ CA par carte en pièces DigiKey à la quantité 1 (2026-10-16), sans l'Arduino
Mega. La V5 change la liste (U4 sorti ; U9, U10, L1, J17, J18 et quelques résistances entrés ; la V5.1 ajoute J19) : revérifier le fichier chez DigiKey.

## Embases JST NH (J3, J4, J5)

DigiKey ne stocke pas les B10P-SHF-1AA et B12P-SHF-1AA (minimum 250 et 6 500 pièces). Mouser ne les a pas.
LCSC les a (C160365 et C160367), comme d'autres distributeurs JST. Le B5P-SHF-1AA (J14) est en stock chez DigiKey.
J18 (B4P-SHF-1AA) est chez LCSC sous la référence C160360 (24 302 en stock le 2026-11-14).

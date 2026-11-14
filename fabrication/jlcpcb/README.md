# Ordering from JLCPCB (board + SMD assembly)

**English** | [Français](README.fr.md)

JLCPCB makes the board and solders 124 SMD parts. You solder the through-hole parts yourself.

| File | Upload it at |
|---|---|
| [`../m2-io-emulator-board-gerbers.zip`](../m2-io-emulator-board-gerbers.zip) | "Add gerber file" |
| [`m2-io-emulator-board-BOM-jlcpcb.csv`](m2-io-emulator-board-BOM-jlcpcb.csv) | PCB Assembly → "Add BOM File" |
| [`m2-io-emulator-board-CPL-jlcpcb.csv`](m2-io-emulator-board-CPL-jlcpcb.csv) | PCB Assembly → "Add CPL File" |

> Read the [open points](../../README.md#open-points) first.

## Order settings

- **PCB:** 2 layers, 180 × 190 mm (the size is read from the Gerbers), 1.6 mm. Colour and surface finish are your choice. The
  HDMI block uses 0.15 mm tracks (0.2 mm minimum elsewhere), 0.2 mm clearance, and vias down to 0.45 / 0.20 mm (0.6 / 0.3 mm elsewhere);
  component holes are 0.8 mm at the smallest. 27 vias are
  0.45 / 0.20 mm, right at the size JLCPCB surcharges: confirm it on the quote.
  design uses 0.2 mm minimum tracks with 0.2 mm clearance, 0.7 / 0.3 mm and 0.8 / 0.4 mm vias and 0.8 mm minimum component
  holes, all within JLCPCB's standard rules.
  - **Via-in-pad:** the exposed pad of U9 has 9 vias. Under Via Covering, choose **Epoxy Filled & Capped** (not "Plugged":
    ink plugging does not cover holes inside a pad) so solder does not wick through them. On 2026-10-16 it was offered for 2-layer
    boards and added about 62 USD to 5 boards. Without that option, put less paste on that pad (U9 is placed by JLCPCB, so
    ask for it in the order notes).
  SMD pad is 7.85 mm from the board edge (J15, the HDMI jack, which sits on the edge); every other SMD pad is at least 10 mm away.
  JLCPCB may still ask for edge rails because of J15.
- **Before paying,** check the placement preview:
  - **SOIC and TSSOP parts (U2, U3, U6, U7, U8):** the pin-1 dot of each part must sit on pin 1 of its footprint. The CPL rotates
    them by −90° relative to KiCad, to match the EasyEDA footprints JLCPCB places from.
  - **U10 (SOT-223):** the CPL rotates it by 180° relative to KiCad: its tab is pin 4 in the EasyEDA footprint and pin 2 in KiCad's.
    The tab must face the same way as the large pad drawn on the board.
  - **J15 (HDMI):** the CPL moves its centre by 2.05 mm toward its pins (away from the board edge), because the EasyEDA footprint of C427307 has its
    origin there; pads and orientation are otherwise the same as in KiCad. The jack opening must face the board edge.
  - **Resistors, capacitors, FB1:** they are not polarised and need no rotation correction.

## Parts placed by JLCPCB

All numbers, types, stock levels and prices were checked live on jlcpcb.com on 2026-10-16, in USD per piece at the lowest
quantity. The four rows added by V5 (L1, R69, U9, U10) were checked on 2026-11-14 (stock only).

| LCSC | Part | References | Qty / board | Type | Stock | Price |
|---|---|---|---:|---|---:|---:|
| C49678 | YAGEO CC0805KRX7R9BB104, 100 nF 50 V X7R | C1-C16, C18, C20-C22, C24, C33, C43, C44, C46 | 25 | Basic | 21 M | 0.020 |
| C15850 | Samsung CL21A106KAYNNNE, 10 µF 25 V X5R | C19, C23, C25, C32, C41, C42, C45, C49, C51-C53 | 11 | Basic | 6.6 M | 0.044 |
| C1710 | Samsung CL21B103KBANNNC, 10 nF 50 V X7R | C39, C40 | 2 | Basic | 1.6 M | 0.012 |
| C45783 | Samsung CL21A226MAQNNNE, 22 µF 25 V X5R | C47, C48 | 2 | Basic | 3.8 M | 0.193 |
| C1017 | Sunlord GZ2012D601TF, 600 Ω at 100 MHz | FB1 | 1 | Basic | 679 k | 0.020 |
| C427307 | Amphenol 10029449-111RLF, HDMI type A | J15 | 1 | Extended | 1 514 | 0.62 |
| C503307 | Bourns SRN4018-100M, 10 µH power inductor | L1 | 1 | Extended | 5 217 | — |
| C17673 | UNI-ROYAL 0805W8F4701T5E, 4.7 kΩ 1 % | R1-R13 | 13 | Basic | 4.2 M | 0.005 |
| C17513 | UNI-ROYAL 0805W8F1001T5E, 1 kΩ 1 % | R14-R37, R46 | 25 | Basic | 44 M | 0.004 |
| C17414 | UNI-ROYAL 0805W8F1002T5E, 10 kΩ 1 % | R38-R45, R61-R65, R68, R70 | 15 | Basic | 57 M | 0.003 |
| C17710 | UNI-ROYAL 0805W8F4700T5E, 470 Ω 1 % | R47, R71, R72 | 3 | Basic | 2.3 M | 0.005 |
| C141697 | YAGEO RC0805FR-0775RL, 75 Ω 1 % | R48-R50, R75-R77 | 6 | Extended | 123 k | 0.008 |
| C228933 | YAGEO AC0805FR-07604RL, 604 Ω 1 % | R51-R53 | 3 | Extended | 4 446 | 0.007 |
| C17540 | UNI-ROYAL 0805W8F2000T5E, 200 Ω 1 % | R54-R56 | 3 | Basic | 1.2 M | 0.007 |
| C17634 | UNI-ROYAL 0805W8F330JT5E, 33 Ω 1 % | R57-R59 | 3 | Basic | 1.4 M | 0.005 |
| C17520 | UNI-ROYAL 0805W8F2201T5E, 2.2 kΩ 1 % | R66, R67 | 2 | Basic | 3.7 M | 0.005 |
| C28636 | UNI-ROYAL 0805W8F5600T5E, 560 Ω 1 % | R69 | 1 | Basic | 414 k | — |
| C6005 | Nexperia 74HCT86D,653, SOIC-14 | U2 | 1 | Extended | 911 | 0.36 |
| C2652730 | Texas Instruments OPA3355EA/2K5, TSSOP-14 | U3 | 1 | Extended | **11** | 6.02 |
| C6203 | Microchip AT24C02C-SSHM-T, SOIC-8 | U6 | 1 | Extended | 113 k | 0.21 |
| C2652470 | Texas Instruments TS5V330CPWR, TSSOP-16 | U7 | 1 | Extended | 6 599 | 0.42 |
| C6771 | Texas Instruments SN74HCT157DR, SOIC-16 | U8 | 1 | Extended | 155 | 0.41 |
| C2874140 | Macrosilicon MS9292, QFN-48 6 × 6 mm | U9 | 1 | Extended | **91** | — |
| C26537 | onsemi NCP1117ST33T3G, 3.3 V regulator, SOT-223 | U10 | 1 | Extended | 89 k | — |

- **U9 stock is low too:** 91 pieces on 2026-11-14, so check it before you order several boards.
- **U3 stock is very low:** only 11 pieces were in stock. If it runs out, buy it ahead of time in your JLCPCB parts library, or
  wait for a restock. U3 has no drop-in replacement.
- **Extended parts:** there are 11 of them, and JLCPCB charges a setup fee for each extended part. Basic parts have no such fee.
- **10 µF capacitors:** the JLCPCB BOM uses a 25 V X5R capacitor, a Basic part, instead of the 16 V X7R in the DigiKey BOM; X5R
  is rated up to 85 °C. To keep X7R, use C95841 instead (Samsung CL21B106KOQNNNE, Extended, 268 k in stock).
- **U2:** if C6005 runs out, C527451 is a drop-in replacement (TI CD74HCT86M96, same SOIC-14 package, Extended, 10 826 in stock).
- **Not placed:** the DNP parts C50, R60, R73 and R74 (see [`../../bom/BOM.md`](../../bom/BOM.md#not-fitted-dnp)), and TP1-TP4.
- **Values:** all the other values and packages match [`../../bom/BOM.md`](../../bom/BOM.md) (FB1: the DigiKey BOM uses a Murata
  equivalent; C47, C48: Samsung here, Murata in the DigiKey BOM, same value). The BOM, the CPL and the KiCad placement file list
  the same 124 SMD references; positions are the same except J15 (see above).

## Parts you solder yourself

- **Through-hole parts:** C17, D1, J1-J14, J16, J17, J18, JP1-JP10, U1, SW1 and SW2, plus the SH1-SH10 jumpers. TP1-TP4 are not fitted. Order them with
  the [DigiKey BOM](../../bom/BOM-digikey.csv), leaving out the SMD lines (J18 is not in that file: LCSC C160360).

JLCPCB can also solder through-hole parts, at extra cost. For J16, LCSC stocks the Lian Xin XDJK-0271-1650 (C7527522), which fits
the same footprint. LCSC stocks the 10-pin and 12-pin JST NH headers (C160365: 3 292 in
stock; C160367: 133 in stock, on 2026-10-16) and the 4-pin one (J18, C160360: 24 302 in stock, on 2026-11-14).

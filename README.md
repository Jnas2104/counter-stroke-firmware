# counter-stroke-firmware

ZMK-Firmware für die Bluetooth-Tastenbox des [Tischtennis-Zählers](https://github.com/Jnas2104/counter-stroke):
nRF52840 „Pro Micro“/SuperMini (nice!nano-v2-kompatibel), zwei Taster gegen GND.

| Taster | Pad | sendet |
|---|---|---|
| links  | `017` (P0.17) + GND | Pfeil links |
| rechts | `020` (P0.20) + GND | Pfeil rechts |

**Neues Handy koppeln:** Die Box merkt sich nur ein Handy und lehnt jedes andere ab („Koppeln fehlgeschlagen“,
„falsche PIN“, Eintrag verschwindet). Dann **beide Taster 5 s gedrückt halten** → Kopplung gelöscht, das neue
Handy kann sich verbinden. Auf dem alten Handy das Gerät „CounterStroke“ danach unter Bluetooth ignorieren/entfernen.

Jeder Push baut unter **Actions** zwei Dateien: `tt_zaehler-nice_nano_v2-zmk.uf2` (die Firmware) und
`settings_reset-nice_nano_v2-zmk.uf2` (löscht alle Bluetooth-Kopplungen; danach wieder die Firmware flashen).

Flashen: Reset-Taster auf dem Board zweimal schnell drücken → Laufwerk `NICENANO` erscheint → UF2-Datei draufkopieren.

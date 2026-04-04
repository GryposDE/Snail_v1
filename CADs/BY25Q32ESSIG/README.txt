Files included:
- BY25Q32ES.kicad_sym                : KiCad symbol library entry
- BY25Q32ES.pretty/                  : KiCad footprint library folder
- BY25Q32ES_SOIC-8_150mil.kicad_mod  : Footprint for SOP8 150mil package
- by25q32es_reference.kicad_sch      : Reference schematic for standard SPI use

Assumptions:
- Package chosen: SOP8 150mil (BY25Q32ESTIG style package)
- Standard SPI use only; /WP and /HOLD tied high, /CS pulled up, 100nF decoupling cap

Import notes:
1. Add the folder /mnt/data/by25_kicad/BY25Q32ES.pretty as a footprint library in KiCad.
2. Add /mnt/data/by25_kicad/BY25Q32ES.kicad_sym as a symbol library.
3. Open by25q32es_reference.kicad_sch as a starting schematic.

Please verify footprint dimensions against your exact package/order code before manufacturing.

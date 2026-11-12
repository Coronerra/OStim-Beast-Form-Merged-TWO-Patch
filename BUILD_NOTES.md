# Build notes: OStim Beast Form Merged - TWO Patch

## 0.1 (first public release)
- Started from Merged 0.5's `WerewolfBeastRace` record (Growl + JS Emissive Eyes base). Replaced only HEAD/INDX with the head-part list from TWO's `WerewolvesGrowl.esp` and WNAM with a new skin `OBFTWO_SkinNakedWerewolfBeast`.
- Copied TWO's `NakedTorsoWerewolfBeast` ARMA unchanged so TWO's body wins over Merged 0.5's redirect.
- New `OBFTWO_WerewolfSheathAA` (slot 49): the sheath shapes split out of Merged 0.5's male body NIF, partitions re-flagged to 49, geometry/weights untouched. Female model = TWO Core `AddonEmpty.nif`.
- Copied TWO's `FemaleMouthWerewolf` HDPT and fixed NAM1 (`.nif` → TWO's `ExpMouthWerewolf.tri`).
- BFA add-on: same TRI method as the TWO Edition (TWO TRI + 2 authored brow morphs).
- No scripts. No animations or behaviours changed (no Pandora run needed).

Static checks (all pass): `Data/Docs/OStim Beast Form Merged TWO Patch/STATIC_CHECKS_TWO_Patch_0.1.txt` — ESL flag, masters, record list, byte-identity of the race record vs 0.5 apart from HEAD/INDX/WNAM, every HEAD resolves in TWO, slot use, no file byte-identical to or overwriting any TWO / Alternate Textures file, no personal paths. OStrands analysis: `OSTRANDS_TWO_FINDINGS.txt`.

Release asset: `OStim_Beast_Form_Merged_TWO_Patch_0.1.zip` (FOMOD: `00 Patch` required, `10 BFA Heads` optional).

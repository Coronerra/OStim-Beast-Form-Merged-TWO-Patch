# AI_CONTEXT: how OStim Beast Form Merged - TWO Patch works

For AI assistants, bots and modders. Everything written by That Guy (Coronerra) is MIT; third-party assets belong to their authors (see [LICENSE](LICENSE)). Read the main project's AI_CONTEXT first: [OStim-Beast-Form-Merged](https://github.com/Coronerra/OStim-Beast-Form-Merged/blob/main/AI_CONTEXT.md).

## 1. Scope and sibling projects
- **This repo:** a save-safe patch on top of OStim Beast Form Merged 0.5 + Growl that swaps the werewolf look to **TWO - Total Werewolf Overhaul 4.1** (Frosferes). Plugin `OStim_Beast_Form_Merged_TWO_Patch.esp`. `OStim_Beast_Form_Merged.esp` stays enabled with the same FormIDs.
- **[OStim-Beast-Form-Merged](https://github.com/Coronerra/OStim-Beast-Form-Merged):** the main Growl edition this patch needs.
- **[OStim-Beast-Form-TWO](https://github.com/Coronerra/OStim-Beast-Form-TWO):** standalone TWO edition (no Growl). Never combine it with this patch.
- This repo exists separately so it can be removed on request from Frosferes without touching the main project. Never add TWO files to it.

## 2. Repository layout
```
Data/Docs/OStim Beast Form Merged TWO Patch/   packaged README, static checks, OStrands findings
fomod/                                          ModuleConfig.xml + info.xml used by the release zip
BUILD_NOTES.md                                  how the patch was built
```
Binaries (ESP, NIF, TRI) are in the release zip, not in git. There are no scripts.

Release zip: `00 Patch` (required: ESP, `meshes/actors/werewolfbeast/character assets/coronerra/twopatch/werewolfsheath.nif`, docs) and `10 BFA Heads` (optional: `OStim_Beast_Form_Merged_TWO_Patch - BFA Heads.esp`, `meshes/.../coronerra/two/ExpHeadWerewolf_BFA.tri`).

## 3. Patch plugin (ESL, 5 records, HEDR nextID 0x802)
Masters (index order): `Skyrim.esm`, `Update.esm`, `Dawnguard.esm`, `Dragonborn.esm`, `JS Emissive Eyes SE - Johnskyrim.esp`, `Growl - Werebeasts of Skyrim.esp`, `MonsterLipSync1.esp`, `Werewolves.esp` (TWO), `OStim_Beast_Form_Merged.esp`. No OStim / OCum / OCreatures / WerewolvesGrowl master.

| FormID | Type | EditorID | Content |
|---|---|---|---|
| 000CDD84 | RACE | WerewolfBeastRace | Merged 0.5's record byte for byte except HEAD/INDX (TWO's head parts, as TWO's Growl patch lists them) and WNAM (new skin) |
| 000CDD87 | ARMA | NakedTorsoWerewolfBeast | TWO's record unchanged (vanilla body paths, BOD2 0x59C); undoes 0.5's `coronerra\bfa` redirect |
| xx000800 | ARMO | OBFTWO_SkinNakedWerewolfBeast | new skin: TWO body ARMA + sheath ARMA |
| xx000801 | ARMA | OBFTWO_WerewolfSheathAA | slot 49; male = `coronerra\twopatch\werewolfsheath.nif`, female = TWO Core `AddonEmpty.nif` |
| (TWO) 806 | HDPT | FemaleMouthWerewolf | TWO's record; NAM1 `ExpMouthWerewolf.nif` → TWO's `ExpMouthWerewolf.tri` |

No record of `OStim_Beast_Form_Merged.esp` is overridden. Slot use: sheath 49, OBL aroused addon 52, OCum urethra node 48.

The plugin must load directly after `OStim_Beast_Form_Merged.esp`, and `Werewolves.esp` / `WerewolvesGrowl.esp` must load after OCreatures and the Growl patches.

### BFA add-on (ESL, 2 records)
Masters `Skyrim.esm`, `MonsterLipSync1.esp`, `Werewolves.esp`. Overrides `MaleHeadWerewolf` (MFA 0x800 as TWO overrides it) and `FemaleHeadWerewolf` (TWO 0x805), NAM1 only, to `coronerra\two\ExpHeadWerewolf_BFA.tri`. That TRI = TWO's `ExpHeadWerewolf.tri` (1362 verts, 36 morphs, byte-identical) + `browupleft` / `browupright`.

## 4. Sheath mesh
`werewolfsheath.nif` is the limp sheath + tip + knot shapes cut out of Merged 0.5's own male werewolf body (ABC geometry by BakaFactory). Geometry and bone weights are unchanged; only the dismember partitions moved to slot 49. It is fitted to TWO's default pelvis.

## 5. Why it is save-safe
- `OStim_Beast_Form_Merged.esp` keeps its name and FormIDs; the patch adds only two unplaced forms.
- The aroused-swap path saved in `OBL_Main` is unchanged (GT Softbody `Addon_Dog_Black_Hard.nif`).
- HDT Werewolves' `Werewolves.esp` is replaced by TWO's file of the same name; HDT's version only overrode vanilla records, so the one-time missing-content prompt is harmless.

## 6. MFA
`MonsterLipSync1.esp` is a **hard master** of TWO and of this patch (Merged 0.5 itself does not need it). "MFA and Growl Patch" is an older HDT-era plugin and is not required.

## 7. Rules for contributors
- Never add TWO, TWO Alternate Textures, MFA, Growl or Merged 0.5 files to this repo or its zips.
- Keep the patch's FormIDs stable.
- Credit: That Guy (Coronerra); Frosferes for TWO; TealEri (CinnaMewRoll) for MFA morphs; BakaFactory for ABC geometry.

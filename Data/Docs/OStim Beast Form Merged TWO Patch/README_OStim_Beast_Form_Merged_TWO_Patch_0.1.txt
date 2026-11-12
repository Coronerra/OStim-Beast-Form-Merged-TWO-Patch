OStim Beast Form Merged - TWO Patch 0.1 (Skyrim SE / AE)
By That Guy (Coronerra)
https://github.com/Coronerra/OStim-Beast-Form-Merged-TWO-Patch

WHICH DOWNLOAD IS FOR YOU?
--------------------------
There are three related downloads. Use exactly ONE setup:
- OStim Beast Form Merged 0.5 (Growl edition) on its own: Growl with the
  HDT Werewolves / ABC look.  https://github.com/Coronerra/OStim-Beast-Form-Merged
- OStim Beast Form Merged 0.5 + THIS PATCH: you use Growl and Merged 0.5 and
  want TWO - Total Werewolf Overhaul 4.1 bodies and heads, without losing
  your save.
- OStim Beast Form - TWO Edition: you use TWO and do NOT need Growl.
  https://github.com/Coronerra/OStim-Beast-Form-TWO
This patch and the TWO Edition must NEVER be used together.

WHAT THIS IS
------------
A small patch for people who already run OStim Beast Form Merged 0.5 with
Growl and want the bodies and heads from TWO - Total Werewolf Overhaul 4.1
(Frosferes) instead of the HDT Werewolves / BFA look.
- It is NOT a new edition and NOT a repack. OStim_Beast_Form_Merged.esp stays
  installed and enabled, with the same name and the same FormIDs, so saves
  that use it keep working.
- TWO's werewolf body, heads, skeleton, SMP and textures (and TWO Alternate
  Textures if you use them) take over the look.
- Growl's gameplay (attacks, keyword, spells) and everything Beast Form does
  stay: OStim as a werewolf/VL, hubs, Beast Aware, SkyrimNet/OStimNet, the
  shift-back timer pause, Lirael packs, optional OCreatures, Beast Load (OCum),
  OCum Werewolf Shot, and the GT Softbody aroused swap.
- The 0.5 limp sheath + penis tip + knot is kept. It is now its own piece
  (slot 49) that sits on TWO's body, so it shows outside scenes and stays
  under the GT Softbody cock during scenes, the same way 0.5 looked.
- TWO's own hard canine mesh is NOT used. Scenes use the same GT Softbody
  aroused cock as 0.5.
- No TWO file is included. You need your own copy of TWO 4.1.

FILES
-----
00 Patch (required)
  OStim_Beast_Form_Merged_TWO_Patch.esp   ESL-flagged ESP, 5 records
  meshes\actors\werewolfbeast\character assets\coronerra\twopatch\
      werewolfsheath.nif                  the 0.5 sheath + tip, cut out of
                                          0.5's own male body (geometry and
                                          weights unchanged, partitions -> 49)
  Docs\OStim Beast Form Merged TWO Patch\  this README, static checks, OStrands
                                          findings
10 BFA Heads (optional)
  OStim_Beast_Form_Merged_TWO_Patch - BFA Heads.esp   ESL-flagged ESP
  meshes\actors\werewolfbeast\character assets\coronerra\two\
      ExpHeadWerewolf_BFA.tri             TWO's head expression TRI plus the two
                                          brow-raise morphs Better Facial
                                          Animations needs
No TWO, Alternate Textures, MFA, Growl or Merged 0.5 file is included or
overwritten. Nothing from Merged 0.5 needs replacing.

WHAT THE PATCH PLUGIN CHANGES (all else comes from your installed mods)
-----------------------------------------------------------------------
Masters: Skyrim, Update, Dawnguard, Dragonborn, JS Emissive Eyes SE -
Johnskyrim.esp, Growl - Werebeasts of Skyrim.esp, MonsterLipSync1.esp,
Werewolves.esp (TWO), OStim_Beast_Form_Merged.esp. (The first six are the
same masters Merged 0.5 already has, in the same order. MonsterLipSync1.esp
and Werewolves.esp are new hard masters.)
1. RACE WerewolfBeastRace: Merged 0.5's race record byte for byte (Growl
   keyword and attacks, JS Emissive Eyes glow spell, FaceGen on, voices),
   except:
   - head parts = TWO's (MFA male head/mouth/eyes as TWO overrides them, TWO
     female head/mouth/eyes, TWO fur parts), exactly as TWO's Growl patch
     lists them;
   - skin = a new skin armor (below) instead of the vanilla one.
2. ARMA NakedTorsoWerewolfBeast: TWO's record unchanged (vanilla body paths,
   which TWO and BodySlide fill). This undoes Merged 0.5's redirect to the
   coronerra\bfa bodies.
3. ARMO OBFTWO_SkinNakedWerewolfBeast (new): TWO body addon + sheath addon.
4. ARMA OBFTWO_WerewolfSheathAA (new): slot 49, males get the sheath,
   females get TWO's empty addon (nothing).
5. HDPT FemaleMouthWerewolf: TWO's record with one fix. TWO names
   ExpMouthWerewolf.nif as the mouth's expression file. It now points to
   TWO's own ExpMouthWerewolf.tri, so female werewolf mouths can move.
Vampire Lord: untouched. 0.5's VL heads, body, JS glow and hard swap stay.
Nothing in OStim_Beast_Form_Merged.esp is overridden. No scripts.

BFA heads add-on (optional): overrides TWO's MaleHeadWerewolf and
FemaleHeadWerewolf head parts. It only changes which expression TRI they use
(ExpHeadWerewolf_BFA.tri). Head shapes, BodySlide builds and textures stay
TWO's. Without it, TWO's heads still talk and emote with MFA, but Better
Facial Animations has no brow-raise morphs on the werewolf (same gap TWO and
MFA have).

REQUIREMENTS
------------
- OStim Beast Form Merged 0.5 (keep it enabled; its plugin stays)
- Growl - Werebeasts of Skyrim
- JS Emissive Eyes (already a master of Merged 0.5)
- GT - Softbody, OCum, "OCum TL SceneFix + GT Softbody Merge" and the other
  0.5 requirements (SKSE, PapyrusUtil, OStim, FSMP, ...)
- Monster Facial Animation / Monster Lipsync SE (MonsterLipSync1.esp).
  REQUIRED: TWO and this patch both list it as a master. Merged 0.5 by itself
  does not need it, so install it now if you don't already have it.
- NEW: TWO - Total Werewolf Overhaul 4.1 (Frosferes, LoversLab; not
  included). FOMOD choices:
    Core: yes (required)
    Genitals: None   (CF Standalone needs Creature Framework, HCOS needs
                      Horny Creatures, SOS needs Schlongs of Skyrim. The
                      patch already gives males the 0.5 sheath; picking CF,
                      HCOS or SOS would give a second set at rest.)
    Extras: off       (needs HCOS)
    Wicked Werewolves skeleton: OFF (changes proportions; animations would
                      line up worse)
    SOS addon patches: off
    Misc patches: Growl ON (the installer ticks it for you). Moonlight Tales: off.
NOT REQUIRED: "MFA and Growl Patch" (an older plugin from the HDT Werewolves
era). This patch does not need it. If it is already in your list you can
leave it; it no longer decides the werewolf look, because this patch's race
record loads later and wins.

OPTIONAL
--------
- TWO - Alternate Textures 4.0 (textures only; any choice is fine)
- BodySlide builds of TWO's bodies/heads. You do NOT have to run BodySlide:
  TWO's default bodies and heads already work. Only build if you want TWO's
  sliders/presets. If you do, the output must go in its OWN mod BELOW TWO in
  the left pane (if it goes into an older BodySlide output mod that sits above
  TWO, TWO still wins and you keep seeing the defaults). The sheath is fitted
  to TWO's default pelvis (the same shape TWO's own soft canine uses), so very
  different groin sliders can make it float or clip.
- Better Facial Animations + the BFA Heads add-on (see below)
- OCreatures.esp, exactly as optional as in 0.5

DISABLE
-------
- "HDT werewolves SMP" (its plugin is ALSO called Werewolves.esp; it cannot
  run next to TWO). Leave it unticked in the left pane.
- Keep these off if they are not already: Female Werewolf ABC HDT MFA,
  FemaleWerewolf_Compat_JSEyes, any FemaleWerewolf genitals test files,
  BeastForm_BFA_Heads and BeastFormBFAHeads - Growl JSEyes Patch.esp,
  Werewolves Reposed SSE, and the old separate Beast Form / Beast Lite /
  Beast Aware / Werewolf Shot mods (all merged into 0.5).
- OStim Beast Form - TWO Edition, if you ever installed it. Never run it
  together with this patch.
Leave enabled: OStim Beast Form Merged, Growl and its patches, MFA
(MonsterLipSync1.esp, a required master), JS Emissive Eyes, GT - Softbody,
OCum TL SceneFix + GT Softbody Merge. BakaFactory Animated Beasts Cocks stays
OFF as in 0.5 (Merged ships the textures it needs). If you ever turn it on,
TWO must win its werewolf skeleton/body files.

INSTALL (MO2)
-------------
1. In game: change back to human form, leave any scene, and make a NEW save.
2. Close Skyrim AND Mod Organizer.
3. Back up your profile folder (plugins.txt, loadorder.txt, modlist.txt).
4. Install MFA (Monster Lipsync SE) if you don't have it yet.
5. Install TWO 4.1 with the FOMOD choices above. Optionally install TWO
   Alternate Textures.
6. Install this zip ("Install a new mod from archive"). Tick "BFA Heads" only
   if you use Better Facial Animations.
7. Left pane (mod priority, lower wins). Put these, in this order, BELOW
   OStim Beast Form Merged, BakaFactory Animated Beasts Cocks (if on), Monster
   Lipsync SE, MFA and Growl Patch (if you have it), Growl, GT - Softbody and
   OCreatures Reforged (if used):
       TWO - Total Werewolf Overhaul 4.1
       TWO - Alternate Textures            (optional)
       your TWO BodySlide output           (optional, its own mod)
       OStim Beast Form Merged - TWO Patch
   Then open TWO's Conflicts tab: TWO (or your TWO BodySlide output) must WIN
   actors\werewolfbeast\character assets\skeleton.nif and the
   malebodywerewolf / femalebodywerewolf files. TWO and Merged 0.5 overlap
   only on the MoreNastyCritters werewolf textures, and those are
   byte-identical, so that conflict doesn't matter.
   Untick HDT werewolves SMP.
8. Right pane (plugins). Move them by hand; do NOT let LOOT re-sort them:
       ... MonsterLipSync1.esp ... Growl - Werebeasts of Skyrim.esp ...
       ... your Growl patches ...
       Werewolves.esp                       <- TWO, right after the Growl patches
                                               (and after OCreatures.esp if on)
       WerewolvesGrowl.esp                  <- right after Werewolves.esp
       ... everything else unchanged ...
       OStim_Beast_Form_Merged.esp          <- stays where it is now
       OStim_Beast_Form_Merged_TWO_Patch.esp            <- directly below it
       OStim_Beast_Form_Merged_TWO_Patch - BFA Heads.esp <- optional, directly below
       ... anything that must stay last in your list (for example map mods)
           stays last.
   The patch masters Merged and Werewolves.esp, so MO2 will flag it if it
   ends up above either.
9. No Pandora/FNIS run is needed (no animations or behaviors changed).
10. Start the game and load the save from step 1.
   - If Skyrim says some content is missing, that is HDT Werewolves'
     Werewolves.esp being replaced by TWO's file with the same name. HDT's
     file only edited vanilla records, so nothing in your save depended on
     it. Click Yes, then make a new save.
   - Transform. You should get TWO's body and head.

NEW GAME? No.
-------------
The save keeps every Beast Form form, quest, MCM setting, hotkey and Beast
Load state, because OStim_Beast_Form_Merged.esp is still there with the same
FormIDs, and the patch doesn't touch any of them. The patch only adds two
forms of its own (a skin and an armor addon), which are never placed in the
world or an inventory.
Mid-save caveats:
- A save made while you were transformed can come up with the old 0.5
  head/body until you change back and transform again. Install from a
  human-form save to avoid this.
- Werewolf NPCs that are already loaded keep their old look until their
  cell reloads.
- The aroused-swap mesh path is stored in the save, but this patch doesn't
  change it (it is still the GT Softbody cock), so nothing goes stale.
- If OStim is set to keep a scene going while you save/load, finish the
  scene first, as with any Beast Form update.

UNINSTALL
---------
Change back to human form, save, quit. Untick the patch (and the BFA add-on)
and TWO's two plugins (Werewolves.esp, WerewolvesGrowl.esp), disable TWO, and
re-enable HDT werewolves SMP. The 0.5 look comes back and the save still
loads.

FEATURE PARITY WITH MERGED 0.5
------------------------------
Carried over unchanged (they live in OStim_Beast_Form_Merged.esp and its
files, which this patch does not touch):
- OStim as a werewolf/VL with your mind intact, hotkey and MCM
- Hubs and pack pages (Billyy/Baka/FlufyFox/FunnyBiz/WWF_OnTop), Lirael packs
- Beast Aware, SkyrimNet + OStimNet bridge, scene descriptions
- Shift-back timer pause (PlayerWerewolfShiftBackTime)
- Beast Load / Beast Pie (OCum), multi-round stacking
- OCum Werewolf Shot: the urethra node uses bone WWD 9, which TWO's skeleton
  has at the same rest position as the ABC skeleton
- GT Softbody aroused swap: same OBL_WerewolfAddon record, same
  MoreNastyCritters\werewolf\Addon_Dog_Black_Hard.nif, same slot 52. Keep
  GT - Softbody and the OCum TL + GT Softbody merge installed.
- ABC: the limp sheath, penis tip and knot from 0.5 (now on slot 49) and the
  ABC/MNC textures (Merged 0.5 and TWO ship identical copies)
- Optional OCreatures support (OCR keyword restore at runtime)
- Vampire Lord: everything, including the JS Emissive Eyes VL glow
- Werewolf JS Emissive Eyes glow: the glow spell is still on the werewolf
  race, unchanged from 0.5. TWO's eyes are a different mesh, so whether the
  glow sits right on them is test item 6 below.
Changed on purpose:
- Werewolf body, heads, skeleton, SMP and textures: TWO's instead of 0.5's
  HDT/ABC/BFA bodies and heads.
- BFA on werewolf heads: via the optional BFA Heads add-on instead of 0.5's
  own head parts.

OSTRANDS: NO NEW OSTRANDS NEEDED
--------------------------------
Keep your current OStrands (0.8.0.3) and OStrands.ini as they are.
- The werewolf penis rig is WWD 2..WWD 9. TWO's skeleton has all of them, at
  the same rest positions as the ABC and OCreatures skeletons (differences
  under 0.002 units).
- OStrands decides "he has an erect penis" by looking for a mesh skinned to
  WWD 7/8/9. Outside scenes, neither TWO's body nor the sheath uses those
  bones, so there are no strands or precum while soft, same as 0.5. In
  scenes, the GT cock (WWD 3-9) is worn exactly as in 0.5.
- Female werewolves get BETTER results: TWO's skeleton has the real
  vagina/anus bones OStrands looks for (NPC L/R Pussy02, VaginaB1,
  Clitoral1, VaginaDeep1, the four NPC Anus2 bones, NPC Anus Deep1). The
  ABC/OCR skeletons lack most of them, which is why the 0.8.0.3
  [CreatureOpenings] fallback exists. That fallback only kicks in when
  those bones are missing, so with TWO it just stays unused.
- Mouth (NPC Head / Head MagicNode) and body bones are the same names.
- OStrands reads no mesh paths or NiStringExtraData for werewolves, so TWO's
  file names don't matter to it.
Details: Docs\OStim Beast Form Merged TWO Patch\OSTRANDS_TWO_FINDINGS.txt

PLEASE CHECK (test list for 0.1)
--------------------------------
0.1 has passed static checks (records, masters, paths, mesh and TRI checks;
see STATIC_CHECKS_TWO_Patch_0.1.txt) but has not had wide in-game testing
yet. If something below looks wrong, please open an issue on GitHub.
1. Male werewolf, out of a scene: TWO body + TWO head, the 0.5 sheath/tip/
   knot visible, not floating, no purple textures. Female: TWO body, no sheath.
2. Male werewolf OStim scene: the GT Softbody cock appears over the sheath
   (one cock), softbody physics work, and it goes away after the scene.
   Watch the balls: TWO's body SMP also swings the WWLB/WWRB ball bones the
   GT mesh uses. Report it if they jitter or stretch.
3. Beast Load / Werewolf Shot climax: cum comes from the tip.
4. OStrands: strands from the GT cock in scenes, none while soft. Female
   werewolf scenes use the vagina/anus openings.
5. Talking/expressions: MFA lip sync on TWO heads; female mouth moves now;
   with the BFA add-on, brows raise.
6. JS Emissive Eyes glow sits on TWO's eyes (the glow follows head nodes, but
   TWO's eyes are a different mesh).
7. Vampire Lord unchanged.
8. Hubs, Beast Aware, SkyrimNet, timer pause: unchanged.
9. OCreatures on (if you use it): the race order still works (Werewolves.esp
   after OCreatures.esp).
10. Load a human-form save from before the install: no missing-form errors
   beyond the one-time missing-content prompt.

PERMISSIONS
-----------
- This download contains NONE of TWO's meshes, textures, plugins or skeleton.
  You must already own TWO 4.1 (Frosferes, LoversLab). The plugin only points
  at TWO's file paths and carries over two TWO records (the body addon, and
  the female mouth head part with its file-name fix), as any compatibility
  patch does.
- 00 Patch: the sheath mesh is cut from Merged 0.5's own male body (ABC
  geometry by BakaFactory). It has the same assets and permissions as 0.5.
- Permission was sought from Frosferes before publishing. Frosferes has been
  unreachable since 2023. This patch is kept in its own repository so that,
  if Frosferes objects, it can be removed without affecting the main OStim
  Beast Form Merged project.
- 10 BFA Heads: ExpHeadWerewolf_BFA.tri is a modified copy of TWO's
  expression TRI (TWO bases it on MFA morphs by TealEri, aka CinnaMewRoll),
  with only browupleft / browupright added; TWO's 36 morphs and vertex data
  are kept. Credit to Frosferes and TealEri. The same takedown applies to it.
- That Guy (Coronerra)'s own work here (plugins and docs) is MIT; see the
  GitHub repository LICENSE. Third-party assets belong to their authors.

CREDITS
-------
- Frosferes: TWO - Total Werewolf Overhaul (bodies, heads, skeleton, SMP).
- TealEri (aka CinnaMewRoll): Monster Facial Animation and Expressive
  Werebeasts, the base of TWO's expressive heads.
- BakaFactory: Animated Beast's Cocks (the sheath geometry, as in 0.5).
- EnaiSiaion: Growl. johnskyrim: JS Emissive Eyes. Goutou: GT - Softbody.
- Everyone credited in the OStim Beast Form Merged 0.5 README.
- That Guy (Coronerra): OStim Beast Form Merged, this patch and the BFA brow
  morphs.

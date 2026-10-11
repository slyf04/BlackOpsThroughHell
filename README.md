# Black Ops through Hell

DOOM 3's campaign, from the Mars City arrival onward, played as **Alex**, a Black Ops III super-soldier.

- **Black Ops III movement:** jump again in mid-air to thrust-jump, crouch while sprinting to power-slide, and jump
  at a wall while holding forward to wall-run (jump again to kick off it).
- **Tank Dempsey's real lines** from Black Ops III Zombies on kills, headshots, kill streaks, pickups, low health,
  low ammo and boss demons.
- **Scorestreaks:** kills earn a **UAV** (shows every demon on the minimap for 30 s) and a **Care Package** (a crate
  drops in front of you: ammo for every gun, +50 health, +50 armor), each with Black Ops III's announcer.
- **The Ray Gun** is your specialist weapon: kills fill the specialist ring on the HUD. When it's full, equip the
  real Black Ops III Ray Gun for 20 green splash bolts, then you get your old gun back.
- **Black Ops III guns** in place of DOOM 3's, with Black Ops III arms, animations and sounds: MR6 (pistol),
  KRM-262 (shotgun), KN-44 (machine gun), Death Machine (chaingun), frag grenade, Wunderwaffe DG-2 (plasma gun),
  XM-53 (rocket launcher), Thundergun (BFG) and Bowie knife (fists). Hold the right mouse button to aim down the
  sights (the XM-53 goes up on your shoulder and you aim through its sight, firing with Black Ops III's own recoil).
- **Wonder weapons:** the DG-2 fires a lightning bolt that jumps from demon to demon, electrocuting up to 11; the
  Thundergun's blast throws every demon in front of you back as a ragdoll.
- **Black Ops III HUD** built from Black Ops III's own art and fonts: minimap with compass (the level's floor plan;
  demons hunting you show up, and every demon while your UAV is up), ammo counter with the weapon name and your
  grenades, the Ray Gun specialist ring, scorestreak icons, crosshair and hit markers, and Alex's player card with
  your kills and armor. DOOM 3 keeps its objectives, PDA and video downloads, flashlight and oxygen meters.
  (`bth_hud 0` in the console brings DOOM 3's HUD back.)
- **Black Ops III health:** there's no health number. The screen edges go red as you get hurt, and a few seconds
  without a hit heals you back to full. Armor still works, and medkits still heal.
- **DOOM 3's campaign and soundtrack** as normal (no rounds). Dying plays a short scary DOOM 3 sting.
- **Alex's face on the DOOM 3 marine** in every cutscene (DOOM 3, Resurrection of Evil and The Lost Mission) and in
  third-person view, moving with DOOM 3's own facial animation; Alex's portrait on the HUD, and Alex's name and photo
  on the PDA.
- **New faces for Sergeant Kelly, Jack Campbell and Councilor Swann** (Swann without his glasses), on DOOM 3's own face
  rigs: they talk, blink and act in every scene with DOOM 3's own animations.
- **Black Ops III's safehouse loading movie** plays while the game starts, and the game has its own icon and its own
  Black Ops through Hell logo on the main menu.

Solo. DOOM 3 has no co-op campaign.

## What you need

- **DOOM 3: BFG Edition** (on Steam it's now called "DOOM 3", app 208200). The mashup plays from your copy.
- **Call of Duty: Black Ops III**. Its guns, animations, HUD art, fonts and sounds are read from your copy the first
  time you start (under a minute from an internal drive, a few minutes from a USB hard drive, with Black Ops III's
  loading movie playing meanwhile; later starts take seconds).
  **Dempsey's lines need Black Ops III's Zombies Chronicles content.** Without it, everything else still works and
  Alex just doesn't speak.
- Windows 10 or 11 with a DirectX 12 graphics card.

Nothing from either game is included in the download. The mashup reads both games from your PC.

## Controls (added to DOOM 3's)

| Key | Action |
|---|---|
| Right mouse | Aim down the sights |
| Space (in the air) | Thrust jump |
| C while sprinting | Power slide |
| Space during a wall-run | Wall jump |
| G | Equip the Ray Gun when charged |
| Z | Call in the UAV |
| X | Call in the Care Package |
| V | Third-person view (see Alex) |

## Where things go

- Saves, settings and everything read from Black Ops III: `Saved Games\Black Ops through Hell`.
- The mashup never changes either game's folder.

## How it works

It is a fork of the open-source **RBDOOM-3-BFG 1.6.0** engine (GPL-3). At first start it reads Black Ops III's sound
banks (`zone/snd/*.sabs|.sabl`, FLAC inside), fastfiles and xpaks (`zone/*.ff|.xpak`) and converts only what it
needs: gun and arm models to md5 meshes, animations to md5 animations, textures and HUD art to DOOM 3 BFG images,
and the HUD's TrueType fonts to DOOM 3 fonts. While it works, Black Ops III's loading movie (`video/*.mkv`) plays,
decoded by Windows' own Media Foundation. It builds Alex's head on the skeleton of your DOOM 3 player head, and
it changes DOOM 3's definitions in memory. No game files are shipped or modified. Everything the mashup does is driven by the design sheets in `sheets/` (`tools/preflight.py` checks them,
`tools/gen.py` turns them into code and data).

Both games are found through Steam (every Steam library), so the exe can simply be double-clicked. To point it
elsewhere: `+set fs_basepath "<DOOM 3 folder>"` on the command line and the environment variable `BTH_BO3_DIR` for
the Black Ops III folder (Melty sets both). The `bth_status` console command prints what was imported.

## Credits and licences

- Engine: RBDOOM-3-BFG by Robert Beckebans and contributors, based on the DOOM 3 BFG Edition GPL source by id
  Software. GPL-3, see `licenses/`. The full modified source is offered as a separate download next to this release.
- dr_flac by David Reid (public domain / MIT-0); stb_truetype by Sean Barrett (MIT / public domain); BC7 tables from
  Intel's ISPC Texture Compressor (MIT).
- Black Ops III file layouts as documented by Greyhound (Scobalula, GPL-3).
- Microsoft Visual C++ runtime (redistributable).
- Alex's head and portrait: the creator's own Avaturn avatar.
- Built with Claude (Anthropic) using the universal-modder toolkit.
- DOOM 3 is (c) id Software / ZeniMax. Call of Duty: Black Ops III is (c) Activision / Treyarch. Neither is affiliated
  with this mashup. Their content stays in your own installs.

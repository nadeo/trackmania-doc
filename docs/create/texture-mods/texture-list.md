# Texture List

This is a living document - if you see something inaccurate/missing, feel free to contribute.

## Suffixes

| **Suffix** | **Format** | **Filetype** | **Purpose** | **Notes**
| :-: | :-: | :-: | :-: | :-: |
| \_D | Diffuse | DDS (BC1)<br>DDS (BC3 if transparent) | Base image/texture |
| \_H | | DDS (BC1) | Height | Grey `(128,128,128)` is level<br>Black `(0,0,0)` lowers elevations<br>White `(255,255,255)` raises elevation
| \_I | Illum | | Self-illumination, texture glows but doesn't emit light | 
| \_L | | | Color of lightbulbs/LEDs | Displaced by `_H`
| \_M | | DDS (BC1) | Mask (black/white) | Color is determined by `DecalPaint_D`
| \_N | Normal | DDS (BC5) | Texture that stores a direction at each pixel
| \_O | | | Texture overlaid on top of glass (grayscale)
| \_R | Roughness | DDS (BC5) | Roughness (matte/shiny)<br>Metallic | Can be kept as greyscale (BC1) if not used<br> Red channel is used for roughness, green channel is used for metallic
| \_T | | | Glass color
| \_X2 | | DDS (BC1) | Large overlay for color values |

### Hue Masks

- `_HueMask`
- `_HueMask2`
- `_HueShiftMask`

These textures determine what is tintable and what isn't - they use the RGB channels.
**Red** and **Blue** are kept black, **Green** follows these rules:

- White pixels determine what is colorable.
- Black pixels determine what isn't.
- Greyscale can be used to blend with the corresponding material's `_D` color.

## 📁 Image

| **Name** | **Used For** | **\_D** | **\_H** | **\_I** | **\_L** | **\_M** | **\_N** | **\_O** | **\_R** | **\_T** | **\_X2** | **\_HueShiftMask**
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| Ad1x1Screen | Default 1x1 sign |||||||||||| 
| Ad2x1Screen | Default 2x1 sign |||||||||||| 
| Ad4x1Screen | Default 4x1 sign |||||||||||| 
| CanopyGlass | Canopy glass | _D ||||| _N || _R ||| _HueMask | 
| CanopyStructure | Canopy edges | _D | _H | _I | _L || _N || _R ||| _HueMask | 
| Canopy | Canopy "X" shapes | _D ||||| _N || _R ||| _HueMask | 
| ChronoCheckpoint | Checkpoint chronometer ||| _I ||||||||| 
| ChronoFinish | Finish chronometer ||| _I ||||||||| 
| Chrono | Multilap chronometer | _D | _H | _I | _L || _N || _R |||| 
| CustomBricks | | _D ||||| _N || _R |||| 
| CustomConcrete | | _D ||||| _N || _R || _X2 || 
| CustomDirt | | _D ||||| _N || _R |||| 
| CustomGrass | | _D ||||| _N || _R || _X2 || 
| CustomIce | | _D ||||| _N || _R |||| 
| CustomMetalPainted | | _D ||||| _N || _R |||| 
| CustomMetal | | _D ||||| _N || _R |||| 
| CustomModAddSelfIllum2 | ||| _I ||||||||| 
| CustomModAddSelfIllum | ||| _I ||||||||| 
| CustomModColorize2 | | _D ||||| _N || _R ||| _HueShiftMask | 
| CustomModColorize | | _D ||||| _N || _R ||| _HueShiftMask | 
| CustomModDecal2 | | _D ||||| _N || _R |||| 
| CustomModDecal | | _D ||||| _N || _R |||| 
| CustomModOpaque2 | | _D ||||| _N || _R |||| 
| CustomModOpaque | | _D ||||| _N || _R |||| 
| CustomModSelfIllum2 | | _D | _H | _I | _L || _N || _R |||| 
| CustomModSelfIllumSimple2 | | _D || _I ||| _N || _R |||| 
| CustomModSelfIllumSimple | | _D || _I ||| _N || _R |||| 
| CustomModSelfIllum | | _D | _H | _I | _L || _N || _R |||| 
| CustomModTrans2 | | _D ||||| _N || _R |||| 
| CustomModTrans | | _D ||||| _N || _R |||| 
| CustomPlasticShiny | | _D ||||| _N || _R |||| 
| CustomPlastic | | _D ||||| _N || _R |||| 
| CustomRockPxz | | _D ||||| _N || _R |||| 
| CustomRockPy | |||||||||| _X2 || 
| CustomRock | | _D ||||| _N || _R |||| 
| CustomRoughWood | | _D ||||| _N || _R |||| 
| CustomSand | | _D ||||| _N || _R |||| 
| CustomSnow | | _D ||||| _N || _R || _X2 || 
| DecalCurbs | Markings on curved roads | _D ||||| _N || _R ||| _HueMask | 
| DecalGateGameplay | Stadium gate decal | _D ||||| _N || _R |||| 
| DecalGateGameplay_Desert | Desert gate decal |||||||||||| 
| DecalGateGameplay_Rally | Rally gate decal |||||||||||| 
| DecalGateGameplay_Snow | Snow gate decal |||||||||||| 
| DecalLogo4x1 | Trackmania logo ||||| _M ||||||| 
| DecalLogo8x1 | Trackmania text ||||| _M ||||||| 
| DecalMarksItems | Item decals | _D ||||| _N || _R ||| _HueShiftMask | 
| DecalMarksRamp | Ramp decals | _D ||||| _N || _R |||| 
| DecalMarksStart | Start pad decal | _D ||||| _N || _R ||| _HueMask | 
| DecalMarks | Decals | _D ||||| _N || _R |||| 
| DecalObstaclePusher | Pusher decals | _D ||||| _N || _R |||| 
| DecalObstacleTube | Pipe decals | _D ||||| _N || _R |||| 
| DecalObstacleTurnstile | Spinner decals |||||| _N || _R |||| 
| DecalObstacleTurnstileLeft | Spinner decals | _D ||||||||||| 
| DecalObstacleTurnstileRight | Spinner decals | _D ||||||||||| 
| DecalPaint | Color of roadside decals | _D ||||| _N || _R ||| _HueMask | 
| DecalPaint2 | Color of roadside decals | _D ||||||||||| 
| DecalPlatform | Tech platform borders | _D ||||| _N || _R ||| _HueMask | 
| DecalPlatformDirt | Dirt platform borders | _D ||||||||||| 
| DecalPlatformGrass | Grass platform borders | _D ||||||||||| 
| DecalPlatformIce | Ice platform borders | _D ||||||||||| 
| DecalPlatformPlastic | Plastic platform borders | _D ||||||||||| 
| DecalSpecialBoost2 | Super reactor boost decal | _D ||||||||||| 
| DecalSpecialBoost | Reactor boost decal | _D ||||||||||| 
| DecalSpecialCruise | Cruise control decal | _D ||||||||||| 
| DecalSpecialFragile | Fragile decal | _D ||||||||||| 
| DecalSpecialMarks | Effect block decals | _D ||||| _N || _R |||| 
| DecalSpecialNoBrake | No brakes decal | _D ||||||||||| 
| DecalSpecialNoEngine | Engine off decal | _D ||||||||||| 
| DecalSpecialNoSteering | No steering decal | _D ||||||||||| 
| DecalSpecialReset | Reset decal | _D ||||||||||| 
| DecalSpecialSlowMotion | Slow motion decal | _D ||||||||||| 
| DecalSpecialTurbo2 | Super turbo decal | _D ||||||||||| 
| DecalSpecialTurboRoulette | Roulette turbo decal | _D ||||||||||| 
| DecalSpecialTurbo | Turbo decal | _D ||||||||||| 
| DecalSpecial | Effect block decal |||||| _N || _R |||| 
| DecalSponsor1x1BigA | 1x1 decal on waypoints (can be overridden by clubs) | _D ||||| _N || _R |||| 
| DecalSponsor4x1A | "Trackmania" decal on waypoints (can be overridden by clubs) ||||| _M ||||||| 
| DecalSponsor4x1B | "Nadeo" decal on waypoints ||||| _M ||||||| 
| DecalSponsor4x1C | "Ubisoft" decal on waypoints ||||| _M ||||||| 
| DecalSponsor4x1D | "Stadium" decal on waypoints ||||| _M ||||||| 
| DecoCliffBase | Bottom of large grass cliff blocks | _D ||||| _N || _R ||| _HueMask | 
| DecoCliffBaseDirt | Bottom of large sand cliff blocks | _D ||||||||||| 
| DecoCliffBaseIce | Bottom of large snow cliff blocks | _D ||||||||||| 
| DecoCliffPxz | Grass cliff rocks | _D ||||| _N || _R |||| 
| DecoCliffDirtPxz | Sand cliff rocks | _D ||||| _N || _R |||| 
| DecoCliffIcePxz | Snow cliff rocks | _D ||||| _N || _R |||| 
| DecoHill | DecoHill block texture | _D ||||| _N || _R |||| 
| DecoHill2 | Borders of open roads | _D ||||||||||| 
| DecoHillPy | UVless grass texture | _D ||||| _N || _R || _X2 || 
| DecoHillDirt | DecoHill block texture | _D ||||| _N || _R |||| 
| DecoHillDirt2 | Borders of open roads | _D ||||||||||| 
| DecoHillDirtPy | UVless sand texture | _D ||||| _N || _R || _X2 || 
| DecoHillIce | DecoHill block texture | _D ||||| _N || _R |||| 
| DecoHillIce2 | Borders of open roads | _D ||||||||||| 
| DecoHillIcePy | UVless snow texture | _D ||||| _N || _R || _X2 || 
| DecoTechnics | | _D ||||| _N || _R |||| 
| DirtPy | Dirt platform | _D ||||| _N || _R || _X2 | _HueMask | 
| FoggerSmoke | Smoke from foggers |||||||||||| 
| GateGameplayScreen | Stadium gate screen |||||||||||| 
| GateGameplayScreen_Desert | Desert gate screen |||||||||||| 
| GateGameplayScreen_Rally | Rally gate screen |||||||||||| 
| GateGameplayScreen_Snow | Snow gate screen |||||||||||| 
| GlassWaterWall | Waterfall |||||| _N | _O | _R | _T ||| 
| GlossyFloor | Floor of the disc in the main menu | _D ||||| _N || _R |||| 
| GrassFence | 3D grass on the stadium floor | _D ||||||||||| 
| Grass | Stadium grass | _D ||||| _N || _R || _X2 || 
| IceMarks | Scratch marks on ice ||||| _M | _N || _R |||| 
| IcePy | |||||| _N || _R |||| 
| ItemAd1x1ScreenSmall | Yellow arrow sign ||| _I ||||||||| 
| ItemAd1x1ScreenSmallC | Green arrow sign ||| _I ||||||||| 
| ItemAd1x1ScreenSmallB | Red arrow sign ||| _I ||||||||| 
| ItemAd1x1ScreenSmallWrongWay | Wrong way sign ||| _I ||||||||| 
| ItemBase | Bottom of tree items | _D ||||| _N || _R |||| 
| ItemBorder | | _D ||||| _N || _R |||| 
| ItemCactus | Cactus | _D ||||| _N || _R |||| 
| ItemCherryTreeBranch | Cherry tree leaves | _D ||||| _N || _R |||| 
| ItemCherryTreePetals | Cherry tree falling petals | _D ||||| _N |||||| 
| ItemCypressBranch | Cypress leaves | _D ||||| _N || _R |||| 
| ItemFallTreeBranch | Fall tree leaves | _D ||||||||||| 
| ItemFallTreePetals | Fall tree falling leaves | _D ||||| _N |||||| 
| ItemFirBranch | Fir leaves | _D ||||| _N || _R |||| 
| ItemFirSnowBranch | Snowy fir leaves | _D ||||| _N || _R |||| 
| ItemFlag | Flag | _D ||||||| _R ||| _HueMask | 
| ItemFrozenTreeBranch | Frozen tree leaves | _D ||||||||||| 
| ItemInflatableFloor | Plastic platform | _D ||||| _N || _R ||| _HueMask | 
| ItemInflatableMat | Plastic item sides | _D ||||| _N || _R ||| _HueMask | 
| ItemInflatableTube | Pipe items | _D ||||| _N || _R ||| _HueMask | 
| ItemLamp | Lamp item | _D | _H | _I | _L || _N || _R |||| 
| ItemLampB | Lamp item (warm white) ||| _I ||||||||| 
| ItemLampC | Lamp item (cool white) ||| _I ||||||||| 
| ItemObstacle | Moving items | _D ||||| _N || _R |||| 
| ItemObstacleLight | Lights on moving items | _D | _H | _I | _L || _N || _R |||| 
| ItemObstaclePusher | Pushers | _D ||||| _N || _R |||| 
| ItemPalmTreeBark | Palm tree bark | _D ||||| _N || _R |||| 
| ItemPalmTreeBranch | Palm tree leaves | _D ||||| _N || _R |||| 
| ItemPillar | Pole | _D ||||| _N || _R ||| _HueMask | 
| ItemPillar2 | Pole | _D ||||||| _R |||| 
| ItemRamp | Ramp item | _D ||||| _N || _R ||| _HueMask | 
| ItemRoadSign | Road sign item | _D ||||| _N || _R |||| 
| ItemSpectatorLow | Spectators, lowest LOD | _D ||||| _N || _R |||| 
| ItemSpectator | Spectators | _D ||||| _N || _R |||| 
| ItemSpringTreeBranch | Tree leaves | _D ||||| _N || _R |||| 
| ItemSupportConnector | Support connectors | _D ||||| _N || _R |||| 
| ItemSupportTube | Support tubes | _D ||||| _N || _R ||| _HueMask | 
| ItemTorchFlame | Torch flames ||| _I ||||||||| 
| ItemTrackBarrier | Barrier | _D ||||| _N || _R ||| _HueMask | 
| ItemTrackBarrier2 | Barrier | _D ||||||||||| 
| ItemTrackBarrierB | White barrier | _D ||||||||||| 
| ItemTrackBarrierC | Black barrier | _D ||||||||||| 
| ItemTreeTrunk | Tree trunks | _D ||||| _N || _R |||| 
| LightCells | Screen pixels |||||| _N || _R |||| 
| LightCells2 | Screen pixels | _D | _H || _L || _N || _R |||| 
| LightCells3 | Screen pixels | _D | _H || _L || _N || _R |||| 
| LightShape | Light shape items | _D | _H | _I | _L || _N || _R |||| 
| LightSpot | Lights | _D | _H | _I | _L || _N || _R |||| 
| LightSpot2 | Lights | _D | _H || _L || _N || _R |||| 
| LightTubeBig | Light tube items |||||||||||| 
| LightTubeRefract | Light tube items refraction ||| _I ||||||||| 
| LightTubeSmall | Light tube items |||||||||||| 
| LightTube | Light tube items | _D || _I ||| _N || _R |||| 
| OpenDirtBorders | Open dirt road borders | _D ||||||||||| 
| OpenGrassBorders | Open grass road borders | _D ||||||||||| 
| OpenIceBorders | Open ice road borders | _D ||||||||||| 
| OpenTechBorders | Open tech road borders | _D ||||| _N || _R ||| _HueMask | 
| PlatformGrass | Grass platform | _D ||||| _N || _R |||| 
| PlatformIce | Ice platform | _D | _H |||||||||| 
| PlatformTech | Tech platform | _D ||||| _N || _R |||| 
| PodiumBorder | Podium borders | _D | _H | _I | _L || _N || _R |||| 
| PodiumMedalMetal | Podium metals | _D ||||| _N || _R |||| 
| PodiumScreen155 | Podium screen (unused) ||| _I ||||||||| 
| PodiumSelfIllum | Podium numbers | _D || _I ||| _N || _R |||| 
| PodiumStepScreen | Podium steps |||||||||||| 
| Pylon | | _D ||||| _N || _R |||| 
| RaceAd6x1 | Default 64x10 sign |||||||||||| 
| RaceArchCheckpoint | Top of checkpoint arch ||| _I ||||||||| 
| RaceArchFinish | Top of finish arch ||| _I ||||||||| 
| RaceArch | Top of checkpoint and finish arches | _D | _H || _L || _N || _R |||| 
| RaceScreenStart | 3-2-1-go sign ||| _I ||||||||| 
| RaceTriggerFXCheckpoint | Checkpoint gate trigger ||| _I ||||||||| 
| RaceTriggerFXFinish | Finish gate trigger ||| _I ||||||||| 
| RaceTriggerFXMultilap | Multilap gate trigger ||| _I ||||||||| 
| RoadBump | Sausage road | _D ||||| _N || _R ||| _HueMask | 
| RoadDirt | Dirt road | _D ||||| _N || _R ||| _HueMask | 
| RoadIce | Bobsleigh | _D | _H ||||||||| _HueMask | 
| RoadTech | Tech road | _D ||||| _N || _R ||| _HueMask | 
| ScreenBack | Back of signs | _D ||||| _N || _R |||| 
| ScreenPusher | Pusher screen | _D | _H | _I | _L || _N || _R |||| 
| Show4x1 | |||||||||||| 
| SparklerEnd | Sparkler ending animation | _D ||||||||||| 
| Sparkler | Sparkler shooting animation | _D ||||||||||| 
| SpeakerFront | Front of speakers | _D ||||| _N || _R |||| 
| SpeakerSide | Side of speakers | _D ||||| _N || _R |||| 
| SpecialFXBoost2 | Super reactor boost energy ||| _I ||||||||| 
| SpecialFXBoost | Reactor boost energy ||| _I ||||||||| 
| SpecialFXCruise | Cruise control energy ||| _I ||||||||| 
| SpecialFXFragile | Fragile energy ||| _I ||||||||| 
| SpecialFXGateGameplay | Transformation gate energy ||| _I ||||||||| 
| SpecialFXNoBrake | No brakes gate energy ||| _I ||||||||| 
| SpecialFXNoEngine | Engine off gate energy ||| _I ||||||||| 
| SpecialFXNoSteering | No steering gate energy ||| _I ||||||||| 
| SpecialFXReset | Reset gate energy ||| _I ||||||||| 
| SpecialFXSlowMotion | Slow motion gate energy ||| _I ||||||||| 
| SpecialFXTurbo2 | Super turbo gate energy ||| _I ||||||||| 
| SpecialFXTurboRoulette | Roulette turbo gate energy ||| _I ||||||||| 
| SpecialFXTurbo | Turbo gate energt||| _I ||||||||| 
| SpecialSignBoost2Down | Super reactor boost down sign ||| _I ||||||||| 
| SpecialSignBoost2 | Super reactor boost up sign ||| _I ||||||||| 
| SpecialSignBoostDown | Reactor boost down sign ||| _I ||||||||| 
| SpecialSignBoost | Reactor boost up sign ||| _I ||||||||| 
| SpecialSignCruise | Cruise control sign ||| _I ||||||||| 
| SpecialSignFragile | Fragile sign ||| _I ||||||||| 
| SpecialSignNoBrake | No brakes sign ||| _I ||||||||| 
| SpecialSignNoEngine | Engine off sign ||| _I ||||||||| 
| SpecialSignNoSteering | No steering sign ||| _I ||||||||| 
| SpecialSignOff | Reverse turbo sign (unused) ||| _I ||||||||| 
| SpecialSignReset | Reset sign ||| _I ||||||||| 
| SpecialSignSlowMotion | Slow motion sing ||| _I ||||||||| 
| SpecialSignTurbo2Off | Reverse super turbo sign ||| _I ||||||||| 
| SpecialSignTurbo2 | Super turbo sign ||| _I ||||||||| 
| SpecialSignTurboRouletteOff | Reverse roulette turbo sign ||| _I ||||||||| 
| SpecialSignTurboRoulette | Roulette turbo sign ||| _I ||||||||| 
| SpecialSignTurboOff | Reverse turbo sign||| _I ||||||||| 
| SpecialSignTurbo | Turbo sign ||| _I ||||||||| 
| Speedometer | Blue lights on checkpoints and finishes | _D || _I ||| _N || _R |||| 
| Structure | Pillars | _D ||||| _N || _R ||| _HueMask | 
| StructureInWorld | Pillars in vistas | _D ||||| _N || _R ||| _HueMask | 
| StructureTruss | Truss items | _D ||||| _N || _R ||| _HueMask | 
| TechnicsSpecials | Effect block details | _D ||||| _N || _R |||| 
| TechnicsStepLow | Stand steps, lowest LOD |||||| _N |||||| 
| TechnicsStep | Stand steps | _D ||||| _N || _R ||| _HueMask | 
| TechnicsTrims | Details | _D ||||| _N || _R ||| _HueMask | 
| Technics | Details | _D ||||| _N || _R ||| _HueMask | 
| ThemeDesertBarrier | Desert barrier | _D ||||| _N || _R ||| _HueMask | 
| ThemeRallyBarrier | Rally barrier | _D ||||| _N || _R |||| 
| ThemeRallyCastleBorders | Castle borders | _D ||||| _N || _R |||| 
| ThemeRallyCastleRoof | Castle roof | _D ||||| _N || _R ||| _HueMask | 
| ThemeRallyCastleWall | Castle walls | _D ||||| _N || _R |||| 
| ThemeSnowRoadBorder | Wood road border | _D ||||| _N || _R ||| _HueMask | 
| ThemeSnowRoad | Wood road | _D ||||| _N || _R |||| 
| ThemeSnowTempleDetails | Temple details | _D ||||| _N || _R ||| _HueMask | 
| ThemeSnowTempleFloor | Temple floor | _D |||||||||| _HueMask | 
| ThemeSnowTempleLamp | Temple lamp | _D | _H | _I | _L || _N || _R |||| 
| ThemeSnowTempleTransparent | Temple transparent parts | _D ||||| _N || _R |||| 
| TrackBordersInWorld | Walls and edges of roads in vistas | _D ||||| _N || _R ||| _HueMask | 
| TrackBorders | Walls and edges of roads | _D | _H | _I | _L || _N || _R ||| _HueMask | 
| TrackWallClipsInWorld | Black roads and platforms in vistas | _D ||||| _N || _R ||| _HueMask | 
| TrackWallClips | Black roads and platforms | _D ||||| _N || _R ||| _HueMask | 
| TrackWallPxzInWorld | Wooden pillars in vistas | _D ||||| _N || _R |||| 
| TrackWallPxz | Wooden pillars | _D ||||| _N || _R ||| _HueMask | 
| TrackWallPy | |||||||||| _X2 || 
| TrackWall | Wooden pillar stripes | _D ||||| _N || _R |||| 
| TriggerFXBoost2 | Super reactor boost gate trigger ||| _I ||||||||| 
| TriggerFXBoost | Reacot boost gate trigger ||| _I ||||||||| 
| TriggerFXCruise | Cruise control gate trigger ||| _I ||||||||| 
| TriggerFXFragile | Fragile gate trigger ||| _I ||||||||| 
| TriggerFXGateGameplay | Transformation gate trigger ||| _I ||||||||| 
| TriggerFXNoBrake | No brakes gate trigger ||| _I ||||||||| 
| TriggerFXNoEngine | Engine off gate trigger ||| _I ||||||||| 
| TriggerFXNoSteering | No steering gate trigger ||| _I ||||||||| 
| TriggerFXReset | Reset gate trigger ||| _I ||||||||| 
| TriggerFXSlowMotion | Slow motion gate trigger ||| _I ||||||||| 
| TriggerFXTurbo2 | Super turbo gate trigger ||| _I ||||||||| 
| TriggerFXTurboRoulette | Roulette turbo gate trigger ||| _I ||||||||| 
| TriggerFXTurbo | Turbo gate trigger ||| _I ||||||||| 
| Underwater | Pool walls | _D ||||| _N || _R |||| 
| Water_SxSySz | Water surface |||||||||||| 
| WaterBorders | Pool walls | _D ||||| _N || _R |||| 
| WaterFog | Unused |||||||||||| 
| Waterground | Pool floor | _D ||||| _N || _R |||| 
| WaterTransmittance.ImageGen.Gbx | Water colour |||||||||||| 


Notes:

- All files are .dds unless mentioned otherwise.
- In the case of `ItemObstacle_D`, `ItemObstaclePusher_D` and `ItemObstacleLight_I`, A second suffix exists
- Add a second suffix depending on type of obstacle:
    - Pink: `_DiscontinuousLevel0`
    - Violet: `_DiscontinuousLevel1`
    - Indigo: `_DiscontinuousLevel2`
    - Yellow: `_Level0`
    - Orange: `_Level1`
    - Red: `_Level2`
- ItemTrackBarrier_D uses `_HueMask`. ItemTrackBarrierB_D and C_D use `_HueMask2`.
- SpecialFXTurboRoulette_LightColor exists.
- LightTubeBig and LightTubeSmall contain a _G.tga texture.
- Structure contains a _D.tga HueMask.
- TrackBorders _I is a .tga file rather than a .dds file. 


## 📁 Moods
| **Name** | **Used For** |
|:-:|:-:|
| AmbCube
| AmbCubeP
| Clouds | Cloud shadows moving on top of the map
| EnvCubicHdr | Cubemap reflections (DDS BC6U)
| Fresnel
| IconMoodSmall
| Mood.MoodSetting.xml | Determines parameters for the mood lighting. For more info see [this documentation page](https://doc.maniaplanet.com/title-pack/mood)
| SkyClouds | Cloud textures
| SkyColor | Skybox texture (DDS BC6U)


## Car Effects

| **Name** | **Used For** |
|:-:|:-:|
| CarAsphaltMarks | Skidmarks on road
| CarDirtMarks | Skidmarks on dirt
| CarDirtSmoke | Smoke while skidding on dirt
| CarGrassMarks | Skidmarks on grass
| EnvLayerDirt_D | Color of dirt on the car

Note: 
TBC

Last updated on 5 August 2026.
Last edited by Zai

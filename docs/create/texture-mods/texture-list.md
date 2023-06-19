# Texture List

This is a living document - if you see something inaccurate/missing, feel free to contribute.

## Suffixes

| **Suffix** | **Format** | **Filetype** | **Purpose** | **Notes**
| :-: | :-: | :-: | :-: | :-: |
| \_D | Diffuse | DDS (BC1)<br>DDS (BC3 if transparent) | Base image/texture |
| \_H | | DDS (BC1) | Height | Grey `(128,128,128)` is level<br>Black `(0,0,0)` lowers elevations<br>White `(255,255,255)` raises elevation
| \_I | Ilium | | InsideColor<br>Colorization of things behind glass | Multiplication before applying glass layers
| \_L | | | Color of lightbulbs/LEDs | Displaced by `_H`
| \_M | | DDS (BC1) | Mask (black/white) | Color is determined by `DecalPaint_D`
| \_N | Normal | DDS (BC5) | Texture that stores a direction at each pixel
| \_O |
| \_R | Roughness | DDS (BC5) | Roughness (matte/shiny)<br>Metallic | Can be kept as greyscale (BC1) if not used.
| \_T |
| \_X2 | | DDS (BC1) | Large overlay for color values | Upscaled texture for `CustomMaterial` projection

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
| Ad1x1Screen | "Default" 1x1 Sign |
| Ad2x1Screen | "Default" 2x1 Sign |
| Ad4x1Screen | "Default" 4x1 Sign |
| AdScreenOff | "Off" Sign |
| Chrono |  | \_D | \_H | \_I | \_L | | \_N | | \_R |
| ChronoCheckpoint |  | | | \_I |
| ChronoFinish |  | | | \_I |
| CustomBricks |  | \_D | | | | | \_N | | \_R |
| CustomConcrete |  | \_D | | | | | \_N | | \_R | | \_X2 |
| CustomDirt |  | \_D | | | | | \_N | | \_R |
| CustomGrass |  | \_D | | | | | \_N | | \_R |
| CustomIce |  | \_D | | | | | \_N | | \_R |
| CustomMetal |  | \_D | | | | | \_N | | \_R |
| CustomMetalPainted |  | \_D | | | | | \_N | | \_R |
| CustomModColorize |  | \_D | | | | | \_N | | \_R | | | \_HueShiftMask |
| CustomModDecal |  | \_D | | | | | \_N | | \_R |
| CustomModOpaque |  | \_D | | | | | \_N | | \_R |
| CustomModSelfIllum |  | \_D | \_H | \_I | \_L | | \_N | | \_R |
| CustomModTrans |  | \_D | | | | | \_N | | \_R |
| CustomPlastic |  | \_D | | | | | \_N | | \_R |
| CustomRock |  | \_D | | | | | \_N | | \_R |
| CustomRockPxz |  | \_D | | | | | \_N | | \_R |
| CustomRockPy |  | | | | | | | | | | \_X2 |
| CustomRoughWood |  | \_D | | | | | \_N | | \_R |
| CustomSand |  | \_D | | | | | \_N | | \_R |
| CustomSnow |  | \_D | | | | | \_N | | \_R | | \_X2 |
| DecalCurbs |  | \_D | | | | | \_N | | \_R |
| DecalLogo4x1 |  | |  |  |  | \_M |
| DecalLogo8x1 |  | |  |  |  | \_M |
| DecalMarks |  | \_D | | | | | \_N | | \_R |
| DecalMarksItems |  | \_D | | | | | \_N | | \_R |
| DecalMarksRamp |  | \_D | | | | | \_N | | \_R |
| DecalMarksStart |  | \_D | | | | | \_N | | \_R |
| DecalObstaclePusher |  | \_D | | | | | \_N | | \_R |
| DecalObstacleTube |  | \_D | | | | | \_N | | \_R |
| DecalObstacleTurnstile |  | | | | | | \_N | | \_R |
| DecalObstacleTurnstileLeft |  | \_D |
| DecalObstacleTurnstileRight |  | \_D |
| DecalPaint |  | \_D | | | | | \_N | | \_R |
| DecalPaint2 |  | \_D |
| DecalPlatform |  | \_D | | | | | \_N ^1^ | | \_R |
| DecalPlatformDirt |  | \_D |
| DecalPlatformGrass |  | \_D |
| DecalPlatformIce |  | \_D |
| DecalPlatformPlastic |  | \_D |
| DecalSpecial |  | | | | | | \_N | | \_R |
| DecalSpecialBoost |  | \_D |
| DecalSpecialBoost2 |  | \_D |
| DecalSpecialCruise |  | \_D |
| DecalSpecialFragile |  | \_D |
| DecalSpecialNoBrake |  | \_D |
| DecalSpecialNoEngine |  | \_D |
| DecalSpecialNoSteering |  | \_D |
| DecalSpecialReset |  | \_D |
| DecalSpecialSlowMotion |  | \_D |
| DecalSpecialTurbo |  | \_D |
| DecalSpecialTurbo2 |  | \_D |
| DecalSpecialTurboRoulette |  | \_D |
| DecalSponsor1x1BigA |  | \_D | | | | | \_N | | \_R |
| DecalSponsor4x1A |  | |  |  |  | \_M |
| DecalSponsor4x1B |  | |  |  |  | \_M |
| DecalSponsor4x1C |  | |  |  |  | \_M |
| DecalSponsor4x1D |  | |  |  |  | \_M |
| DecoHill |  | \_D | | | | | \_N | | \_R |
| DecoHill2 |  | \_D |
| DecoHillDirt |  | \_D | | | | | \_N | | \_R |
| DecoHillDirt2 |  | \_D |
| DecoHillDirtPy |  | \_D | | | | | \_N | | \_R |
| DecoHillIce |  | \_D | | | | | \_N | | \_R |
| DecoHillIce2 |  | \_D |
| DecoHillIcePy |  | \_D | | | | | \_N | | \_R |
| DecoHillPy |  | \_D | | | | | \_N | | \_R |
| DirtPy |  | \_D | | | | | \_N | | \_R | | \_X2 |
| GlassWaterWall |  | | | | | | \_N | \_O | \_R | \_T |
| Grass |  | \_D | | | | | \_N | | \_R | | \_X2 |
| GrassFence |  | \_D |
| IceMarks |  | | | | | \_M | \_N | | \_R |
| IcePy |  | | | | | | \_N | | \_R |
| ItemAd1x1ScreenSmall |  | | | \_I |
| ItemAd1x1ScreenSmallB |  | | | \_I |
| ItemAd1x1ScreenSmallC |  | | | \_I |
| ItemAd1x1ScreenSmallWrongWay |  | | | \_I |
| ItemBase |  | \_D | | | | | \_N | | \_R |
| ItemBorder |  | \_D | | | | | \_N | | \_R |
| ItemCactus |  | \_D | | | | | \_N | | \_R |
| ItemCherryTreeBranch |  | \_D | | | | | \_N | | \_R |
| ItemCherryTreePetals |  | \_D | | | | | \_N |
| ItemCypressBranch |  | \_D | | | | | \_N | | \_R |
| ItemFallTreeBranch |  | \_D |
| ItemFallTreePetals |  | \_D | | | | | \_N |
| ItemFirBranch |  | \_D | | | | | \_N | | \_R |
| ItemFirSnowBranch |  | \_D | | | | | \_N | | \_R |
| ItemFlag |  | \_D | | | | | | | \_R |
| ItemInflatableFloor |  | \_D | | | | | \_N | | \_R |
| ItemInflatableMat |  | \_D | | | | | \_N | | \_R |
| ItemInflatableTube |  | \_D | | | | | \_N | | \_R |
| ItemLamp |  | \_D | \_H | \_I | \_L | | \_N | | \_R |
| ItemLampB |  | | | \_I |
| ItemLampC |  | | | \_I |
| ItemObstacle |  | \_D ^2^ | | | | | \_N | | \_R |
| ItemObstacleLight |  | \_D | \_H | \_I ^2^ | \_L | | \_N | | \_R |
| ItemObstaclePusher |  | \_D ^2^ | | | | | \_N | | \_R |
| ItemPalmTreeBark |  | \_D | | | | | \_N | | \_R |
| ItemPalmTreeBranch |  | \_D | | | | | \_N | | \_R |
| ItemPillar |  | \_D | | | | | \_N | | \_R |
| ItemRamp |  | \_D | | | | | \_N | | \_R |
| ItemRoadSign |  | \_D | | | | | \_N | | \_R |
| ItemSpectator |  | \_D | | | | | \_N | | \_R |
| ItemSpringTreeBranch |  | \_D | | | | | \_N | | \_R |
| ItemSupportConnector |  | \_D | | | | | \_N | | \_R |
| ItemSupportTube |  | \_D | | | | | \_N | | \_R |
| ItemTrackBarrier |  | \_D ^3^ | | | | | \_N | | \_R |
| ItemTrackBarrierB |  | \_D ^3^ |
| ItemTrackBarrierC |  | \_D ^3^ |
| ItemTreeTrunk |  | \_D | | | | | \_N | | \_R |
| LightCells |  | | | | | | \_N | | \_R |
| LightCells2 |  | \_D | \_H | | \_L | | \_N | | \_R |
| LightCells3 |  | \_D | \_H | | \_L | | \_N | | \_R |
| LightSpot |  | \_D | \_H | \_I | \_L | | \_N | | \_R |
| LightSpot2 |  | \_D | \_H | | \_L | | \_N | | \_R |
| OpenDirtBorders |  | \_D |
| OpenGrassBorders |  | \_D |
| OpenIceBorders |  | \_D |
| OpenTechBorders |  | \_D | | | | | \_N | | \_R |
| PlatformGrass |  | \_D | | | | | \_N | | \_R |
| PlatformIce |  | \_D | \_H |
| PlatformTech |  | \_D | | | | | \_N | | \_R |
| Pylon |  | \_D | | | | | \_N | | \_R |
| RaceAd6x1 |  |
| RaceArch |  | \_D | \_H | | \_L | | \_N | | \_R |
| RaceArchCheckpoint |  | | | \_I |
| RaceArchFinish |  | | | \_I |
| RaceScreenStart |  | | | \_I |
| RoadBump |  | \_D | | | | | \_N | | \_R |
| RoadDirt |  | \_D | | | | | \_N | | \_R |
| RoadIce |  | \_D | \_H |
| RoadTech |  | \_D | | | | | \_N | | \_R |
| ScreenBack |  | \_D | | | | | \_N | | \_R |
| ScreenPusher |  | \_D | \_H | \_I | \_L ^2^ | | \_N | | \_R |
| SpecialFXBoost |  | | | \_I |
| SpecialFXBoost2 |  | | | \_I |
| SpecialFXCruise |  | | | \_I |
| SpecialFXFragile |  | | | \_I |
| SpecialFXNoBrake |  | | | \_I |
| SpecialFXNoEngine |  | | | \_I |
| SpecialFXNoSteering |  | | | \_I |
| SpecialFXReset |  | | | \_I |
| SpecialFXSlowMotion |  | | | \_I |
| SpecialFXTurbo |  | | | \_I |
| SpecialFXTurbo2 |  | | | \_I |
| SpecialFXTurboRoulette ^4^ |  | | | \_I |
| SpecialSignBoost |  | | | \_I |
| SpecialSignBoost2 |  | | | \_I |
| SpecialSignBoost2Down |  | | | \_I |
| SpecialSignBoostDown |  | | | \_I |
| SpecialSignCruise |  | | | \_I |
| SpecialSignFragile |  | | | \_I |
| SpecialSignNoBrake |  | | | \_I |
| SpecialSignNoEngine |  | | | \_I |
| SpecialSignNoSteering |  | | | \_I |
| SpecialSignOff |  | | | \_I |
| SpecialSignReset |  | | | \_I |
| SpecialSignSlowMotion |  | | | \_I |
| SpecialSignTurbo |  | | | \_I |
| SpecialSignTurbo2 |  | | | \_I |
| SpecialSignTurboRoulette |  | | | \_I |
| Speedometer |  | \_D | | \_I | | | \_N | | \_R |
| Structure |  | \_D | | | | | \_N | | \_R |
| Technics |  | \_D | | | | | \_N | | \_R |
| TechnicsSpecials |  | \_D | | | | | \_N | | \_R |
| TechnicsTrims |  | \_D | | | | | \_N | | \_R |
| TrackBorders |  | \_D | \_H | \_I | \_L | | \_N | | \_R |
| TrackWall |  | \_D | | | | | \_N | | \_R |
| TrackWallClips |  | \_D | | | | | \_N | | \_R |
| TrackWallPxz |  | \_D | | | | | \_N | | \_R |
| TrackWallPy |  | | | | | | | | | | \_X2 |
| Underwater |  | \_D | | | | | \_N | | \_R |
| WarpGlass |  | \_D | | | | | \_N |
| Water_SxSySz |  |
| WaterBorders |  | \_D | | | | | \_N | | \_R |
| WaterFog |  |
| Waterground |  | \_D | | | | | \_N | | \_R |

Notes:

- DecalPlatform has two `_N` textures, one `DDS` and one `TGA`.
- Add a second suffix depending on type of obstacle:
    - Pink: `_DiscontinuousLevel0`
    - Violet: `_DiscontinuousLevel1`
    - Indigo: `_DiscontinuousLevel2`
    - Yellow: `_Level0`
    - Orange: `_Level1`
    - Red: `_Level2`
- ItemTrackBarrier_D uses `_HueMask`. ItemTrackBarrierB_D and C_D use `_HueMask2`.
- SpecialFXTurboRoulette_LightColor exists.

<!-- TODO
## 📁 Moods
| **Name** | **Used For** |
|:-:|:-:|
-->

## Car Effects

| **Name** | **Used For** |
|:-:|:-:|
| AirBubble_Medium |
| AirBubble_Small
| AnimBoost_D
| AnimBoost_Turbo_D
| AnimBoost_Turbo2_D
| AnimBoost_TurboRoulette2_D
| AnimBoost_TurboRoulette3_D
| AnimFire_D
| AnimNitro_D
| AsphaltMarks
| AsphaltSmoke
| CarLights
| CommonCarDetails
| CommonCarShadowProj
| CommonCarWheelShadowProj
| DirtGravels
| DirtMarks
| DirtSmoke
| DirtSmokeHovering
| GrassMarkGround
| HeadLightsProj
| IceMarks_A
| IceMarks_N
| IceMarks_RoughMetal
| Sand
| SandMarks
| SandSmoke
| SmokeWLightmap_D
| SmokeWLightmap_LM
| Snow
| SnowMarks
| SnowSmoke
| Sparkle
| StadiumCarIcon
| StemFoamFxd
| VehicleFXFlare
| WaterSplash
| WaterWake_N
| WetWheelsMarks
| WetWheelsMarks_RM

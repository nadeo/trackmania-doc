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
|Ad1x1Screen|"Default" 1x1 Sign|||||||||||
|Ad2x1Screen|"Default" 2x1 Sign|||||||||||
|Ad4x1Screen|"Default" 4x1 Sign|||||||||||
|AdScreenOff|"Off" Sign|||||||||||
|Canopy|Canopy Pattern|_D|||||_N||_R|||_D
|CanopyGlass|Canopy Glass|_D|||||_N||_R|||_D
|CanopyStructure|Canopy Pattern Edges|_D|_H|_I|_L||_N||_R|||_D, _L
|Chrono||_D|_H|_I|_L||_N||_R|||
|ChronoCheckpoint||||_I||||||||
|ChronoFinish||||_I||||||||
|CustomBricks||_D|||||_N||_R|||
|CustomConcrete||_D|||||_N||_R||_X2|
|CustomDirt||_D|||||_N||_R|||
|CustomGrass||_D|||||_N||_R||_X2|
|CustomIce||_D|||||_N||_R|||
|CustomMetal||_D|||||_N||_R|||
|CustomMetalPainted||_D|||||_N||_R|||
|CustomModAddSelfIllum||||_I||||||||
|CustomModAddSelfIllum2||||_I||||||||
|CustomModColorize||_D|||||_N||_R|||_D
|CustomModColorize2||_D|||||_N||_R|||_D
|CustomModDecal||_D|||||_N||_R|||
|CustomModDecal2||_D|||||_N||_R|||
|CustomModOpaque||_D|||||_N||_R|||
|CustomModOpaque2||_D|||||_N||_R|||
|CustomModSelfIllum||_D|_H|_I|_L||_N||_R|||
|CustomModSelfIllum2||_D|_H|_I|_L||_N||_R|||
|CustomModSelfIllumSimple||_D||_I|||_N||_R|||
|CustomModSelfIllumSimple2||_D||_I|||_N||_R|||
|CustomModTrans||_D|||||_N||_R|||
|CustomModTrans2||_D|||||_N||_R|||
|CustomPlastic||_D|||||_N||_R|||
|CustomPlasticShiny||_D|||||_N||_R|||
|CustomRock||_D|||||_N||_R|||
|CustomRockPxz||_D|||||_N||_R|||
|CustomRockPy|||||||||||_X2|
|CustomRoughWood||_D|||||_N||_R|||
|CustomSand||_D|||||_N||_R|||
|CustomSnow||_D|||||_N||_R||_X2|
|DecalCurbs||_D|||||_N||_R|||_D
|DecalGateGameplay||_D|||||_N||_R|||
|DecalLogo4x1||||||_M||||||
|DecalLogo8x1||||||_M||||||
|DecalMarks||_D|||||_N||_R|||
|DecalMarksItems||_D|||||_N||_R|||_D
|DecalMarksRamp||_D|||||_N||_R|||
|DecalMarksStart||_D|||||_N||_R|||_D
|DecalObstaclePusher||_D|||||_N||_R|||
|DecalObstacleTube||_D|||||_N||_R|||
|DecalObstacleTurnstile|||||||_N||_R|||
|DecalObstacleTurnstileLeft||_D||||||||||
|DecalObstacleTurnstileRight||_D||||||||||
|DecalPaint||_D|||||_N||_R|||_D
|DecalPaint2||_D||||||||||
|DecalPlatform||_D|||||_N||_R|||_D
|DecalPlatformDirt||_D||||||||||
|DecalPlatformGrass||_D||||||||||
|DecalPlatformIce||_D||||||||||
|DecalPlatformPlastic||_D||||||||||
|DecalSpecial|||||||_N||_R|||
|DecalSpecialBoost||_D||||||||||
|DecalSpecialBoost2||_D||||||||||
|DecalSpecialCruise||_D||||||||||
|DecalSpecialFragile||_D||||||||||
|DecalSpecialMarks||_D|||||_N||_R|||
|DecalSpecialNoBrake||_D||||||||||
|DecalSpecialNoEngine||_D||||||||||
|DecalSpecialNoSteering||_D||||||||||
|DecalSpecialReset||_D||||||||||
|DecalSpecialSlowMotion||_D||||||||||
|DecalSpecialTurbo||_D||||||||||
|DecalSpecialTurbo2||_D||||||||||
|DecalSpecialTurboRoulette||_D||||||||||
|DecalSponsor1x1BigA||_D|||||_N||_R|||
|DecalSponsor4x1A||||||_M||||||
|DecalSponsor4x1B||||||_M||||||
|DecalSponsor4x1C||||||_M||||||
|DecalSponsor4x1D||||||_M||||||
|DecoCliffBase||_D|||||_N||_R|||_D|
|DecoCliffBaseDirt||_D||||||||||
|DecoCliffBaseIce||_D||||||||||
|DecoCliffIcePxz||_D|||||_N||_R|||
|DecoCliffPxz||_D|||||_N||_R|||
|DecoHill||_D|||||_N||_R|||
|DecoHill2||_D||||||||||
|DecoHillDirt||_D|||||_N||_R|||
|DecoHillDirt2||_D||||||||||
|DecoHillDirtPy||_D|||||_N||_R||_X2||
|DecoHillIce||_D|||||_N||_R|||
|DecoHillIce2||_D||||||||||
|DecoHillIcePy||_D|||||_N||_R||_X2|
|DecoHillPy||_D|||||_N||_R||_X2|
|DecoTechnics||_D|||||_N||_R|||
|DirtPy||_D|||||_N||_R||_X2|_D
|FoggerSmoke||||||||||||
|GateGameplayScreen||||||||||||
|GlassWaterWall|||||||_N|_O|_R|_T||
|GlossyFloor||_D|||||_N||_R|||
|Grass||_D|||||_N||_R||_X2|
|GrassFence||_D||||||||||
|IceMarks||||||_M|_N||_R|||
|IcePy|||||||_N||_R|||
|ItemAd1x1ScreenSmall||||_I||||||||
|ItemAd1x1ScreenSmallB||||_I||||||||
|ItemAd1x1ScreenSmallC||||_I||||||||
|ItemAd1x1ScreenSmallWrongWay||||_I||||||||
|ItemBase||_D|||||_N||_R|||
|ItemBorder||_D|||||_N||_R|||
|ItemCactus||_D|||||_N||_R|||
|ItemCherryTreeBranch||_D|||||_N||_R|||
|ItemCherryTreePetals||_D|||||_N|||||
|ItemCypressBranch||_D|||||_N||_R|||
|ItemFallTreeBranch||_D||||||||||
|ItemFallTreePetals||_D|||||_N|||||
|ItemFirBranch||_D|||||_N||_R|||
|ItemFirSnowBranch||_D|||||_N||_R|||
|ItemFlag||_D|||||||_R|||_D
|ItemFrozenTreeBranch||_D||||||||||
|ItemInflatableFloor||_D|||||_N||_R|||_D
|ItemInflatableMat||_D|||||_N||_R|||_D
|ItemInflatableTube||_D|||||_N||_R|||_D
|ItemLamp||_D|_H|_I|_L||_N||_R|||
|ItemLampB||||_I||||||||
|ItemLampC||||_I||||||||
|ItemObstacle||_D|||||_N||_R|||
|ItemObstacleLight||_D|_H|_I|_L||_N||_R|||
|ItemObstaclePusher||_D|||||_N||_R|||
|ItemPalmTreeBark||_D|||||_N||_R|||
|ItemPalmTreeBranch||_D|||||_N||_R|||
|ItemPillar||_D|||||_N||_R|||_D
|ItemPillar2||_D|||||||_R|||
|ItemRamp||_D|||||_N||_R|||_D
|ItemRoadSign||_D|||||_N||_R|||
|ItemSpectator||_D|||||_N||_R|||
|ItemSpectatorLow||_D|||||_N||_R|||
|ItemSpringTreeBranch||_D|||||_N||_R|||
|ItemSupportConnector||_D|||||_N||_R|||
|ItemSupportTube||_D|||||_N||_R|||_D
|ItemTorchFlame||||_I||||||||
|ItemTrackBarrier||_D|||||_N||_R|||_D
|ItemTrackBarrier2||_D||||||||||
|ItemTrackBarrierB||_D||||||||||
|ItemTrackBarrierC||_D||||||||||
|ItemTreeTrunk||_D|||||_N||_R|||
|LightCells|||||||_N||_R|||
|LightCells2||_D|_H||_L||_N||_R|||
|LightCells3||_D|_H||_L||_N||_R|||
|LightShape||_D|_H|_I|_L||_N||_R|||
|LightSpot||_D|_H|_I|_L||_N||_R|||
|LightSpot2||_D|_H||_L||_N||_R|||
|LightTube||_D||_I|||_N||_R|||
|LightTubeBig||||||||||||
|LightTubeRefract||||_I||||||||
|LightTubeSmall||||||||||||
|OpenDirtBorders||_D||||||||||
|OpenGrassBorders||_D||||||||||
|OpenIceBorders||_D||||||||||
|OpenTechBorders||_D|||||_N||_R|||_D
|output.csv||||||||||||
|PlatformGrass||_D|||||_N||_R|||
|PlatformIce||_D|_H|||||||||
|PlatformTech||_D|||||_N||_R|||
|PodiumBorder||_D|_H|_I|_L||_N||_R|||
|PodiumMedalMetal||_D|||||_N||_R|||
|PodiumScreen155||||_I||||||||
|PodiumScreen16x9||||_I||||||||
|PodiumSelfIllum||_D||_I|||_N||_R|||
|PodiumStepScreen||||||||||||
|Pylon||_D|||||_N||_R|||
|RaceAd6x1||||||||||||
|RaceArch||_D|_H||_L||_N||_R|||
|RaceArchCheckpoint||||_I||||||||
|RaceArchFinish||||_I||||||||
|RaceScreenStart||||_I||||||||
|RaceTriggerFXCheckpoint||||_I||||||||
|RaceTriggerFXFinish||||_I||||||||
|RaceTriggerFXMultilap||||_I||||||||
|RoadBump||_D|||||_N||_R|||_D
|RoadDirt||_D|||||_N||_R|||_D
|RoadIce||_D|_H|||||||||_D
|RoadTech||_D|||||_N||_R|||_D
|ScreenBack||_D|||||_N||_R|||
|ScreenPusher||_D|_H|_I|_L||_N||_R|||
|Show4x1||||||||||||
|Sparkler||_D||||||||||
|SparklerEnd||_D||||||||||
|SpeakerFront||_D|||||_N||_R|||
|SpeakerSide||_D|||||_N||_R|||
|SpecialFXBoost||||_I||||||||
|SpecialFXBoost2||||_I||||||||
|SpecialFXCruise||||_I||||||||
|SpecialFXFragile||||_I||||||||
|SpecialFXGateGameplay||||_I||||||||
|SpecialFXNoBrake||||_I||||||||
|SpecialFXNoEngine||||_I||||||||
|SpecialFXNoSteering||||_I||||||||
|SpecialFXReset||||_I||||||||
|SpecialFXSlowMotion||||_I||||||||
|SpecialFXTurbo||||_I||||||||
|SpecialFXTurbo2||||_I||||||||
|SpecialFXTurboRoulette||||_I||||||||
|SpecialSignBoost||||_I||||||||
|SpecialSignBoost2||||_I||||||||
|SpecialSignBoost2Down||||_I||||||||
|SpecialSignBoostDown||||_I||||||||
|SpecialSignCruise||||_I||||||||
|SpecialSignFragile||||_I||||||||
|SpecialSignNoBrake||||_I||||||||
|SpecialSignNoEngine||||_I||||||||
|SpecialSignNoSteering||||_I||||||||
|SpecialSignOff||||_I||||||||
|SpecialSignReset||||_I||||||||
|SpecialSignSlowMotion||||_I||||||||
|SpecialSignTurbo||||_I||||||||
|SpecialSignTurbo2||||_I||||||||
|SpecialSignTurbo2Off||||_I||||||||
|SpecialSignTurboOff||||_I||||||||
|SpecialSignTurboRoulette||||_I||||||||
|SpecialSignTurboRouletteOff||||_I||||||||
|Speedometer||_D||_I|||_N||_R|||
|Structure||_D|||||_N||_R|||
|Technics||_D|||||_N||_R|||_D
|TechnicsSpecials||_D|||||_N||_R|||
|TechnicsStep||_D|||||_N||_R|||_D
|TechnicsStepLow|||||||_N|||||
|TechnicsTrims||_D|||||_N||_R|||
|ThemeRallyBarrier||_D|||||_N||_R|||
|ThemeRallyCastleBorders||_D|||||_N||_R|||
|ThemeRallyCastleRoof||_D|||||_N||_R|||_D
|ThemeRallyCastleWall||_D|||||_N||_R|||
|ThemeSnowRoad||_D|||||_N||_R|||
|ThemeSnowRoadBorder||_D|||||_N||_R|||_D
|ThemeSnowTempleDetails||_D|||||_N||_R|||_D
|ThemeSnowTempleFloor||_D||||||||||_D
|ThemeSnowTempleLamp||_D|_H|_I|_L||_N||_R|||
|ThemeSnowTempleTransparent||_D|||||_N||_R|||
|TrackBorders||_D|_H||_L||_N||_R|||_D, _L
|TrackWall||_D|||||_N||_R|||
|TrackWallClips||_D|||||_N||_R|||_D
|TrackWallPxz||_D|||||_N||_R|||_D
|TrackWallPy|||||||||||_X2|
|TriggerFXBoost||||_I||||||||
|TriggerFXBoost2||||_I||||||||
|TriggerFXCruise||||_I||||||||
|TriggerFXFragile||||_I||||||||
|TriggerFXGateGameplay||||_I||||||||
|TriggerFXNoBrake||||_I||||||||
|TriggerFXNoEngine||||_I||||||||
|TriggerFXNoSteering||||_I||||||||
|TriggerFXReset||||_I||||||||
|TriggerFXSlowMotion||||_I||||||||
|TriggerFXTurbo||||_I||||||||
|TriggerFXTurbo2||||_I||||||||
|TriggerFXTurboRoulette||||_I||||||||
|Underwater||_D|||||_N||_R|||
|Water||||||||||||
|WaterBorders||_D|||||_N||_R|||
|WaterFog.tga||||||||||||
|Waterground||_D|||||_N||_R|||
|WaterTransmittance.ImageGen.Gbx||||||||||||

Notes:

- Add a second suffix depending on type of obstacle:
    - Pink: `_DiscontinuousLevel0`
    - Violet: `_DiscontinuousLevel1`
    - Indigo: `_DiscontinuousLevel2`
    - Yellow: `_Level0`
    - Orange: `_Level1`
    - Red: `_Level2`
- In the case of `ItemObstacle_D`, `ItemObstaclePusher_D` and `ItemObstacleLight_I`, A second suffix exists
- ItemTrackBarrier_D uses `_HueMask`. ItemTrackBarrierB_D and C_D use `_HueMask2`.
- SpecialFXTurboRoulette_LightColor exists.
- DecalGateGameplay has Desert.dds, Rally.dds and Snow.dds variants for the snow and rally car respectively.

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

Last updated on the 24th of May 2024 (Desert Update).

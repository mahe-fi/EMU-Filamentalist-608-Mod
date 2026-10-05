# EMU Filamentalist – 608 bearing mod

> [!IMPORTANT]
> **This is an unofficial mod for [EMU – Expandable Multi-material Unit](https://github.com/DW-Tas/EMU)** by DW-Tas and igiannakas.
> All parts here are **derived from the original EMU models** in that repository. Only the parts that had to change for this mod are included. Everything else comes from the original project.
> Please refer to the [original repository](https://github.com/DW-Tas/EMU) for the full documentation, BOM, assembly manuals and videos, and the printed parts configurator ([emu.dwtas.net](https://emu.dwtas.net)).

The stock EMU Filamentalist lane uses five **688** bearings (8×16×5 mm). This mod replaces them with five **608** bearings (8×22×7 mm). 608s are the common skateboard bearing: cheap, widely available and more robust.

## What changes

Per lane, all five 688 bearings are replaced with 608s:

| Location | Bearings | How it was adapted |
|---|---|---|
| Wheel (rim roller) axle | 2 | The inner faces of the bearings stay where they were, so the gap between the two bearings, the one-way bearing, the drive roller (CDR) and the stepper body are unchanged. Each bearing grows 2 mm outward. |
| Idler roller axle | 2 | Same as the wheel axle. The idler roller axle is unchanged. |
| Filamentalist tensioner arm | 1 | The bearing centre moved 3 mm straight away from the CDR, so the pinch gap against the TPU ring is unchanged. |

To make room while keeping the **overall width of the lane unchanged**:

- **Chassis L/R:** new bearing bosses and crush-rib pockets for 22 mm bearings. The four chassis-to-stepper M3 countersunk screws next to the idler bearings moved 2.5 mm outward, because the original screw heads would hit the new bores.
- **Stepper main body:** the four matching heat-set insert pockets moved 2.5 mm outward. The body outline around the idler is extended to match the enlarged chassis plates.
- **Rim rollers and idler rollers:** 2 mm narrower each, taken off the bearing side, so the outer faces of the lane stay in the same place.
- **Tensioner arm:** wider (7 mm) bearing slot, open straight up so the bearing drops in. The flat top face is raised 3 mm for enough wall around the countersunk axle screw.
- **Tensioner mount:** the nose next to the bearing is trimmed about 2 mm, so the larger bearing clears it over the full arm travel.
- **Bushing:** lengthened from 5 mm to 7 mm.
- **LED holder:** raised 4.5 mm to clear the taller tensioner arm, with an added spacer strip underneath that seats on the chassis/stepper as before. The Neopixel PCB moves up with it.

## Hardware changes vs. stock EMU (per lane)

| Stock | This mod | Qty | Notes |
|---|---|---|---|
| 688 bearing (8×16×5 mm) | **608 bearing (8×22×7 mm)** | 5 | Use 2RS/ZZ shielded bearings |
| M3×8 FHCS (LED holder to stepper body) | **M3×12 FHCS** | 1 | The LED holder sits 4.5 mm higher |
| Rim roller rubber band, 23 mm wide | **Rubber band, 21 mm wide** | 2 | See below |

> [!IMPORTANT]
> **A narrower rubber band is needed on the rim rollers.** The band seat on the rim rollers is 2 mm narrower than stock: **21 mm instead of 23 mm**. Inner diameter (~63 mm) and thickness (~1.5 mm) are unchanged. Use a band of the same size as stock, but 21 mm wide, or trim a stock band to 21 mm.

All other hardware is the same as stock EMU. Refer to the original [BOM and sourcing guide](https://github.com/DW-Tas/EMU/blob/main/docs/sourcing.md).

## Files

```
CAD/   EMU_Filamentalist608.step   – full Filamentalist lane assembly with the mod applied
STL/   modified printed parts only
EMU_Filamentalist608.FCStd          – FreeCAD source of the modified Filamentalist lane assembly
```

> [!NOTE]
> **Only modified parts are exported as STLs.** Print all other parts from the original [EMU repository](https://github.com/DW-Tas/EMU) or its [configurator](https://emu.dwtas.net).

STL files follow the original EMU naming convention: **`[a]_` prefix = accent colour part** (red in the CAD model). Parts without the prefix are printed in the primary colour. An **`_x2`** suffix means print two.

| STL | Colour | Replaces original part | Qty | Print notes |
|---|---|---|---|---|
| `Chassis_L_608_Bearing001.stl` | Primary | Chassis_L_688_Bearing | 1 | |
| `Chassis_R_608_Bearing001.stl` | Primary | Chassis_R_688_Bearing | 1 | |
| `Stepper_Main_Body001.stl` | Primary | Stepper_Main_Body | 1 | |
| `EMU_Tensioner_Mount_with_Sensor001.stl` | Primary | EMU_Tensioner_Mount_with_Sensor | 1 | |
| `LED_holder001.stl` | Primary | LED_holder | 1 | **Print lying on its side.** The spacer strip's ends are tapered at 45° so there are no unsupported ledges in that orientation. The file contains two overlapping shells (holder + spacer strip); slicers merge them automatically. |
| `[a]_Rim_Roller_EMU_x2.stl` | Accent | [a]_Rim_Roller_EMU_x2 | **2** | Same part on both sides of the lane, so print 2 |
| `[a]_Idler_Roller_x2.stl` | Accent | [a]_Idler_Roller_x2 | **2** | Same part on both sides of the lane, so print 2 |
| `[a]_Tensioner_Arm001.stl` | Accent | [a]_Tensioner_Arm | 1 | **Print with the large flat top face on the build plate**, no supports needed |
| `[a]_608_Bearing_Bushing001.stl` | Accent | 688_Bearing_Bushing | 1 | 7 mm long (stock 5 mm) |

The STLs are positioned in assembly coordinates, so place them on the build plate in your slicer.

## Print settings

Use the same print settings as the original EMU. The section below is **copied verbatim from the original EMU documentation** ([Printing, Assembly and Wiring](https://github.com/DW-Tas/EMU/blob/main/docs/assembly_wiring/README.md#print-settings)). All credit to the EMU authors.

The parts in this mod are Filamentalist and lane stepper components, so the first subsection applies. The dry box and base unit settings are reproduced for completeness.

---

> [!WARNING]
> **Parts are not shrinkage compensated** - calibrate your filament shrinkage first! 

### Filamentalist components and Lane stepper components:
The below print settings are recommended for the filamentalist and lane stepper components. These are structural parts hence require print settings optimised for strength:
- 0.2 mm layer height
- 0.2 mm first layer height
- 4 walls
- 40% infill
- 0.4mm extrusion width (line width) throughout
- Gyroid sparse infill is recommended as it tends to warp less
- Inner Outer wall ordering, to ensure overhangs and supported areas do not sag
- Arachne wall generator
- One wall top and bottom surfaces (optional but recommended - parts look nicer)
- Disable thick bridges
- Z hop enabled to avoid nozzle scraping (0.2 is sufficient)

> [!IMPORTANT]
> If the bearings are loose, you're either under extruding, or over compensating for shrinkage.<br/>

> [!IMPORTANT]
> The [Idler_Roller_Axle](https://github.com/DW-Tas/EMU/blob/main/STL/Filamentalist/Idler_Roller_Axle.stl) and [[a]_Stepper_Tension_Arm](https://github.com/DW-Tas/EMU/blob/main/STL/Stepper/%5Ba%5D_Stepper_Tension_Arm%5BMR693zz%5D.stl) are best to be printed with **999 walls** to ensure adequate strength of the part and less chance of breakage.

> [!IMPORTANT]
> **Disable thick bridges** in your slicer and make sure your flow rate (EM) is on point! **Over extrusion, thick bridges and insufficient cooling will cause your sensor magnets and bearings not to fit as the bridges will sag.**

**For the TPU filamentalist CDR ring:**
- 0.2 mm layer height
- 0.2 mm first layer height
- 0.4mm extrusion width (line width) throughout
- 6 walls, so that the object is printed solid
- Avoid crossing walls enabled
- Random seam. This is important to avoid an aligned seam bump
- Inner Outer wall ordering, to ensure overhangs and supported areas do not sag
- Z Hop turned off to reduce stringing
  
> [!IMPORTANT]
> Printing TPU can be a challenge - print by object and a slight negative (-0.1) extra length on retract can help reduce stringing.

### Dry Box components:
The below print settings are recommended for the dry boxes and the desiccant holder. The dry boxes need to be as air tight as possible, hence the recommended print settings below are tuned to achieve this while keeping filament use under control.
- 0.2 mm layer height
- 0.2 mm first layer height
- 3 walls
- 15% infill
- For the lid specifically, use 4 walls and 30% infill to ensure strength in the front lip.
- 0.4mm extrusion width (line width) throughout
- Gyroid sparse infill is recommended as it tends to warp less
- Inner Outer wall ordering, to ensure dry box hatch features print with minimal sagging.
- Arachne wall generator
- One wall top and bottom surfaces (optional but recommended - parts look nicer)
- Disable thick bridges
- Z hop enabled to avoid nozzle scraping (0.2 is sufficient)

> [!IMPORTANT]
> Print with **extra first layer squish, use an adhesion promoter on the bed and in a pre-heated chamber with low fan** to prevent warping and ensure better layer adhesion. Mouse ears on the box corners may be required. Slight lifting will not impact part function.<br/>
> **Do not use mouse ears on the lid** as the slicer wrongly fills in the aesthetic lines.<br/>
> **Over extrude (only) the box and lid by ~2% (0.02)** to ensure air tightness. Increase your slicer flow multiplier (EM) by 0.02.

### Base unit components:
The below print settings are recommended for the base units and their accessories. 
- 0.2 mm layer height
- 0.2 mm first layer height
- 3 walls
- 15% infill
- 0.4mm extrusion width (line width) throughout
- Gyroid sparse infill is recommended as it tends to warp less
- Inner Outer Inner wall ordering to improve visual appearance
- Arachne wall generator
- One wall top and bottom surfaces (optional but recommended - parts look nicer)
- Disable thick bridges
- Z hop enabled to avoid nozzle scraping (0.2 is sufficient)
- For the **Eject button lens, 99 walls are recommended,** to reduce possibility of infill shining through the natural ABS

> [!IMPORTANT]
> Print with **extra first layer squish, use an adhesion promoter on the bed and in a pre-heated chamber with low fan** to prevent warping. Slight lifting will not impact part function.

> [!NOTE]
> **Paint on fuzzy skin** on the outer walls of the base unit will improve appearance.<br/>
> Paint on ONLY, not full model fuzzy skin. <br/>
> 0.1 distance, 0.1 or 0.2mm depth. Displacement method (orca slicer)

---

### Additional notes for this mod

- **608 bearing fit:** the new bearing pockets use the same crush-rib style as the original 688 pockets, scaled for 22 mm. The same advice applies: if the bearings are loose, you're under extruding or over-compensating for shrinkage.
- **Tensioner arm:** print with the large flat top face down. The bearing slot is open toward that face, so the 608 drops straight in.
- **LED holder:** print lying on its side.

## Assembly

Assemble as per the original EMU [assembly manuals and videos](https://github.com/DW-Tas/EMU/blob/main/docs/assembly_wiring/README.md). Differences:

1. Press 608 bearings into the chassis bosses (2 per chassis plate) and into the tensioner arm (with the 7 mm bushing).
2. Fit the narrower (21 mm) rubber bands on the rim rollers.
3. Use an M3×12 FHCS instead of M3×8 to fix the LED holder to the stepper body.

## License

The original EMU is licensed under the [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-nc-sa/4.0/). As a derivative work, **this mod is distributed under the same CC BY-NC-SA 4.0 license**. Credit for the original design goes to DW-Tas, igiannakas and the EMU contributors. EMU itself builds on the Filamentalist V3 design.

This is an unofficial community mod and is not endorsed by or affiliated with the EMU authors.

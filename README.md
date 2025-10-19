# FlexiRex-Fusion

A semi-parameterised recreation of the popular 3d printable FlexiRex model, created in Autodesk Fusion.

### License

[Creative Commons - Attribution - Share Alike](https://creativecommons.org/licenses/by-sa/4.0/)

### Attribution

This is a remix/recreation of DrLex0's Flexi Rex with stronger links ([DrLex0/print3D-FlexiRex](https://github.com/DrLex0/print3D-FlexiRex)), which itself is another remix of Kirbs' Flexi Rex ([Thingiverse thing:1759297](https://www.thingiverse.com/thing:1759297)), based on airfish's remix ([Thingiverse thing:2189652](https://www.thingiverse.com/thing:2189652)). That model in turn was most likely inspired by the ‘Flexy Rex’ by zheng3 ([Thingiverse thing:929413](https://www.thingiverse.com/thing:929413)).

Please read the licencing and attribution FAQ on DrLex0's original repository [here](https://github.com/DrLex0/print3D-FlexiRex/blob/master/README.md), the same applies to this model and repository.

## Fusion Parameter Reference

The free for persaonal use version of Autodesk Fusion can be downloaded [here](https://www.autodesk.com/products/fusion-360/personal), opening the [FlexiRex-Fusion.f3d](FlexiRex-Fusion.f3d) file or either of the other variants will allow you to customise the model to your needs by adjusting the built in parameters.

Access the parameters dialoge by clicking _MODIFTY_ > _Change Parameter_

![Fusion's Change Parameter dialoge](/assets/images/parameters.png?raw=true)

It's recommended to only change the favourited (blue stared) parameters, the full list can be found below in order of importance.

### scale_factor

Used to adjust the final scale of the model for printing. It's recommended, but not essential, to represent this as a fraction of the models default thickness (13 mm). For example, if you want the final model to be 7 mm thick, the scale factor would be 7/13.

- Default: 1 (13/13)
- Min: ~0.54 (7/13) with a 0.4 mm nozzle, and adjusted joint scaling and axle offset; ~0.31 (4/13) with a 0.2 mm nozzle, and adjusted joint scaling and axle offset
- Max: limited only by your imagination and the size of your print bed

### joint_scale_factor

Adjust the scale of the joints, this is useful for increasing the strength of the joints on heavily scalled down prints where the shackle thickness may drop below 2 extrusion widths.

|                                  Min: n/a (0.8 shown)                                   |                                       Default: 1                                        |                                 Max: ~1.2 (recommended)                                 |
| :-------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------: |
| ![Joints scaled by a factor of 0.8](/assets/images/joint_scale_factor_0.8.png?raw=true) | ![Joints scaled by a factor of 1.0](/assets/images/joint_scale_factor_1.0.png?raw=true) | ![Joints scaled by a factor of 1.2](/assets/images/joint_scale_factor_1.2.png?raw=true) |

Note: The scaling is centred on the joint axel centre so setting this value too high will cause the cutout for the shackel to break through and partially bisect some of the smaller segments of the model. The joint_axel_offset parameter can be used to mitigate this but even so, the maximum increase in joint scale is only ~20% (joint scale factor of 1.2)

### joint_axle_offset

As described above, offsets the axel to allow fine adjustmetn of the wall thickness of the end of the shackel cutout. This offset is applied after the model has been scaled so that wall thickness at the thinest point can be measured and an increase in axel offset will directly translate to an equal increase in wall thickness. While this does mean that the offset will need to be adjusted every time the model scale is changed, it allows you to easily adjust the wall thickness between the shackel cutout and the oposite face of each model segment to maintain a desired thickness (usaully at least two extrusion widths to maintain printablility and structural integrity). It can also be used to shift the axel further towards the centre point between each segment, having the pivot point at the exact centre point between each segment maximises flexibility, but only very slightly.

|                                          Default: 0 mm                                           |                                     Max: n/a (0.5 mm shown)                                      |
| :----------------------------------------------------------------------------------------------: | :----------------------------------------------------------------------------------------------: |
|         ![Model with no axle offset](/assets/images/joint_axle_offset_0.0.png?raw=true)          |         ![Model with 0.5 mm applied](/assets/images/joint_axle_offset_0.5.png?raw=true)          |
| ![Cutaway of model with no axle offset](/assets/images/joint_axle_offset_slice_0.0.png?raw=true) | ![Cutaway of model with 0.5 mm applied](/assets/images/joint_axle_offset_slice_0.5.png?raw=true) |

Note: It's not recommend to use negative value as this will shift the pivot point further away from the centre and reduce flexibility. In practice the maximum value will depend entirely on the scale of the model, too high a value will cause the axel to eat into and create gaps in the next segment in the chain, though this is preferable to the shackel cutout bisect the previous segment entirely.

### thickness_offset

Used to adjust the overall thickness of the model, the minimum is set such that leg and arm geometry doesn't break. Mainly cosmetic, but it's worth noting that after a point, increasing model thickness will dramatically reduce side-to-side flexibility.

|                                       Min: -2.9 mm                                       |                                       Default: 0 mm                                       |                                 Max: n/a (7 mm shown)                                 |
| :--------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------: |
| ![Model with -2.9 mm thickness offset](/assets/images/thickness_offset_min.png?raw=true) | ![Model with 0 mm thickness offset](/assets/images/thickness_offset_default.png?raw=true) | ![Model with 7 mm thickness offset](/assets/images/thickness_offset_max.png?raw=true) |

### head_thickness_offset

Used to adjust the thickness of the top jaw while maintining the eye and eyebrow position relative to the top of the head. Min is clamped to prevent the eye and shackel cutout from intersecting. Purely cosmetic and a bit of fun.

|                                            Min: -6 mm                                            |                                            Default: 0 mm                                            |                                      Max: n/a (5 mm shown)                                      |
| :----------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------: |
| ![Model with -6 mm head thickness offset](/assets/images/head_thickness_offset_min.png?raw=true) | ![Model with 0 mm head thickness offset](/assets/images/head_thickness_offset_default.png?raw=true) | ![Model with 5 mm head thickness offset](/assets/images/head_thickness_offset_5mm.png?raw=true) |

### layer_height

The layer height you are intending to print the model. Used to maintain vertical spacing and shell thickness of some features and to calculate maximum overhang angle.

### extrusion_width

The extrusion width (line width in most slicers) that will be used when printing the model, important to modify this to match whatever nozzle will be used. Used to maintain horizontal spacing and shell thickness of some features and to calculate maximum overhang angle.

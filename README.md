# TouchDesigner-LaunchPad-Utility
This tool simplifies the process of assigning and mapping buttons on the Novation Launchpad to functions in TouchDesigner.

## Compatibility
This tool is confirmed to work with the Novation LaunchPad Pro MK3 and Novation LaunchPad X. Other models of LaunchPad may not be compatible.

## Usage
For usage examples, open `example.toe`.

1. **Connect LaunchPad to your computer:**
    - If you are using the LaunchPad X, set the mode to `Custom 3` in the factory preset.
    - If you are using the LaunchPad Pro, set the mode to `Custom 7` in the factory preset.

2. **Configure MIDI Device Mapper in TouchDesigner:**
    - Open the `MIDI Device Mapper` from the `Dialog` menu in TouchDesigner.
    - Create a new mapping for the LaunchPad and set both the input and output.

3. **Set up the Master Component:**
    - Place the `launchcontrol_master.tox` (Master COMP) at the same or a higher directory level within your TouchDesigner project.
    - For instance, place it in `project1`.

4. **Configure the Master COMP:**
    - Set the `Device ID` and `MIDI Channel` of your LaunchPad in the Master COMP, and turn on `Active`. You can find these settings in the `MIDI Device Mapper`.
    - If the Master COMP does not work correctly, press `Reset` on the Master COMP.

5. **Set up the Selector Component:**
    - Place the `launchcontrol_select.tox` (Selector COMP) anywhere you need to assign the value of the components on the LaunchPad.
    - Open the `Custom` page in `launchpad_select.tox` and set the following parameters:
        - **Master OP Name**: Enter `LaunchPad_master`.
        - **Depth Level**: Set the number of levels up in the directory hierarchy from the current location of `launchpad_select.tox` to where `launchpad_master.tox` is located. For example, if `launchpad_master.tox` is located two levels up, set `Depth Level` to `2`.

6. **Edit the Map Configuration:**
    - Open `map_config` to edit the components on the LaunchPad.
    - Avoid making changes to other operators here.
    - Duplicate the `control` COMP to add components to the LaunchPad.
    - Use the `Custom` page in the COMP to edit components. Components can be momentary buttons, toggle buttons, or radio select buttons.

7. **Configure Component Parameters:**
    - Set the component mode, give the parameter a name, set its position, and size (if using `radio`), and set the pad LED color.

### Parameter Descriptions of Components
- **Active:** Enable or disable the component.
- **Parameter Name:** Name of the parameter for the component.
- **Position:** Position of the component on the LaunchPad.
- **Size:** Size of the component (applicable for `radio` mode).
- **Pad LED Color:** Color of the LED on the LaunchPad pad.

8. **Use Values from Selector COMP:**
    - You can use the values by either connecting to the output of the Selector COMP or by using Export CHOP directly from the Selector COMP.

## Reference
- [Launchpad Pro [MK3] User Guide by Novation](https://fael-downloads-prod.focusrite.com/customer/prod/s3fs-public/downloads/Launchpad%20Pro%20User%20Guide.pdf)
- [Launchpad Pro [MK3] Programmer's Reference Guide by Novation](https://fael-downloads-prod.focusrite.com/customer/prod/s3fs-public/downloads/LPP3_prog_ref_guide_200415.pdf)

## License
This project is licensed under the MIT License.

## About the Developer
### monoton  
music producer, DJ & VJ, virtual experience design, generative visual design  
[Linktree](https://linktr.ee/monoton)

### Support
If you find this project useful, please consider buying me a coffee!

<a href="https://www.buymeacoffee.com/monoton" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/default-orange.png" alt="Buy Me A Coffee" height="41" width="174"></a>

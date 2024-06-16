# TouchDesigner-LaunchPad-Utility

This tool simplifies the process of assigning and mapping buttons on the Novation Launchpad to functions in TouchDesigner.

## Trademark
Launchpad is a registered trademark of Focusrite. This project is not affiliated with or endorsed by Focusrite.

## Japanese Documentation
日本語のドキュメント（参考版）もあります。  
[日本語ドキュメント](README_JP.md)

## Compatibility
This tool is confirmed to work with the Novation LaunchPad Pro MK3 and Novation LaunchPad X. Other models of LaunchPad may not be compatible.
The tox files and the example project file were made with TouchDesigner in version 2023.11600.

## Usage
For usage examples, see inside the `example.toe`.

### Step 1: Connect LaunchPad to your computer
- If you are using the LaunchPad X, set the mode to `Custom 3` in the factory preset.
- If you are using the LaunchPad Pro, set the mode to `Custom 7` in the factory preset.

### Step 2: Configure MIDI Device Mapper in TouchDesigner
- Open the `MIDI Device Mapper` from the `Dialog` menu in TouchDesigner.
- Create a new mapping for the LaunchPad and set it as both the input and output.

### Step 3: Set up the Master Component
- Place the `launchpad_master.tox` (Master COMP) at the same level or a higher level in the directory hierarchy of the path where you will use this utility within your TouchDesigner project. For instance, place it in `/project1`.

### Step 4: Configure the Master COMP
- Set the `Device ID` and `MIDI Channel` of your LaunchPad in the Master COMP, and turn on `Active`. You can configure these values in the `MIDI Device Mapper`.
- If the Master COMP does not work correctly, press `Reset` on the Master COMP.

### Step 5: Edit the Map Configuration
- Open `map_config` to edit the components on the LaunchPad.
- Each component works as a button or a group of radio select buttons. You can designate each component's function, position on the LaunchPad, and LED color.
- Duplicate the `control_component` COMP to add components to the LaunchPad.
- Use the `Custom` page in the COMP to edit components. Components can be momentary buttons, toggle buttons, or radio select buttons.

#### Parameter Descriptions of Components
- **Active:** Enable this toggle to activate the component.
- **Parameter Name:** Name of the parameter for the component.
- **Type:** Function of the component. `Momentary`, `Toggle`, and `Radio` are available. `Radio` mode works like a radio select button.
- **Position:** Position of the component on the LaunchPad.
- **Size:** Size of the component on the LaunchPad (applicable for `radio` mode).
- **Pad LED Color:** Color of the LED on the LaunchPad with two parameters, `Hue` and `Value`. You can set the color individually for the on state and off state.

### Step 6: Set up the Selector Component
- Place the `launchpad_select.tox` (Selector COMP) anywhere you need to assign the value of the components on the LaunchPad.
- Open the `Custom` page in `launchpad_select.tox` and set the following parameters:
    - **Master OP Name:** Enter `LaunchPad_master`.
    - **Depth Level:** Set the number of levels up in the directory hierarchy from the current location of `launchpad_select.tox` to where `launchpad_master.tox` is located. For example, if `launchpad_master.tox` is located two levels up, set `Depth Level` to `2`.

### Step 7: Configure Component Parameters
- Set the component mode, give the parameter a name, set its position, and size (if using `radio`), and set the pad LED color.

### Step 8: Use Values from Selector COMP
- You can use the values by either connecting to the output of the Selector COMP or by using Export CHOP directly from the Selector COMP.

## Reference
- [Launchpad Pro [MK3] User Guide by Novation](https://fael-downloads-prod.focusrite.com/customer/prod/s3fs-public/downloads/Launchpad%20Pro%20User%20Guide.pdf)
- [Launchpad Pro [MK3] Programmer's Reference Guide by Novation](https://fael-downloads-prod.focusrite.com/customer/prod/s3fs-public/downloads/LPP3_prog_ref_guide_200415.pdf)

## Troubleshooting
- If you encounter issues with the components not responding, ensure that the `Device ID` and `MIDI Channel` settings match those of your LaunchPad.
- Make sure the `launchpad_master.tox` is placed at the correct directory level.
- Double-check the mappings in the `MIDI Device Mapper`.

## License
This project is licensed under the MIT License.

## About the Developer
### monoton  
music producer, DJ & VJ, virtual experience design, generative visual design  
[Linktree](https://linktr.ee/monoton)

### Support
If you find this project useful, please consider buying me a coffee!

<a href="https://www.buymeacoffee.com/monoton" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/default-orange.png" alt="Buy Me A Coffee" height="41" width="174"></a>

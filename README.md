# TouchDesigner-LaunchPad-Utility
A tool for easily assigning and mapping buttons on the Novation Launchpad to functions in TouchDesigner. 

## Competability
This tool is comfirmed to work with Novation LaunchPad Pro MK3 and Novation LaunchPad X. Other types of LaunchPad may not competable with this tool.

## Usage
For detailed instruction and example, open `example.toe` and see inside the project.

1. Connect LaunchPad to your computer and
    - If you use LaunchPad X, set the mode to `Custom 3` of the factory preset.
    - If you use LaunchPad Pro, set the mode to `Custom 7` of the factory preset.

2. Open `MIDI Device Mapper` in `Dialog` menu in TouchDesigner, create new mapping of LaunchPad and set the input and output.

3. Place `launchcontrol_master.tox` (Master COMP) at the same level or a higher level in the directory hierarchy of the path where you will use this utility within your TouchDesigner project.
    - For example, you may put it in `project1`.

4. In Master COMP, set `Device ID`, `MIDI Channel` of your LaunchPad and turn on `Active`. You can confirm them in `MIDI Device Mapper`.
    - If Master COMP does not work correctly, press `Reset` in Master COMP.

5. Place `launchcontrol_select.tox` (Selector COMP) anywhere you want to assign the value of the components on LaunchPad.

6. Use the values from Selector COMP by either:
    - Connecting to the output of Selector COMP.
    - Using Export CHOP directly from Selector COMP.

## Reference
- ["Launchpad Pro [MK3] User Guide English - EN" by Novation](https://fael-downloads-prod.focusrite.com/customer/prod/s3fs-public/downloads/Launchpad%20Pro%20User%20Guide.pdf)
- ["Launchpad Pro [MK3] Programmer's Reference Guide" by Novation](https://fael-downloads-prod.focusrite.com/customer/prod/s3fs-public/downloads/LPP3_prog_ref_guide_200415.pdf)

## License
MIT License

## About Developer
### monoton  
music producer, DJ & VJ, (virtual) experience design, generative visual design  
[Linktree](https://linktr.ee/monoton)

### Support me
If you find this project useful, please consider buying me a coffee!

<a href="https://www.buymeacoffee.com/monoton" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/default-orange.png" alt="Buy Me A Coffee" height="41" width="174"></a>
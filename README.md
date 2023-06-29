# Macro RaiLab
 Macro package for 3dprinters at RAI Lab, design to work with `moonraker.conf`

## How to install
A simple copy and paste a few commands in an ssh terminal. The instructions assume that you have an up to data and working moonraker installation. If not start with updating your moonraker first.
** please check for model of the printer that you are trying to install
  -ender3_model1 is using the original hardware, without the z-probe
  -ender3_model2 is using the improved hardware with z-probe and H2V2 extruder+hotend set

### For ender3_model1
**use the block below if you have two printer per host**
```
cd ~
git clone https://github.com/Zartern/Macro-RaiLab.git
ln -sf ~/Macro-RaiLab/ender3_model1/macros.cfg ~/printer_1_data/config/macros.cfg
ln -sf ~/Macro-RaiLab/ender3_model1/macros.cfg ~/printer_2_data/config/macros.cfg
```
**use the block below if you have one printer per host**
```
cd ~
git clone https://github.com/Zartern/Macro-RaiLab.git
ln -sf ~/Macro-RaiLab/ender3_model1/macros.cfg ~/printer_data/config/macros.cfg
```
### For ender3_model2
**use the block below if you have two printer per host**
```
cd ~
git clone https://github.com/Zartern/Macro-RaiLab.git
ln -sf ~/Macro-RaiLab/ender3_model2/macros.cfg ~/printer_1_data/config/macros.cfg
ln -sf ~/Macro-RaiLab/ender3_model2/macros.cfg ~/printer_2_data/config/macros.cfg
```
**use the block below if you have one printer per host**
```
cd ~
git clone https://github.com/Zartern/Macro-RaiLab.git
ln -sf ~/Macro-RaiLab/ender3_model2/macros.cfg ~/printer_data/config/macros.cfg
```
## Add updater section
You need to update your moonraker.conf to alway get the latest version.
### Add the code block below to `moonraker.conf` **_Per instance of the printer within the host control_**
```
#experimental
[update_manager Macro-RaiLab]
type: git_repo
primary_branch: master
path: ~/Macro-RaiLab
origin: https://github.com/Zartern/Macro-RaiLab.git
refresh_interval: 24
managed_services: klipper
```

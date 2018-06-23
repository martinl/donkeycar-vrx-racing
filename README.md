These are build notes for [donkeycar](http://www.donkeycar.com/) platform using [VRX Racing Coyote EBD 1:10](http://www.riverhobby.com/en/detail.php?id=48) as base. See also http://diyrobocars.com/ and http://docs.donkeycar.com/

BOM
===
* VRX Racing Coyote EBD (RTR) http://www.riverhobby.com/en/detail.php?id=48 162EUR
* local RC shops:
  * https://www.photopoint.ee/kaugjuhitavad-autod?&m=5875&fg=3090&os=1&new=0&pp=36&view=grid&s=price_asc
  * https://rc-est.ee/catalog/index.php?cPath=1_164&sort=3a&page=2&osCsid=bc98706eb21c5e89962b50bf292e0487
  * http://gear7.eu/
* Raspberry Pi 3+ https://www.oomipood.ee/product/2842228_raspberry_pi_3_mudel_b_moodul_1_4ghz_1gb 42EUR
* Raspberry Pi Camera https://www.oomipood.ee/product/2510728_raspberry_pi_camera_board_8mp_v2 39EUR
* PCA9586 https://www.oomipood.ee/product/pca9685_shield_mugandusplaat_mootorite_uhendamiseks_raspberryle?q=pca9685 11EUR
* Step-down USB DC-DC converter with LCD https://www.oomipood.ee/ee/product/ps_step_down_ind_toitemoodul_dc_dc_step_down_1_3_37v_15w_lm2596s_led_n 12EUR
* Total 162+42+39+11+12 = 266EUR

RPi3+
=====

Wiring
------
* 3V3 - red
* SDA - yellow
* SDC - green

* GND - black

* [Electronics diagram](Electronics.pdf)

PCA9586
-------
* channel 0: ESC/BEC
* channel 1: steering servo 

Software
--------
Default donkeycar image does not work with Raspberry Pi 3+ (only with RPi3). See [here](https://github.com/wroscoe/donkey/issues/230) for a link to RPi3+ compatible image and possible issues and solutions.

RPi3+ image is missing d2 directory with car definition, run this before calibration in rpi:
```
donkey createcar --template donkey2 ~/d2
```
Calibration
-----------
* fwd speed 390 (max 400)
* rwd speed 360 (max 330)

* max right 310 (340?)
* max left  460

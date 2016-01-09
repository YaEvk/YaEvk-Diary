It's more maintained than flu.x, it has more options and it works perfectly with Ubuntu 14.10 x64 and Ubuntu 15.04 x64.

It can be installed from the repositories (12.04, 14.04, and newer):

```sudo apt-get install redshift gtk-redshift```

You may optionally create a configuration file for RedShift. It is NOT created automatically, so you'll have to create it using gedit ~/.config/redshift.conf.

This is how my redshift.conf file looks like:
```
; Global settings for redshift
[redshift]
; Set the day and night screen temperatures
temp-day=4500
temp-night=3500

; Enable/Disable a smooth transition between day and night
; 0 will cause a direct change from day to night screen temperature.
; 1 will gradually increase or decrease the screen temperature
transition=1

; Set the screen brightness. Default is 1.0
;brightness=0.8
; It is also possible to use different settings for day and night since version 1.8.
brightness-day=0.9
brightness-night=0.7
; Set the screen gamma (for all colors, or each color channel individually)
gamma=0.8
;gamma=0.8:0.7:0.8

; Set the location-provider: 'geoclue', 'gnome-clock', 'manual'
; type 'redshift -l list' to see possible values
; The location provider settings are in a different section.
location-provider=geoclue

; Set the adjustment-method: 'randr', 'vidmode'
; type 'redshift -m list' to see all possible values
; 'randr' is the preferred method, 'vidmode' is an older API
; but works in some cases when 'randr' does not.
; The adjustment method settings are in a different section.
adjustment-method=randr

; Configuration of the location-provider:
; type 'redshift -l PROVIDER:help' to see the settings
; ex: 'redshift -l manual:help'
[manual]
;lat=51.522698 ; set these values if you've set the location-provider to manual instead of geoclue
;lon=-0.085358

; Configuration of the adjustment-method
; type 'redshift -m METHOD:help' to see the settings
; ex: 'redshift -m randr:help'

[randr]
screen=0
```
If you need to, compiling it manually is also quite easy. Here is the official repository: https://github.com/jonls/redshift

Just make sure that you've installed all the dependencies specified in the travis.yml file before running the bootstrap executable file.

Instructions here: https://github.com/jonls/redshift/blob/master/HACKING.md

For Ubuntu 15.04 users: it could be that you won't be able to use redshift because of some missing dependencies. Try to compile it by getting the code directly from github.
```
sudo apt-get install build-essential libxcb-randr0-dev
./bootstrap
./configure --enable-randr
make
sudo checkinstall
```
...or just install if you don't want to use checkinstall. The libxcb-randr0-dev package should satisfy the dependency to use randr as an adjustment method. Otherwise try to enable vidmode by doing:
```
./configure --enable-vidmode
```

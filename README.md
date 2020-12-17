![Title Artwork](https://i.imgur.com/3kvYoqp.png)


# Launch options
```
-novid -nojoy -console -borderless +exec autoexec
```

# Jump-throw-helper
_Hold Nade, press and hold mouse1, if you pres the Jumptrhow button it jumps and automatic release at highest point_
```
alias "+jumpthrow" "+jump; -attack"
alias "-jumpthrow" "-jump"
bind "t" "+jumpthrow"
```

# Mouse Tweaks
```
m_rawinput "1"
m_pitch "0.022"
zoom_sensitivity_ratio_mouse "1"
m_customaccel "0"
m_mousespeed "0"
m_mouseaccel1 "0"
m_mouseaccel2 "0"
```

# Audio Tewaks
```
snd_menumusic_volume "0"
snd_mix_async "1"
snd_mixahead "0.025"
```

# Toggle AFK-Mode ON/OFF
```
alias afk "afk1"
alias afk1 "+left; +forward; say AFKMODE: ON; alias afk afk2"
alias afk2 "-left; -forward; say AFKMODE: OFF; alias afk afk1"
bind o "afk"
```

# Nice Crosshair with high visibility, static
```
cl_crosshairstyle "5"
cl_crosshaircolor "2"
cl_crosshaircolor_r "255"
cl_crosshaircolor_g "255"
cl_crosshaircolor_b "255"
cl_crosshairalpha "255"
cl_crosshair_drawoutline "1"
cl_crosshair_outlinethickness "0.5"
cl_crosshairthickness "0.75"
cl_crosshairsize "2"
cl_crosshairgap "-1.25"
cl_crosshair_dynamic_splitdist "1"
cl_crosshair_dynamic_maxdist_splitratio "-1"
cl_crosshair_dynamic_splitdist "1"
cl_crosshair_dynamic_maxdist_splitratio "0.15"
cl_crosshairdot "0"
```

### Advanced Attack Crosshair
_ The Crosshair schanges from static to Dynamic and gets smaller if you're shooting,
   good for Spray control and accuracy precision _
```   
alias +size "toggle cl_crosshairsize 2 0.75"
alias +color "toggle cl_crosshaircolor 2 5"
alias +gap "toggle cl_crosshairgap -1.25 -3.0"
alias +type "toggle cl_crosshair_t 0 1"
bind "MOUSE1" "+attack; +color; +gap; +size"
```

# Movement (Clear decals like Bullets, Blood, .. on duck and slowwalk)
```
bind "a" "+moveleft"
bind "d" "+moveright"
bind "s" "+back"
bind "w" "+forward"
bind "MWHEELDOWN" "+jump"
bind "MWHEELUP" "+jump"
bind "SHIFT" "+speed; r_cleardecals"
bind "CTRL" "+duck; r_cleardecals"
```

# Nice colorful HUD with good visibility and custom Safezone
```
cl_hud_color 4
cl_hud_playercount_showcount 1
cl_hud_playercount_pos 1
cl_show_team_equipment
cl_hud_healthammo_style 
cl_hud_background_alpha 
cl_hud_bomb_under_radar 
cl_radar_square_with_scoreboard 
cl_teammate_colors_show 
hud_scaling 
hud_showtargetid 
safezonex 0.75
safezoney 0.85
```

# Reality Viewmodel to make the Game look more natural 
```
cl_viewmodel_shift_left_amt "0.500000"
cl_viewmodel_shift_right_amt "0.250000"
viewmodel_fov "68"
viewmodel_offset_x "2.300000"
viewmodel_offset_y "-1"
viewmodel_offset_z "-2"
viewmodel_presetpos "0"
viewmodel_recoil "0.5"
cl_bob_lower_amt "5.000000"
cl_bobamt_lat "0.100000"
cl_bobamt_vert "0.100000"
cl_bobcycle "0.98"
```

# Rainbow HUD, Rainbow Crosshair (LSD MODE)
```
// RAINBOW HUD 
bind "w" "+forward;toggle cl_hud_color 5 6 4 3 2 1 9 8 7 10 11";
bind "a" "+moveleft;toggle cl_hud_color 5 6 4 3 2 1 9 8 7 10"
bind "s" "+back;toggle cl_hud_color 5 6 4 3 2 1 9 8 7 10 11"
bind "d" "+moveright;toggle cl_hud_color 5 6 4 3 2 1 9 8 7 10 11"
bind "SPACE" "+jump;toggle cl_hud_color 5 6 4 3 2 1 9 8 7 10 11"
bind "ctrl" "+duck;toggle cl_hud_color 5 6 4 3 2 1 9 8 7 10 11"
bind "mouse1" "+attack;toggle cl_hud_color 5 6 4 3 2 1 9 8 7 10 11"

// RAINBOW CROSHAIR
bind "w" "+forward;toggle cl_crosshaircolor 0 1 2 3 4"
bind "a" "+moveleft;toggle cl_crosshaircolor 0 1 2 3 4"
bind "s" "+back;toggle cl_crosshaircolor 0 1 2 3 4"
bind "d" "+moveright;toggle cl_crosshaircolor 0 1 2 3 4"
bind "SPACE" "+jump;toggle cl_crosshaircolor 0 1 2 3 4"
bind "ctrl" "+duck;toggle cl_crosshaircolor 0 1 2 3 4"
bind "mouse1" "+attack;toggle cl_crosshaircolor 0 1 2 3 4"

// BACK TO DEFAULT
bind "w" "+forward"
bind "a" "+moveleft"
bind "s" "+back"
bind "d" "+moveright"
bind "SPACE" "+jump"
bind "ctrl" "+duck"
bind "mouse1" "+attack"
```

# Intelligent MWHEEL Switch
```
// Intelligent MWHEEL UP >> Primary Secondary "Weapon-switch"
alias weaponswitch "weapons1"
alias weapons1 "slot1;alias weaponswitch weapons2"
alias weapons2 "slot2;alias weaponswitch weapons1"

bind "mwheelup" "weaponswitch;kslot"


// Intelligent MWHEEL DOWN  >> "Greanade-switch"
alias grenswitch "gren1"
alias gren1 "use weapon_flashbang;alias grenswitch gren2"
alias gren2 "use weapon_hegrenade;alias grenswitch gren3"
alias gren3 "use weapon_smokegrenade;alias grenswitch gren4"
alias gren4 "use weapon_molotov; use weapon_incgrenade; alias grenswitch gren5"
alias gren5 "use weapon_decoy; alias grenswitch gren1"

bind "mwheeldown" "grenswitch;kslot"


// Toggle between mouselwheel jump and weapon switch
alias toggleHop toggleHopOn
alias toggleHopOff "alias toggleHop toggleHopOn; bind mwheelup invprev;bind mwheeldown invnext"
alias toggleHopOn "alias toggleHop toggleHopOff; bind mwheelup +jump;bind mwheeldown +jump"

bind alt toggleHop 
```

# TEAMCHAT <> ALLCHAT SWITCH
```
// Teamchat on Enter, Allchat on Shift+Enter
alias +walkchat "+speed; bind enter messagemode2"
alias -walkchat "-speed; bind enter messagemode"

bind shift +walkchat
bind rshift +walkchat
bind enter messagemode
```

# Buyscript with Chatlog [NUMBLOCK 0 - 3]
```
// Key = Numpad "0" (ins) - buy Grenade Utility
bind "kp_ins" "buy hegrenade;buy smokegrenade;buy flashbang;buy flashbang; say_team [BUYLOG] 2x Flash, 1x HE, 1x Smoke ..."

// Key = Numpad "1" (end) - buy Heavy Pistol: Deagle / Revolver
bind "kp_end" "buy deagle; buy revolver; say_team [BUYLOG] Dessert Eagle ..."

// Key = Numpad "2" (downarrow) - buy Rifles: M4A1/AK47
bind "kp_downarrow" "buy ak47; buy m4a1; say_team [BUYLOG] M4A1/AK47 ..."

// Key = Numpad "." (del) - buy Utility: Vesthelm + Defusekit
bind "kp_del" "buy vesthelm; buy vest;buy defuser; say_team [BUYLOG] Kevlar + Helmet, Defuse kit ..."

// Key = Numpad "3" (pagedown) - buy Sniper: AWP
bind "kp_pgdn" "buy awp; say_team [BUYLOG] AWP ..."
```

### Full Config to copy
```
clear

unbindall
unbindallmousekeyboard

// FPS
fps_max "999"
fps_max_menu "999"

//Jump-throw-helper
alias "+jumpthrow" "+jump; -attack"
alias "-jumpthrow" "-jump"
bind "t" "+jumpthrow"

// Mouse
sensitivity "2.20"
m_rawinput "1"
m_pitch "0.022"
zoom_sensitivity_ratio_mouse "1"
m_customaccel "0"
m_mousespeed "0"
m_mouseaccel1 "0"
m_mouseaccel2 "0"

// AUDIO
snd_menumusic_volume "0"
snd_mix_async "1"
snd_mixahead "0.025"

// NETWORK
cl_lagcompensation "1"
cl_predict "1"
cl_predictweapons "1"
cl_interp "0.031000"
cl_interp_ratio "2"
cl_cmdrate "64"
cl_updaterate "64"
rate "786432"

// MISC
mm_dedicated_search_maxping "350"
cl_use_opens_buy_menu "0"
con_enable "1"
cl_dm_buyrandomweapons "1"
cl_teammate_colors_show "1"
cl_autowepswitch "0"
cl_autohelp "0"
cl_disablehtmlmotd "0"
cl_downloadfilter "nosounds"
cl_showhelp "0"
cl_forcepreload "1"
joystick "0"
r_dynamic "0"

//HUD
cl_hud_color 4
cl_hud_playercount_showcount 1
cl_hud_playercount_pos 1
cl_show_team_equipment
cl_hud_healthammo_style 
cl_hud_background_alpha 
cl_hud_bomb_under_radar 
cl_radar_square_with_scoreboard 
cl_teammate_colors_show 
hud_scaling 
hud_showtargetid 

// RADAR
cl_hud_radar_scale 1.1
cl_radar_scale 0.5
cl_radar_always_centered 1
cl_radar_rotate 0
cl_radar_icon_scale_min 0.9
cl_radar_square_with_scoreboard "0

// VIEWMODEL
cl_viewmodel_shift_left_amt "0.500000"
cl_viewmodel_shift_right_amt "0.250000"
viewmodel_fov "68"
viewmodel_offset_x "2.300000"
viewmodel_offset_y "-1"
viewmodel_offset_z "-2"
viewmodel_presetpos "0"
viewmodel_recoil "0.5"
cl_bob_lower_amt "5.000000"
cl_bobamt_lat "0.100000"
cl_bobamt_vert "0.100000"
cl_bobcycle "0.98"

// SLOTS
bind "0" "slot10"
bind "1" "slot1"
bind "2" "slot2"
bind "3" "slot3"
bind "4" "slot4"
bind "5" "slot5"
bind "6" "slot6"
bind "7" "slot7"
bind "8" "slot8"
bind "9" "slot9"

// MOVEMENT
bind "a" "+moveleft"
bind "d" "+moveright"
bind "s" "+back"
bind "w" "+forward"
bind "MWHEELDOWN" "+jump"
bind "MWHEELUP" "+jump"
bind "SHIFT" "+speed; r_cleardecals"
bind "CTRL" "+duck; r_cleardecals"
bind "f" "+lookatweapon"

// Crosshair
cl_crosshairstyle "5"
cl_crosshaircolor "2"
cl_crosshaircolor_r "255"
cl_crosshaircolor_g "255"
cl_crosshaircolor_b "255"
cl_crosshairalpha "255"
cl_crosshair_drawoutline "1"
cl_crosshair_outlinethickness "0.5"
cl_crosshairthickness "0.75"
cl_crosshairsize "2"
cl_crosshairgap "-1.25"
cl_crosshair_dynamic_splitdist "1"
cl_crosshair_dynamic_maxdist_splitratio "-1"
cl_crosshair_dynamic_splitdist "1"
cl_crosshair_dynamic_maxdist_splitratio "0.15"
cl_crosshairdot "0"

// ADVANCED ATTACK CROSHAIR
alias +size "toggle cl_crosshairsize 2 0.75"
alias +color "toggle cl_crosshaircolor 2 5"
alias +gap "toggle cl_crosshairgap -1.25 -3.0"
alias +type "toggle cl_crosshair_t 0 1"
bind "MOUSE1" "+attack; +color; +gap; +size"

// Toggle AFK-Mode ON/OFF
alias afk "afk1"
alias afk1 "+left; +forward; say AFKMODE: ON; alias afk afk2"
alias afk2 "-left; -forward; say AFKMODE: OFF; alias afk afk1"
bind o "afk"

bind space "+jump"

// USE, EQUIP
bind "b" "buymenu"
bind "e" "+use"
bind "q" "lastinv"
bind "r" "+reload; r_cleardecals; say_team >I'm Reloading..."
bind "g" "drop; say_team >Item dropped..."
bind "F3" "autobuy"
bind "F4" "rebuy"

// ATTACK
bind "MOUSE1" "+attack"
bind "MOUSE2" "+attack2"

// CHAT
bind "ALT" "+voicerecord"
bind "u" "messagemode2"
bind "z" "messagemode"

// MISC BINDS
bind "m" "teammenu"
bind "k" "toggleconsole"
bind "ESCAPE" "cancelselect"
bind "h" "+spray_menu"
bind "TAB" "+showscores"

host_writeconfig 

clear

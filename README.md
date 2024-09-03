# **FiveM-Modified-Trew-Hud**

A modified version of **trew_hud_ui**

## Preview:
- **Photo with dark background:** [Screenshot 1](https://i.ibb.co/M21MSwc/Screenshot-2166.png)
- **Photo with bright background:** [Screenshot 2](https://i.ibb.co/CMDPjRJ/Screenshot-2168.png)

## Requirements
- **es_extended**
- **esx_society**
- **esx_addonaccount**

### Optional
- **esx_basicneeds**
- **esx_status**
- **LegacyFuel** (it should be started **before** the trew_hud_ui)

## What You Can Disable
- **RadarWhileDriving**

## Post Installation
1. Go to **es_extended** `config.lua` and set `Config.EnableHud` to `false`.

2. If needed, go to **esx_basicneeds** `main.lua` and replace this code:
    ```lua
    TriggerEvent('esx_status:registerStatus', 'hunger', 1000000, '#CFAD0F', function(status)
        return true
    end, function(status)
        status.remove(1000)
    end)
    TriggerEvent('esx_status:registerStatus', 'thirst', 1000000, '#0C98F1', function(status)
        return true
    end, function(status)
        status.remove(750)
    end)
    ```

    with this one:

    ```lua
    TriggerEvent('esx_status:registerStatus', 'hunger', 1000000, '#CFAD0F', function(status)
        return false
    end, function(status)
        status.remove(1000)
    end)
    TriggerEvent('esx_status:registerStatus', 'thirst', 1000000, '#0C98F1', function(status)
        return false
    end, function(status)
        status.remove(750)
    end)
    ```

## Config.ui
**Display or hide elements of the HUD**

- `showJob`: Displays the job name. **Default is true;**
- `showWalletMoney`: Displays the money in your wallet. **Default is true;**
- `showBankMoney`: Displays the money in your bank account. **Default is true;**
- `showBlackMoney`: Displays the black money you have. **Default is true;**
- `showSocietyMoney`: If you are the boss of a job, it displays the money you have in the society vault. **Default is true;** (Society money only works on ESX)
- `showDate`: Displays the date. **Default is true;**
- `showLocation`: Displays the location. **Default is true;**
- `showHealth`: Displays your health. **Default is true;**
- `showArmor`: Displays your armor. **Default is true;**
- `showStamina`: Displays your stamina. **Default is true;**
- `showHunger`: Displays hunger. **Default is true;**
- `showThirst`: Displays thirst. **Default is true;**
- `showMinimap`: Displays the minimap while off the vehicle. **Default is false;**
- `showVoice`: Displays/uses the voice controller. **Default is true;**
- `showWeapons`: Displays the weapons you have on your hand, with ammo. **Default is true;**

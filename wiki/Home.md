# Welcome, Space Penguins!

This wiki is a collection of information on how to run Star Citizen on Linux, as well as our tips and tricks!

🐧 Join us! https://robertsspaceindustries.com/orgs/LUG  

🗨 Discord: https://discord.gg/meCFYPj  
😎 Matrix space: https://matrix.to/#/#SCLUG:matrix.org  

## Contents
* [Quick-Start Guide](Quick-Start-Guide)
* [Manual Installation](Manual-Installation)
* [Troubleshooting](Troubleshooting)
* [Performance Tuning](Performance-Tuning)
* [Tips and Tricks](Tips-and-Tricks)
* [Sticks, Throttles, & Pedals](Sticks,-Throttles,-&-Pedals)

## News

**Game Updates**

> (Mar 11, 2023) **3.18 Mouse/Cursor Issues**  
> - The 3.18 update may cause **mouse and view snapping issues** for some people using Wayland. We recommend installing Gamescope as a workaround or using Xorg.
> - After installing Gamescope, enable it in Lutris: `Right click the game->Configure->System options->Enable Gamescope`. Then, set `Gamescope output resolution` to your monitor's native resolution, ie `1920x1080`.
> - If it doesn't work, manual configuration may be required. Undo the above settings, then `Right click the game->Configure->System options->Command prefix`. Add the following to the text box, changing the width and height to match your desired resolution:
>   ```
>   gamescope --force-grab-cursor -W 1920 -H 1080
>   ```
> - Other arguments that may be required depending on your system: `-f` if it doesn't launch fullscreen, `-g` to grab keyboard
> - Depending on your system, `Prefer System Libraries` may need to be enabled or disabled in Lutris
> - If this doesn't work, you may need to switch to Xorg and reboot.

> (Jan 27, 2023) **RSI Launcher v1.6.2 JavaScript error**  
>
> Special configuration is needed in Lutris or you will receive a JavaScript error. See [CIG's announcement in Spectrum](https://robertsspaceindustries.com/spectrum/community/SC/forum/1/thread/upcoming-launcher-update-for-linux-users/5693728  )
>
> **Solution 1:**
> - **After the launcher updates,** all Penguins must configure the following:
>   - `Right click the game->Configure->Game options` add `--no-sandbox` to the Arguments
>   - In `System options`, make sure Advanced options is on then enable `CLI mode`
>
> **Solution 2:**
> - **If this does not fix the problem**, revert the above changes and install the latest GloriousEggroll runner, available in our Helper

> (Jan 27, 2023) **Fresh installs fail to create needed directories**
> - This has been resolved in the latest version of our [Helper](https://github.com/starcitizen-lug/lug-helper/releases) for new installs.
> - For existing or manual installs, run the following command to create the necessary directory structure for both the LIVE and PTU environments. Adjust the wine prefix path if installing to a non-default location:  
> ```
> mkdir -p "/home/$USER/Games/star-citizen/drive_c/Program Files/Roberts Space Industries/StarCitizen/"{LIVE,PTU}
> ```


**General News**

> (Feb 11, 2023) **Lutris install script**
> - The Star Citizen install script on the Lutris website is currently broken. We recommend using the installer we bundle with our [Helper](https://github.com/starcitizen-lug/lug-helper) instead.
> - To fix broken installs after using the Lutris website's script, enable DXVK in Lutris then install a recommended DXVK and runner based on our [Quick Start Guide ](https://github.com/starcitizen-lug/knowledge-base/wiki/Quick-Start-Guide). You may also need to disable `Prefer System Libraries` and `Use System Winetricks` and manually create missing directory paths for the install to complete.


**Nvidia News**

> (March 15, 2023) **Severe frame drops on 3.18**
> - We're currently tracking VRAM exhaustion problems on nvidia cards and 3.18. Keep an eye on our Discord tech support channel, but no solutions have been found just yet besides switching to AMD.

> (Jan 27, 2023) **Required DXVK version**
> - DXVK 2.1 may resolve issues Penguins had with previous versions of DXVK and may perform better without async.
> - For DXVK 2.0 and prior, Penguins with RTX cards should use [gnusenpai DXVK v1.10.1 or later](https://github.com/gnusenpai/dxvk/releases) to fix the `corrupted size vs. prev_size` error/crash. Can be installed manually or from the LUG helper.

> (Nov 17, 2022) **DXVK 2.0**
> - DXVK 2.0 changes the way shaders are handled on some Nvidia cards and may provide better performance than async (see the [release notes](https://github.com/doitsujin/dxvk/releases/tag/v2.0)). If you have worse performance on 2.0, remove the the `DXVK_ASYNC=1` environment variable.
> - DXVK 2.0 requires Nvidia driver **v510.47.03** or later, but **v520.56.06** or later is recommended.


**Easy Anti-Cheat**

> (Feb 12, 2022) **Easy Anti-Cheat is live.**
> - CIG is aware of the problem but there is still no ETA. There are currently no consequences that we are aware of for using the workaround, but CIG has suggested that eventually people will be kicked for tripping EAC. To apply the workaround, use the [LUG Helper](https://github.com/starcitizen-lug/lug-helper).

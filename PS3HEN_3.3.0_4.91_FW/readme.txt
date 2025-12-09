PS3HEN v3.3.0

Compatible with 4.91 HFW ONLY

WARNING: HFW by itself could have potential issues. It is recommended to only use this firmware as a way
to install PS3HEN, not a firmware to use unmodified. The reason is some of the SPRX files get replaced by
older versions during the creation of HFW itself. Only after installing PS3HEN are these files restored
to an OFW state, leaving only silk_webkit patched for exploit.


WHAT IS HEN:
HEN stands for Homebrew ENabler. it also consists of much more new functions relatively close to a CFW


File Hash Verify

PS3HEN.BIN	015BAC505DBDA9D61FBAFCC562E49BA4





Standard Online/Local Host HEN Setup Instructions
-------------------------------------------------

1) Run the /html/hen_installer/index.html (or visit http://ps3xploit.me/hen/installer/)
2) HEN package will be downloaded and installed automatically
3) Reboot PS3
4) Launch From New "Enable HEN" XMB Icon, Under Game Column


HEN Enable will be the default XMB landing icon after installation. To make it work properly, navigate to System Settings > Display [Whats New] > Off




CHANGELOG
----------

v3.3.0

Global Changes

  - Added support for 4.91 CEX firmware (HFW) (thanks Joonie)

HEN Plugin Changes

  - Fixed early reboot problem with HEN_UPD.PKG for Emergency USB Recovery

Payload Changes

  - Fixed issue with PSP Launcher (thanks aldostools, LuanTeles)

Resource Changes

  - Added *Toggle 99 Percent Package Install/Delete* option in HFW Tools->Maintenance (thanks zmod)
  - Updated download_list.xml to use updated paths on dev_hdd0 (thanks LuanTeles, DeViL303)
  - Added support for PS Home Catalogue path in download_list.xml (thanks DeViL303, LuanTeles, aldostools)
  - Added support for dev_usb002 - dev_usb007 in package manager (thanks LuanTeles)
  
  

v3.2.2

Global Changes

  - Added support for 4.80 and 4.81 CEX firmware
  - Added support for 4.82 DEX firmware
  - Automatic Updates are now disabled by default. You can use HFW Tools->Maintenance and toggle back on/off

HEN Plugin Changes

  - Added support for RCO Sounds and LED Status (thanks aldostools)
  - Updated install finished detection method (thanks aldostools)
  - Updated and cleaned up downloadPKG_thread2 function
  - Added detection of dev_build toggle for usb000 and usb001

Payload Changes

  - Pad function fixed to not hang when more than one device is connected (thanks aldostools)
  - Disabled VSH Attach To Debugger as default, to not conflict with some CFW (4.82/4.84 DEX)
  - Multiple Updates: PSP launcher blacklisting + more (thanks aldostools)
  - Added L2 to disable mappath remap on hen launch

Resource Changes

  - Updated software_update_plugin.rco message to display the .me domain instead of the .com
  - Added *Uninstall HEN* option to HFW Tools->Maintenance
  - Added *Disable Remapping On Next Reboot* option in HFW Tools->Maintenance. This will disable the remapped files from mappath so these files can be managed and users can also use the backup/restore option from XMB (thanks Fredy66)
  - Added *Toggle Hotkey Polling* option in HFW Tools->Maintenance. This will enable/disable check_combo_buttons function when HEN launches. (thanks FFF256)
  - Added *Toggle app_home Support* option in HFW Tools->Maintenance. This updates xml containing the seg_gamedebug entries (thanks Fredy66)
  - Added *Enable Quick Preview Option On XMB* option in HFW Tools->Developer. This swaps the explore_plugin.sprx between CEX and DEX versions



v3.2.1

Global Changes

  - Added support for 4.84 DEX firmware
  - Updated DEX resources and stackframe (4.84 DEX/PEX Only) (thanks Joonie)
  - Added support for 4.83 firmware (HFW)
  - Re-added support for 4.82 firmware (OFW)
  - Updates to PS3HEN_GEN and added makefile (thanks bucanero)

Installer Changes

  - Bytes will be written by webkit if HEN is being loaded from HTML, so HEN can set the installing flag
  - Added downloadhenD() function to allow DEX p3t download if DEX checkbox is checked (4.82D/4.84D Only)

HEN Plugin Changes

  - Updated detected COBRA version to 8.4
  - Updated PS3MAPI_CORE_VERSION to 1.24 (thanks bucanero)
  - Added check for HEN installing. Boot plugins text files will be deleted if HEN is ran from installer html
  - Updated UMD/PSP blacklisting and fixed spacing (thanks aldostools)

Payload Changes

  - Added check for webMAN-MOD, and if installed will download package with WMM included, only if HEN is installing
  - Updated peekq offsets and values for CEX/DEX when downloading packages

Resource Changes

  - Added VSH message to alert users of deleted boot plugins text
  - Updated HEN Welcome Message for developer mode/release
  
  

v3.2.0

Global Changes

  - Added support for 4.90 firmware. Special thanks to lmn7 and Joonie for their work on porting offsets, HFW, and other code contributions
  - Xai updated to support new HFW Tools options. Special thanks to Evilnat for his help and code contributions

HEN Plugin Changes

  - Automatic reboot after successful initial HEN installation from Network and USB
  - Added Clear Browser Cache code, currently disabled. This will be moved into xai_plugin (thanks xfrcc)
  - Changes to HEN plugin attempting to make it unload properly (thanks @aldostools, TheRouLetteBoi)
  - Updated host domain name from ps3xploit.com to ps3xploit.me

Payload Changes

  - Added mutex functionality to map_path and open_path_hook (thanks bguerville)
  - Updated, fixed, and optimized map_path and open_path_hook. Also kept support for legacy homebrew that uses map_path (thanks bguerville)
  - Added stat to open_path_hook for DEBUG build only (thanks DeViL303 for the idea and bguerville for the code and implementation)
  - Changed compatibility for modules patching. Firmware versions 4.84-4.88 share values, but 4.89 has its own values now for hashes and sprx patches
  - Added support for custom subchannel data via LSD files (thanks @aldostools)
  - PSX BIOS patched with product code 0x85 for PAL games (thanks @aldostools)
  - Option to force PAL or NTSC including the word in the file name (thanks @aldostools)
  - Added support for .sbi files and improve the performance seeking the custom subchannels (thanks @aldostools)
  - Added toggle for libaudio BT patch (thanks in1975)
  - Updated act.dat restore function (thanks bucanero)
  - Support for rap and RAP extension (lowercase/uppercase) (thanks aldostools)
  - Added button detection on launch. Currently will look for R2 held, to disable boot plugins

Resource Changes

  - HEN Enable and Package Manager have been separated from category_game.xml
  - Package Manager hidden on boot and shows full on HEN launch (thanks LuanTeles, DeViL303)
  - The HEN Enable egg menu item will be shown on boot and will be hidden after the XMB is refreshed. This will be updated later to refresh automatically. (thanks LuanTeles, DeViL303)
  - Added Developer options under HFW Tools -> Developer
  - Added the ability to switch HEN from Release and Debug modes via HFW Tools -> Developer (USB will be added next release)
  - Added the option to remove hen_enable.png to allow install from browser via HFW Tools -> Developer
  - Only supporting Stock and Rebug themes for now until custom colors can be fixed



v3.1.1

HEN Plugin Changes

  - HOTFIX: Updated HEN_REV to 0x0311

Resource Changes

  - Replaced explore_plugin.sprx with OFW version, 4.89 only (Replacement is needed to make sure the old one is overwritten on dirty 4.89 installs)
  - Removed unused RCO files that match OFW (explore_category_psn.rco, explore_category_video.rco, wboard_plugin.rco, xmb_ingame.rco, xmb_plugin_normal.rco)
  - Temporarily fixed display issues with Trophies, Package Manager (it does currently work, but stutters on sub-menu, and has broken icon until HEN enabled), and other XMB items. This fix may have improvements, moving forward. Thanks to everyone who reported issues (aleks1992, Colek, Cyberdev, Farzin, H3N7R1K, LuanTeles, PopCornLover, ReMiX2000, SolidGoldPug, Xjordy13x, Yoti) and to anyone we missed!



v3.1.0

HEN Plugin Changes

  - Updated To Support 4.89 HFW
  - Added act.dat Backup/Restore feature (thanks bucanero)

Payload Changes

  - Updated To Support 4.89 HFW
  - COBRA PS3MAPI Changes
    * Updated To Identify 4.89 Firmware

Resource Changes

  - Added Dump PSID option to HFW Tools
  - Added Toggle Automatic Update option to HFW Tools
  - Updated text on Theme Selector in HFW Tools
  - Added new icons for updated HFW Tools options (thanks xps3riments)
  - Updated RCO files to fix display issues with 4.89 only (thanks sandungas)
    - explore_plugin_full.rco: 44292838814555627FC8F9F9CB632CD8
    - software_update_plugin.rco: D1FAF469796E6894AA1CECCFAC7895EF
  - Updated layout_grid_table files for 480p and 272p to fix display issues in Remote Play with 4.89 only (thanks sandungas)



v3.0.3

HEN Plugin Changes

  - Updated To Support 4.88 HFW

Payload Changes

  - Updated To Support 4.88 HFW
  - COBRA PS3MAPI Changes
    * Updated To Identify 4.88 Firmware



v3.0.2

HEN Plugin Changes

  - Updated To Support 4.87 HFW

Payload Changes

  - Updated To Support 4.87 HFW
  - COBRA PS3MAPI Changes
    * Updated To Identify 4.87 Firmware

Resource Changes

  - Updated HEN Loader category.xml to use new icon (thanks xps3riments)



v3.0.1

HEN Plugin Changes

  - Updated To Support 4.86 HFW

Payload Changes

  - Updated To Support 4.86 HFW
  - COBRA PS3MAPI Changes (thanks to TheRouletteBoi)
    * Added a better set process memory by using the function used to actually write to process, this will allow user to write to memory where writing permissions are disabled.
    * Added ps3mapi_process_page_allocate this function will allocate memory into the eboot process allowing your to write/read/execute code into start_address parameter
    * Added ps3mapi_get_process_module_info which will get the name, module path, module segments, module start and module stop address all in one function
    * Added ps3mapi_create_process_thread to create thread into the process, This is useful if you want to load a small function into the process without needed make and load a sprx module



v3.0.0

Global Changes

  - No Longer Officially Supporting 4.82 Firmware

HEN Plugin Changes

  - Fixed freezing if DVD or CD is already inserted into PS3 when HEN is enabled
  - Showing error message if reply length is too short from server

Payload Changes

  - Fixed Freezing Problems on All Models
  - Fixed Issues With Incompatible Models
  - Improved Sanity Checks



v2.4.0

Global Changes

  - Stage2 Size went from 100kb+ to 90kb

Payload Changes

  - Added VSH patches and disabled signature check of RIF, now other tools are compatible
  - PS3MAPI can now write to VSH text segment like CFW
  - Disabled VSH check in RIF that R and S cant be just 0
  - DLC/PSX games RAP support added
  - Fixed hitching of PSX PAL on NTSC TV and vice versa
  - Removed unnecessary hooks on CellFsOpen/CellFsRead/CellFsClose, possibly increasing stability
  - Speed improvement when loading NPDRM type 2 games (need original or RAP Activated RIF), CPU couldnt generate ECDSA fast enough
  - Fixed issue where people sometimes got stuck downloading games from PSN



v2.3.3 BETA

Payload Changes

  - Remapping HFW XML from /dev_flash/ now instead of /dev_hdd0/

Resource Changes

  - Updated path pointing to ps3hen_updater.xml in hfw_settings.xml



v2.3.2

HEN Plugin Changes

  - Updated To Support 4.85 HFW

Payload Changes

  - Updated To Support 4.85 HFW



v2.3.1

HEN Plugin Changes

  - Fixed the issue when Network is disabled

Payload Changes

  - Now mounts both dev_rewrite & dev_blind to save the scene

Resource Changes

  - Added duplicate icon fix by DeViL303



v2.3.0

Global Changes

  - Exploit init is faster
  - Increased sleep in html, removed from bins

HEN Plugin Changes

  - HEN Updater added with version check
  - Fixed crash that sometimes happened on init
  - If HEN doesnt init an automated soft reboot takes place
  - HEN can be enabled when failed, and ran successively, without reboot
  - Removed infinite loop. One second is 10 tries, otherwise reboot

Payload Changes

  - SELF Decrypter Fix
  - Fixed some blackscreen issues
  - Fixed freezing if someone tries to enable hen successfully twice
  - Optimizations added to how much stack is available to the syscalls (original vs before original-0xd0). Thanks aldostools
  - Handler requests are passed fast, removed many branch conditions there for faster handling
  - Updated extended download plugin patches, per DeViL303 suggestion
  - HEN queue is drained before the patches get disabled, and synchronized properly



v2.2.2

Payload Changes

  - HEN_init freezing fixed by timer change
  - Syscall handler bug fixed, removed 2 second hang on xmb no cleanup thread
  - HashCalc bug fixed, strict hashcheck
  - USB Package installation support for HEN installer

Resource Changes

  - Updated videoplayer_plugin.sprx to use proper DEX version for each firmware version



v2.2.1

Global Changes

  - The stackframe and PS3HEN bins are now merged as a single payload binary (PS3HEN.BIN)
  - Added HEN refresh and version display on initialize, using embedded plugin
  - Replaced dev_blind with dev_rewrite to maintain RW state at all times
  - On Boot, HEN Enabler icon is selected by default

HEN Plugin Changes

  - HEN version notification on boot
  - Refreshes Game and Network Category
  - Enables in-game Screenshot feature
  - Unloads Itself

Payload Changes

  - HEN Installer feature added and memory management changes
  - Fixed Encryption
  - HMAC Hash Validation
  - PSP ISO Launcher Support
  - PS2Classics launcher activation on the fly (thanks aldostools)
  - Impoved compatibility with apps like MultiMan and others which replace syscall 6-10
  - Cleanup thread added and Faster boot times for app increasing stability
  - Embedded buffers and removed memory fragmentation
  - Memory Management of map_path improved
  - Memory Optimization (no embedded buffer for kernel plugin, only allocs when requested)
  - Fail-safe added for stage0 incase stage2 not found (thanks aldostools)
  - Fixed bug where if kernel plugin was more than 64kb it will crash PS3
  - Fixed extern typo of 64mb to 64kb
  - Added missing COBRA patches & BT/USB passthrough support added
  - PS3MAPI bugfix + Stability
  - Self Threading Support. Fixes the issue with a few games (SC Trilogy and etc). Currently ISO/NetISO not supported
  - Improved SELF auth (Fixes games that run multiple executables. Stability improved)

Resource Changes

  - Default Theme Pack removed from main package and can now download from Themes Updater
  - HEN Theme Pack by Itroublve_Hacker downloadable package updated with fixed icons
  - PKG Linker is now located under Package Manager - Install Packages
  - Cleaned Up Unused XML Entries. Added 1 query for external.xml on usb000 (thanks DeViL303)
  - Replaced Manual link from Network column with PS3Xploit Home link
  - Added new coldboot, icons, and JS/HTML overlay (thanks xps3riments)


v2.1.1

Stackframe Binary

  - 4.82 CEX is now supported! Each FW version has its own stackframe, package, and update XML.

PS3HEN Payload

  - PSNPatch is fixed, no more freezing from syscall removal
  - Remap for HFW_settings is now fully protected, no more disappearing HFW tools
  - Stability patches added on initial boot process
  - HEN Check added to not freeze if missing files

Resources

  - PKG Linker entries added to category_game.xml



v2.1.0

Many thanks to Habib who accidentally released v1.0.0 as anonymous ;)

PS3HEN Payload

  - Payload size is reduced by 20kb
  - Advanced QA Flag. This DOES NOT allow downgrading!
  - Debug Settings Enabler added
  - AES calculation now uses internal library from LV2
  - RAP can now be loaded / accessed from dev_hdd0/exdata

Resources

  - Added Update Themes option to PS3HEN Updater menu
  - Added theme pack by "Itroublve Hacker" to PS3HEN Updater -> Update Themes
  - Small text edit on "Theme selector" is now "Theme Selector" under Hybrid Firmware Tools



v2.0.2

Stackframe Binary

  - C00 unlocker activated by default


PS3HEN Payload

  - RAP activation on the fly, default path : usb000/exdata/<rap> or usb001/exdata/<rap>
  - Fixed issue with official NPDRM content rif deletion and unable to boot error
  - PS2 classics launcher support
  - Added @DeViL303's advanced download plugin patches
  - Fixed Install All Packages
  - Fixed explore_plugin patches
  - App restriction on RemotePlay with PC removed
  - Improved games compatibilty e.g COD3
  - Enabling dev_blind by default
  - Multiple path on boot_plugins & boot_plugins_kernel (HDD & USB) Thanks to @aldostools
  - Hybrid Firmware Tools available when HEN's activated (Enable HEN to use this feature) *
    *Only available via PS3HEN PKG installation


Resources

  - Fixed infinite spinning wheel when in-game
  - Both REBUG and Stock Edition available
  - Hybrid Firmware Tools available via PKG installation
  - HEN updater support available under Network Category
  - Official firmware updates via internet blocked



v2.0.1 BETA

  - mappath is used for enabling xai_plugin so it wouldn't appear on fresh boot.
  - Remote Play with PC restriction removed
  - @DeViL303's extended download_plugin support added (offline pkg includes v1.01 HEN edition)
  - Hybrid Firmware Tools (equivalent to CFW settings with less features)
  - Both Stock and REBUG edition (theme) available.
  - webMAN MOD 1.47.20 beta integrated (auto-refresh Game and Network Categories, detection of re-enabled cfw syscalls)
  - Added option to re-enable cfw syscall by accessing the system update menu on XMB Settings



v2.0.0

  - HOTFIX: Removed HEN Check From Offline Packages

  - Fake flash is no longer used, in favor of on-the-fly patching
  - Fixed blackscreen crashes
  - Fixed random recovery kicks
  - ISO support added
  - PS3MAPI support can now read/set process mem using webman
  - KW stealth extensions added
  - Random lv2 panic fixed
  - Added check in html for hen success
  - Kernel plugins support
  - Photo gui opcode support for webman
  - Syscall 389/409 product mode check disabled
  - Opcode 1339 added, returns HEN version (0x0200)
  - Full BD/DVD ISO support (AACS decryption required for BDRip)

  Notes:

  WebmanMOD tested with 1.47.17 and 1.47.19, with fan control and PS3MAPI working



v1.0.0

  - Managunz backup manager works best for jb rips(ISO not supported)!
  - MULTIMAN works too but compatibility is not the same.
  - PSXISO Support is there!!!!
  - BD/DVD Region patches
  - BDISO support(stutter with xmb, use showtime)
  - BOOTPLUGINS WORK location "/dev_usb000/boot_plugins_nocobra.txt"(Use webman original one and not the mod one. also disable - content scan on boot in settings)
  - Discless games work with disc icon!
  - Syscall 6 added
  - Syscall 7 added(address>0x8000000000352230) and disabled overwriting syscall 0->15
  - Syscall 15 added
  - Syscall 8 opcodes added for detection HEN and for advanced lv2 poke(read DEVELOPER SECTION)
  - Whole kernel memory RWX(execute kernel payload like this at high locations or hook syscalls etc)
  - PS3MAPI support for modding
  - Debug PKG install
  - Homebrew resigned for 3.55 and less support!
  - Homebrew Root Flags enabled!
  - HAN PKG insall support
  - PSN Connectivity
  - All process executed after HEN have rwx permissions!
  - HAN Enabled by default!

CFW PATCHES:
  - CFW settings
  - Retail/DEBUG pkg installation
  - Unlink to Delete
  - Remote play with PC
  - Download debug pkg on retail
  - Remote play ignores SFO check
  - Cinavia protection
  - videoplayer_plugin
  - DVD region check (not cracking RCE)
  - REBUG themed RCO & XML
  - AIO copy

  NOTES:
  if you get error 80010017 launching homebrew that simply means HEN failure, restart console and try again!(restart is important!)
  also try deleting cache, browsing data, cookies and the likes from browser, make the exploit page the home page
	
DEVELOPERS:
  - #define SYSCALL8_OPCODE_IS_HEN 0x1337
  - using this if return 0x1337 its hen
		
  - ADVANCED POKE:syscall8(0x7003, addr, value);
	this allows poking any location in lv2 memory BUT you have to restore original value before exiting to another application or exiting to xmb.USE WISELY OTHERWISE PS3 SHUTS DOWN

  - BDMIRROR:Managunz FTW!(please use Cobra payload because by default its MULTIMAN) 	
    NOTE:mounting dev_blind will actually mount dev_flash. change files directly from dev_flash instead or hdd0/plugins/CFW/			
		
  - Kernel Mode returns 0x53434500 on success to user webkit 0x8a000000. its good to measure HEN success. right now hen is already close to or is 100%

# CombatMissionFixes

Fixes for the Steam version of Combat Mission released by SNEG.

Fixes for Combat Mission 2 will come soon.

## Combat Mission 3: Afrika Korps

Combat Mission 3 loses the ability to target with vehicles when you enable WASD. The `cmak.dll` file in your installation directory is a shim that enables this functionality and patches CM3 at runtime. The DLL defines what keyboard keys should be remapped. The <kbd>D</kbd> key (`Hull Down`) is remapped to <kbd>T</kbd> for tanks, so that WASD controls the camera. The fix is to adjust that DLL directly, giving it no key in the rebind for `Hull Down`. The only way to trigger the `Hull Down` command is to right-click on the vehicle and 

As I'm not distributing any binaries, you'll have to apply this patch yourself. I'm using game console ROM hacking technology to apply the patch, as that's quite a large ecosystem of tools.

The patch is in BPS format, which validates you have the correct source file for patching. You can use any rom patching tool that supports BPS files, but I used https://www.marcrobledo.com/RomPatcher.js/ in the creation of the BPS file and in testing.

1. Download the BPS file from the releases here on GitHub.
2. Open https://www.marcrobledo.com/RomPatcher.js/ and click on the **ROM file** box to open the file dialog.
3. Navigate to your game folder (most likely `C:\Program Files (x86)\Steam\steamapps\common\Combat Mission Afrika Korps`) and select the `cmak.dll` file.

   Data for my version of the file, which must match:

   | Hash Type | Hash Value |
   | --- | --- |
   | CRC32 | 54526c62 |
   | MD5 | 650623fdfcfe123bd20875f9ab911eae |
   | SHA-1 | cf95122f5439f3e003d418cc678620627df03110 |

4. Click on the **Patch file** box and open the file dialog.
5. Select the `cmak.bps` file downloaded from this repository.
6. Click **Apply patch**.

   This downloads the file, as a DLL file is output, your browser may try to prevent you from downloading the file as unsafe. Remember, this is a patched version of your own file. You'll have to bypass these checks. Alternatively, you can use some other tool to patch locally and not through a browser.

7. In your game directory, rename your original `cmak.dll` file to something else, as a backup.
8. Move the downloaded file to the game directory and rename it to `cmak.dll`.

# 禁用macOS的一些安全措施


##1.Disable System Integrity Protection.

csrutil disable




## 2.Disable SSV.

csrutil authenticated-root disable



## 3.禁用库验证	
Launch Terminal and enter two following commands:

sudo defaults write /Library/Preferences/com.apple.security.libraryvalidation.plist DisableLibraryValidation -bool true

⁃	This command allows Finder (and all applications) to load arbitrary library.
⁃	By default, Finder can load libraries signed by Apple only.



## 4.开启arm64e的第三方库
sudo nvram boot-args=-arm64e_preview_abi

⁃	Required for Apple silicon Mac.
⁃	Restart after executing this command.
⁃	This command allow system to load third-party Arm64e libraries.
⁃	Apple’s documentation Test your driver extensions on arm64e



注意：开启arm64e的第三方库只适用于arm64的机器！

---


## 关闭交换内存和开启arm64e的第三方库
sudo nvram boot-args=-arm64e_preview_abi\ vm_compressor=2


sudo nvram boot-args="-arm64e_preview_abi vm_compressor=2 amfi_get_out_of_my_way=1 amfi_allow_any_signature=1"

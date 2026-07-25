# LazyIDA
Make your IDA Lazy!

This fork merges functionality from [P4nda0s’ fork](https://github.com/P4nda0s/LazyIDA), which has not been updated for 2 years.

Have quickly tested on IDA Pro 9.3.260421

Please report bug to me!

> [!NOTE] Why stick to LazyIDA?
>
> As the upstream mentioned, this project was written casually 10 years ago.
> 
> Many features are now outdated or built-in:
>
> - Remove return type: Built-in since IDA Pro 7.5+
> - Dump feature: Can be replaced with IDA's built-in `Shift-E`
> - Format string vulnerability scan: Since Hex-Rays decompiler now supports most common architectures, this feature should be reimplemented using Hex-Rays API for better results
>
> But it and its fork do have some QoL functions that I want. So I try to merge functions ;) 

## Installation

1. Clone this repository into your IDA plugins directory:

- **Windows:**  
  `%APPDATA%\Hex-Rays\IDA Pro\plugins\`
- **macOS/Linux:**  
  `~/.idapro/plugins/`

2. Restart IDA.
3. You should find `LazyIDA ({PLUGIN_VERSION}) plugin has been loaded.` in Output window.

# Features

- Functions from [P4nda0s’ fork](https://github.com/P4nda0s/LazyIDA)

    - Jump to other based-address without rebase the idb.

      shortcuts: Shift + G, LazyIDA will copy the address from clipboard, and fill it in 'Target Addr'.

    - lazy dumper, A tool for dump memory to a file, you can specify it size in ui. (No need for script when unpacking)
    - paste data to arbitary address, supports paste from HEX, BASE64, or ASCII
    - Copy RVA (Relative Virtual Address)


  - Remove function return type in Hex-Rays (IDA 7.5+ has this feature built-in):

![2016-06-12 11 05 29](https://cloud.githubusercontent.com/assets/5360374/15991889/2dad5d62-30f2-11e6-8d4b-e4efb0b73c77.png)

  - Convert data into different formats, output will also be automatically copied to the clipboard:

![2016-06-12 11 01 57](https://cloud.githubusercontent.com/assets/5360374/15991854/b813070a-30f1-11e6-931e-08ae85355cca.png)
![2016-06-12 11 03 18](https://cloud.githubusercontent.com/assets/5360374/15991863/e5271146-30f1-11e6-89ac-bafd46eb1e45.png)
  - Scan for format string vulnerabilities:

![2016-06-15 8 19 03](https://cloud.githubusercontent.com/assets/5360374/16064234/da39aa8c-32d1-11e6-89b8-1709cef270f5.png)
  - Jump to vtable functions by double-clicking
  - Lazy shortcuts:
    - Disasm Window: 
      - `w`: Copy address of current line into clipboard
    - Hex-rays Window: 
      - `w`: Copy address of current item into clipboard
      - `c`: Copy name of current item into clipboard
      - `v`: Remove return type of current item

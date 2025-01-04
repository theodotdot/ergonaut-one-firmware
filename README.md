# ZMK Firmware for Ergonaut One keyboard

This is a repository for a ZMK Firmware for Ergonaut One keyboard.

## Default keymap

Visual representation of the default keymap in keyboard-layout-editor: [KLE](http://www.keyboard-layout-editor.com/#/gists/13d0f7ae7a8b5835efcd23d61f50336a)

Below representation was generated with [`keymap-drawer`](https://github.com/caksoylar/keymap-drawer) – check out the automatically generated layouts using the [automated Github workflow](https://github.com/caksoylar/keymap-drawer/tree/main#setting-up-an-automated-drawing-workflow) for each keyboard in the [`keymap-drawer` folder](keymap-drawer/), which is always up to date with the config.

![Keymap Representation](./keymap-drawer/ergonaut_one.svg?raw=true "Keymap Representation")

SVG is created using [keymap drawer](https://github.com/caksoylar/keymap-drawer) and specifically [this link](https://caksoylar.github.io/keymap-drawer?keymap_yaml=H4sIAAAAAAAC_-1W23LaMBB9z1doJjPxC4kD5OpOH4wR4GJs15dc-sIYrAQPtkV8CcMw_Eb_pj_TL6mQFOwE0qTpNJN08nKOtbvaXa3WkrZBS9U0oOpggEI8BVcBCn0wDbIR8MCtF-YIhMEYgflNNO6P0WyAvcSXwBVKkiAV0ylCk8XWNsAJmOMkG-F-6M1wnklgnk7CgHCW5KgCEjxNJVCvgCEO8ygm34cVkI3yaEA-a4ulixQhMMqySSqJ4jWJnw_2hjgSh944xbPQS0QSPfImu37iTVEiDkI8ECMviMUuvOzJZt82obIX-dssgS2exxZ4mDpKrnHs5ZmIY7RYmqEkXZr1ZFVf8i5w5AblrxTPKUKKFtNTvKToUlQpGhRNig1Z6dqmrLB5ws7Qm6T9KU58gQrmpDJyBYwkoMGWA-yO2nIWK41daNquWsibhVwxdMcytELXKnSyxn21KXZWNl-ojaW2OyWjpaJbUqx51krKe-l8KilKK2hCDTps3RHyA49-faN4QVGheMbqRFGn2GO1qrAS7VEUWd2LGKvo0FZkE9IU4jzqX-XxYkPl7_aSztAdaD1WAjqFefNuSyWni3kYhZhIK5Of33-QXp5N0LLZvThdvBGNBZu8I2Wb74dimKxtFZcV0tW5zUsCFK1bDEmDFAPeSoWAVPwJn2RPbc1Quqs5rKWMc331AWTLMs6LvnjzG_G4xrRU3bEVC0K2vI7Rg3zL2rBYNR257GCBevPNLItKRuTC-L0p_3HYH9OqMqoxqjM6YHTI6IjRMaMTRqd8-j5n7qfKHAm77NQQqpxrnOucDzgfcj7ifMz5hPMp533On4V33F_vqEleS0OvJOljf_6J5szQ3F7p4OJjfnT1XH4N_fdNbmryJTm1XZuf5hY8Uw3XZm8deOF8NMyrahqOxJ_hA4yzEHs-SvjxvpNmuR_gfh6HeDjmwpfSRmdrMRvkYaRZq4QbDn1dkgtnsSarbpDVNsjqG2QHz5TVnxljUy53OZeWRIowS_sJSlH2l9V8WNv7btf-OeGpi1oQ_uRG-gVfnf2NGQ8AAA%3D%3D). Use the .keymap link and upload the ergonaut_one.json layout as an override.

This layout is heavily inspired from [Watchman 42-key layout](https://github.com/aroum/Watchman-layouts)

## FAQ

- [FAQ](#faq)
  - [How to change the keymap?](#how-to-change-the-keymap)
  - [How to flash the keyboard?](#how-to-flash-the-keyboard)
  - [How to pair halves?](#how-to-pair-halves)
  - [Problems](#problems)
    - [I'm getting File Transfer Error after copying firmware to the keyboard](#im-getting-file-transfer-error-after-copying-firmware-to-the-keyboard)

### How to change the keymap?

1. Fork or use this repository as a template https://github.com/ergonautkb/one-zmk-config.
2. Enable Github Actions for your repository.

You have two options on how to configure your desired keymap:

#### Option 1. Keymap Editor

1. Open [Keymap Editor](https://nickcoutsos.github.io/keymap-editor/).
2. Connect it to your Github account and give an access to your repository to Keymap Editor's app.
3. Make changes to your keymap and press `Save` - it will trigger software build. Wait for it to complete.
4. Grab the `firmware.zip` archive.

#### Option 2. Manual

1. Make changes to the [ergonaut_one.keymap](config/ergonaut_one.keymap) file using your favorite text editor.
2. Commit changes to your repository.
3. Go to `Actions` tab in your Github repository, locate the latest build and wait for it to complete.
4. Grab the `firmware.zip` archive

### How to flash the keyboard?

1. Obtain `firmware.zip`
2. Unzip `firmware.zip` - you should have `ergonaut_one_left-seeeduino_xiao_ble-zmk.uf2` and `ergonaut_one_right-seeeduino_xiao_ble-zmk.uf2` files
3. Turn off the power for selected halve (move slider to position `OFF`)
4. Connect selected halve to the PC via USB-C cable
5. Press `RESET` button **twice** to enter DFU mode - you should see new USB device in your file manager
6. Copy the corresponding firmware to the root directory of the new USB device
7. Disconnect selected halve from the PC
8. Repeat steps 3-7 for the other halve

### How to pair halves?

1. Turn off the power for both halves (move slider to position `OFF`)
2. Turn on the power for both halves (move slider to position `ON`)
3. Press `RESET` button **once** on both halves **simultaneously**

### Problems

#### I'm getting File Transfer Error after copying firmware to the keyboard

It's OK. Proof: https://zmk.dev/docs/troubleshooting#file-transfer-error

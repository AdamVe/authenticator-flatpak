# authenticator-flatpak
A testing repository for building flatpak for Yubico Authenticator. The goal is to create a version which supports all functionality and contribute the findings to existing Flathub project. The version of Yubico Authenticator in this flatpak is 7.0.0.

## Supported features

1. working with OATH accounts, Passkeys, Fingerprints, OTP slots and PIV certificates
2. managing OATH password and FIDO PIN
3. changing YubiKey configuration
4. scanning OATH QR code by taking screenshots
5. using custom icon packs for OATH accounts

NOTE: the features depend on connected YubiKey

## Build
To build you will need `flatpak`, `flatpak-builder` and standard Linux development environment.
Basic build is executed with following command:
```
flatpak-builder --force-clean build-dir com.yubico.yubioath.yml
```
Running without installation:
```
flatpak-builder --run build-dir com.yubico.yubioath.yml authenticator
```
Install and run
```
flatpak-builder --user --install --force-clean build-dir com.yubico.yubioath.yml authenticator
flatpak run com.yubico.yubioath
```
Uninstall
```
flatpak uninstall com.yubico.yubioath
```
Create a bundle
```
flatpak build-bundle ~/.local/share/flatpak/repo authenticator.flatpak com.yubico.yubioath
```

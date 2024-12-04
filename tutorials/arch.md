
## 1. Nainstalujte potřebné balíčky

Ujistěte se, že máte nainstalované potřebné balíčky:
```bash
sudo pacman -S networkmanager network-manager-applet wpa_supplicant
```

Ujistěte se, že NetworkManager běží:
```bash
sudo systemctl enable --now NetworkManager
```

## 2. Zjistěte připojené rozhraní (interface)

V tuto chvíli nás zajímá Ethernetové připojení...

```bash
nmcli device status | grep en
```

![status](https://github.com/josefzemanp/8021X-guide/blob/main/screen3.png?raw=true)
*en → Označuje Ethernetové připojení (kabelové rozhraní).*

## 3. Otevřete NetworkManager GUI
Můžete ho otevřít přes příkaz:
```bash
nm-connection-editor
```

![w](https://github.com/josefzemanp/8021X-guide/blob/main/screen1.png?raw=true)


## 4. Rozklikněte connection podle rozhraní (v sekci Ethernet)

![w1](https://github.com/josefzemanp/8021X-guide/blob/main/screen5.png?raw=true)

## 5. Přejděte na sekci **802.1X Security** v horním navigátoru a nastavení proveďte podle vzoru

Authentication -> **Protected EAP (PEAP)**\
Inner authentication -> **MSCHAPv2** \
Username -> **email ze školy** \
Password -> **!heslo od školního počítače!**

![w1](https://github.com/josefzemanp/8021X-guide/blob/main/screen4.png?raw=true)

## 6. Zkuste provést ping pro ověření připojení

```bash
ping 8.8.8.8
```

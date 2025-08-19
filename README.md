# 🎮 RetroPie no Raspberry Pi 3  

Transforme sua **Raspberry Pi 3** em um console retrô com o **RetroPie**.  
Este guia mostra como instalar, configurar e transferir jogos (ROMs) para jogar clássicos como Mario, Sonic, Street Fighter e muito mais.  

---

## 📦 Requisitos  

- Raspberry Pi 3 (com fonte de alimentação e cartão microSD 16GB ou mais)  
- Teclado e mouse USB  
- Monitor ou TV com entrada HDMI  
- Controle USB ou Bluetooth (ex: DualShock, Xbox, genérico)  
- Pendrive (opcional, para transferir jogos)  
- Conexão com internet  

---

## 🔧 Instalação do RetroPie  

1. **Baixe a imagem do RetroPie**:  
   👉 [https://retropie.org.uk/download/](https://retropie.org.uk/download/)  

2. **Grave no cartão microSD** usando o [Raspberry Pi Imager](https://www.raspberrypi.com/software/) ou [balenaEtcher](https://etcher.balena.io/).  

3. Insira o cartão na Raspberry Pi, conecte teclado, mouse, monitor e ligue.  

4. Na primeira inicialização, configure:  
   - Layout do teclado / Mapear botões  
   - Rede Wi-Fi ou cabo Ethernet (necessário se for acessar via SSH)  
   - Resolução da tela  

---
Pressione F4 para entrar no cmd do RetroPie
## 🎛️ Configuração inicial  

1. Conecte seu **controle USB ou Bluetooth**.  
2. Siga as instruções para mapear os botões.  
3. Reinicie se necessário.  `sudo reboot now` 

---

## 📂 Transferindo jogos (ROMs) para o RetroPie  

Você pode enviar os jogos (ROMs) de várias formas:  

- Via **pendrive** (mais simples)  
- Via **rede (Samba share)**  
- Via **SSH**  

Aqui vamos usar o método **pendrive**.  

---

### 1. Criar pasta de montagem do USB  

No meu caso, criei manualmente a pasta `/media/usb` para montar o pendrive. Ela é criada ao lado na pasta `/home/pi`, ficando ao lado da pasta principal "RetroPie".

Ao acessar, temos que "montar o pendrive", informando onde devem ser colocados os arquivos, que será na pasta nova criada. Para isso, fazemos:

```bash

sudo mkdir -p /media/usb
sudo mount -t vfat /dev/sda /media/usb
cp /media/usb/*.gba /home/pi/RetroPie/roms/gba/
sudo umount /media/usb

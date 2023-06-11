Criação Hackintosh Notebook Acer A515-54G

Modelo do equipamento (Especificações):

* Core i7 10th 10510U (1GHz ~ 3.4GHz)
* 20GB memória RAM DDR4 (2133MHz)
* Modelo: Aspire A515-54G-77RU
* Resolução de tela: 1920x1080 15"
* 512GB SSD NVMe M.2 2280 Wester Digital Black SN770
* Placa de vídeo (Onboard) Intel UHD 630
* Placa de vídeo (Onboard) NVIDIA MX250 (Incompatível - Desativado)
* Placa de som ALC255
* Placa de Wifi/Bluetooth BMC9436NG (1200MBPs) 2.4Ghz/5GHz bluetooth v4
* Webcam 720p (HD User Facing)
* 4 Portas USB 2.0/3.0 (3x USB-A  | 1x USB-C )
* 1 Porta HDMI


Versão do sistema operacional utilizada na EFI:

Mac OS Ventura 13.4 (22F66)


O que está funcionando:

- Portas USB-A e USB-C (Ideal é efetuar o mapeamento das portas sempre)
- Porta HDMI
- Webcam
- SSD WD Black NVMe M.2 2280 512Gb (Foi trocado por esse modelo para melhorar desempenho 3500Mbps leitura e gravação )
- Wifi BMC9436NG (Foi adicionada para melhor compatibilidade, Intel funciona em modo compatibilidade);
- Placa de rede 10/100/1000 RTL8111
- Placa vídeo UHD 630 (Onboard) funcionando HEVC e H264
- Tela em Full HD (1920x1080)
- Teclado ABNT2 Português Brasil
- Touchpad
- Combojack

O que não está funcionando:

- Placa vídeo Nvidia MX250

Desativado via SSDT

Uso do equipamento:

Para desenvolvimento de simples aplicações (desenvolvimento app), uso Microsoft 365, Reuniões on-line, Pequenas virtualizações (Virtualbox e Parallells).
Ao ligar equipamento demora em média 20-25 (segundos) para ligar
Bateria dura em média 4h~4h30 (Uso brilho em 70%)

Configuração BIOS:

S-ATA: AHCI
Secure Boot: Disable
Fast-Boot: Disable

Ferramentas a serem utilizadas:

Tabela ACPI - https://www.acpica.org/downloads/binary-tools
Tabela SSDT - https://github.com/corpnewt/SSDTTime
Editar Config.plist - https://github.com/corpnewt/ProperTree
Gerar SMBIOS - https://github.com/corpnewt/GenSMBIOS
Ajustes Hackintool: https://github.com/benbaker76/Hackintool
Pacote opencore (Bootloader): https://github.com/acidanthera/OpenCorePkg
Kexts: https://github.com/orgs/acidanthera/repositories

1º Passo:

Caso seu equipamento seja exatamente o mesmo (A515-54G-77RU) o arquivo EFI irá funcionar possivelmente funcionar sem a necessidade de muitas alterações.

Recomendo a leitura do guia de instalação:

https://dortania.github.io/OpenCore-Install-Guide/

Acesse o site:

https://www.olarila.com/topic/6278-olarila-vanilla-images-macos-installer/

Efetue o download da versão desejada do Mac OS (Utilizei o Mac OS Ventura)


2º Passo:

Extraia a tabela DSDT do seu equipamento, para isso recomenda a leitura da documentação:

https://dortania.github.io/Getting-Started-With-ACPI/

Irá utilizar o seguinte software ainda com o Windows (Para outros sistemas consulte a documentação acima) em funcionamento para extrair:

acesse ACPICA.org (https://www.acpica.org/downloads/binary-tools), efetue o download do iASL compiler, rode o seguinte comando no terminal do windows:

> acpidump.exe -b -n DSDT -z

com a tabelas DSDT cria as SSDT com base na documentação ACPI do Dortania, utilizando o SSDTIME:

Utilize a documentação a seguir para efetuar:

https://github.com/corpnewt/SSDTTime
https://dortania.github.io/Getting-Started-With-ACPI/

3º Passo:

Já com o primeiro passo feito (Criação do pendrive bootavél) insira as SSDT necessárias no pasta EFI >> OC >> ACPI
Agora é necessário adicionar as kexts básicas para o funcionamento do Hackintosh, no caso deste modelo foi utilizado:

- AirportBrcmfixup (https://github.com/acidanthera/AirportBrcmFixup) - Foi necessário pois algumas vezes a hibernação não retornava
- AppleALC (https://github.com/acidanthera/AppleALC) Layout ID utilizado: 71
- BrightnessKeys (https://github.com/acidanthera/BrightnessKeys)
- CpuTscSync (https://github.com/acidanthera/CpuTscSync)
- ECEnabler (https://github.com/1Revenger1/ECEnabler)
- HibernationFixup (https://github.com/acidanthera/HibernationFixup)
- Lilu (https://github.com/acidanthera/Lilu)
- NVMeFix (https://github.com/acidanthera/NVMeFix)
- RealtekRTL8111 (https://github.com/Mieze/RTL8111_driver_for_OS_X/releases)
- RestrictEvents (https://github.com/acidanthera/RestrictEvents)
- SMCBatteryManager (https://github.com/acidanthera/VirtualSMC)
- SMCProcessor (https://github.com/acidanthera/VirtualSMC)
- SMCSuperIO (https://github.com/acidanthera/VirtualSMC)
- VerbStub (Utilize o combojack para ajustar o combojack P2 do equipamento : https://github.com/hackintosh-stuff/ComboJack)
- VirtualSMC (https://github.com/acidanthera/VirtualSMC)
- VoodooI2C (https://github.com/acidanthera/VoodooPS2)
- VoodooI2CHID (https://github.com/VoodooI2C/VoodooI2C)
- VoodooPS2Controller (https://github.com/acidanthera/VoodooPS2)
- WhateverGreen (https://github.com/acidanthera/WhateverGreen)







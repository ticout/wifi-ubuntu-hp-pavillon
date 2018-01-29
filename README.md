# Install wifi drivers [10ec:d723] ubuntu 

> HP Pavillon 15-cc507nf 15.5": 
> Driver missed for network cotroller: Network controller [0280]: Realtek Semiconductor Co., Ltd. Device [10ec:d723]

> 

### REQUIREMENTS

- kernel 4.11
- For network controller Realtek Device [10ec:d723]

:question: How to know Network controller?
` lspci -vnn | grep Network`

### Install process
:bulb: 
```bash
 git clone https://github.com/smlinux/rtl8723degit clone https://github.com/smlinux/rtl8723de
cd rtl8723de
make
sudo make install
sudo modprobe -v 8723de
cd ..
sudo apt install dkms
sudo dkms add ./rtl8723de
sudo dkms install rtl8723de/5.1.1.8_21285.20171026_COEX20170111-1414
sudo depmod -a
sudo reboot
```

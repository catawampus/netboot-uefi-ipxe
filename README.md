# ipxe netboot

ipxe menu script and boot binary

git clone https://github.com/ipxe/ipxe.git

edit configuration include files

```
src/config/console.h
#define       CONSOLE_FRAMEBUFFER     /* Graphical framebuffer console */
src/config/general.h
#define CONSOLE_CMD           /* Console command */
```

build

```
cd src
echo '#!ipxe\n\ndhcp\ntftp://${next-server}/ipxe/ipxe.cfg' > ipxe.boot
make bin-x86_64-efi/snponly.efi EMBED=ipxe.boot
```

create ipxe dir at root of tftp and add snponly.efi and ipxe.cnf

CC=arm-none-eabi-gcc
CP=arm-none-eabi-g++
OC=arm-none-eabi-objcopy
OD=arm-none-eabi-objdump
LD=arm-none-eabi-ld

all:
	$(CC) -g *.c -c -march=armv6z -O2 -ffast-math -std=c99 -Wall -march=armv6k -mtune=mpcore -mfloat-abi=hard -mtp=auto
	$(CC) -g *.s -c -march=armv6z -march=armv6k -mtune=mpcore -mfloat-abi=hard -mtp=auto
	$(CC) -T 3ds.ld *.o -march=armv6k -mtune=mpcore -mfloat-abi=hard -mtp=auto
	mkdir -p ../romfs
	$(OC) --set-section-flags .bss=alloc,load,contents -O binary a.out ../romfs/arm11.bin
	rm *.out *.o

clean:
	rm *.out *.o

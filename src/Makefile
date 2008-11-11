obj-m:= tarfs.o

KDIR:= /lib/modules/${shell uname -r}/build
PWD:= ${shell pwd}
tarfs-objs:= file.o inode.o super.o dir.o tarent.o namei.o
HEADERS:= tarfs.h tarinf.h

TARGET:= tarfs.ko
clean-files:= *.o *.ko *.mod.[co] *~

all: ${TARGET}

${tarfs-objs}: ${HEADERS}
	${MAKE} -C ${KDIR} M=${PWD}

tarfs.ko: ${tarfs-objs}
          ${MAKE} -C ${KDIR} M=${PWD} modules

clean:
	rm -rf ${clean-files}

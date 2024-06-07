obj-m += kern_net.o

all: kernel_module user_program

kernel_module:
	make -C /lib/modules/$(shell uname -r)/build M=$(PWD) modules

user_program: usr_net
	gcc -o usr_net usr_net.c

usr_net: usr_net.c

clean:
	make -C /lib/modules/$(shell uname -r)/build M=$(PWD) clean
	rm -f usr_net kern_net.ko
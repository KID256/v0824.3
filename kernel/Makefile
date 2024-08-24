obj-m += motion_sensor.o

USER_PROGRAM_PATH := ../system
USER_PROGRAM := $(USER_PROGRAM_PATH)/user_program

all: modules user_program

modules:
	make -C /lib/modules/$(shell uname -r)/build M=$(PWD) modules

user_program:
	gcc -o $(USER_PROGRAM) $(USER_PROGRAM_PATH)/user_program.c

clean:
	make -C /lib/modules/$(shell uname -r)/build M=$(PWD) clean
	rm -f $(USER_PROGRAM)
FILES = simple_file.o pecoff.o guid.o sha256.o console.o \
	execute.o configtable.o shell.o
ifeq ($(ARCH),x86_64)
FILES += security_policy.o
endif
LIBFILES = $(FILES) kernel_efivars.o
EFILIBFILES = $(patsubst %.o,%.efi.o,$(FILES)) variables.o 

include ../Make.rules

lib.a: $(LIBFILES)
lib-efi.a: $(EFILIBFILES)

clean:
	rm -f lib.a
	rm -f lib-efi.a
	rm -f $(LIBFILES)
	rm -f $(EFILIBFILES)


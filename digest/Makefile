CPP= g++
CPPDEFINES= -D_GNU_SOURCE -D_REENTRANT
CPPINCLUDES= -I../include -I/usr/local/include
CPPFLAGS= -Wall -g -MMD -std=c++11 -fPIC $(CPPDEFINES) $(CPPINCLUDES)

CPP_SOURCES= SHA1.cc SHA256.cc SHA384.cc SHA512.cc DigestBase.cc
CPP_OBJECT= $(CPP_SOURCES:.cc=.o)
DEPEND= $(CPP_OBJECT:.o=.d)

.PHONY: clean

all: $(CPP_OBJECT)

$(CPP_OBJECT): %.o: %.cc
	$(CPP) -c $(CPPFLAGS) -o $@ $<

clean:
	-rm -f $(CPP_OBJECT) $(DEPEND) $(PROGRAM)

-include $(DEPEND)

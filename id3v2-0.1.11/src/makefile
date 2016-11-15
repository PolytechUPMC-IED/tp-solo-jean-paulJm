ID3= /home/sasl/shared/main3/env/tools
CC= g++
CFLAGS= -Wall
LDLIBS= /lib
CLIBS= /include
TPSOLO= /home/sasl/eleves/main/3672607/TP_solo/bin
EXEC= /home/sasl/eleves/main/3672607/TP_solo/EnvDev/id3v2-0.1.11/src/id3v2
MAN= /home/sasl/eleves/main/3672607/TP_solo/man/man1
all : list.o convert.o id3v2.o genre.o id3v2

list.o : list.cpp
	${CC}  -I/${ID3}${CLIBS} -DVERSION="\"${VERSION}\"" -c -o list.o list.cpp

convert.o : convert.cpp
	${CC} -I/${ID3}${CLIBS} -DVERSION="\"${VERSION}\"" -c -o convert.o convert.cpp

id3v2.o : id3v2.cpp
	${CC} -I/${ID3}${CLIBS} -DVERSION="\"${VERSION}\"" -c -o id3v2.o id3v2.cpp

genre.o : genre.cpp
	${CC} -I/${ID3}${CLIBS} -DVERSION="\"${VERSION}\"" -c -o genre.o genre.cpp

id3v2 : convert.o list.o id3v2.o genre.o 
	
	${CC} -L${ID3}${LDLIBS} ${CFLAGS} -o id3v2 convert.o list.o id3v2.o genre.o -lid3 -lz

install : id3v2 
	
	cp ${EXEC} ${TPSOLO}
	nroff -man /home/sasl/eleves/main/3672607/TP_solo/EnvDev/id3v2-0.1.11/id3v2.1 > ${MAN}/id3v2.1

distclean : 
	-rm -f ${TPSOLO}/id3v2
	-rm -f ${MAN}/id3v2.1
	-rm -f convert.o list.o id3v2.o genre.o id3v2
clean: 
	-rm -f convert.o list.o id3v2.o genre.o id3v2

.PHONY :clean

#8.on realise la commande mv  LD_LIBRARY_PATH /home/sasl/shared/main3/env/tools/lib
#9. 


OBJ_DIR = ../obj
STATIC_LIB = ${OBJ_DIR}/libpcmalloc.a
DYNAMIC_LIB = ${OBJ_DIR}/libpcmalloc.so
TARGET = ${STATIC_LIB} ${DYNAMIC_LIB}
PAPI_PATH = /usr/local/papi/include

OBJS = ${patsubst %.c,${OBJ_DIR}/%.o,${wildcard *.c}}
LIBS =
#CFLAGS = -Wall -lm -g -fPIC -Wformat -lpapi -O2
CFLAGS = -Wall -lm -g -fPIC -Wformat -lpapi
CC = gcc

all : ${TARGET}


${OBJ_DIR}/%.o : %.c
	${CC} -c ${CFLAGS} $< -o ${OBJ_DIR}/$@ -I${PAPI_PATH}


${STATIC_LIB} : ${OBJS}
	ar -r -o $@ $^

${DYNAMIC_LIB} : ${OBJS}
	${CC} -fPIC -shared -o $@ $^ -ldl -I${PAPI_PATH}

.PHONY: all


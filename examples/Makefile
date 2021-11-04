CXX = g++
CXXFLAGS = -O3
LDLAGS = -O3
PRG_NAME = examples
BIN_DIR = bin
OBJ_DIR = obj
SOURCES = $(wildcard *.c)
OBJS = $(patsubst %.c,$(OBJ_DIR)/%.o,$(SOURCES))

all: $(BIN_DIR)/examples

$(BIN_DIR)/examples: $(OBJS)
	export LD_LIBRARY_PATH=./../library/bin
	gcc obj/example.o -o bin/example -lmylib -L./../library/bin
	gcc obj/minigzip.o -o bin/minigzip -lmylib -L./../library/bin


$(OBJ_DIR)/%.o: %.c dirmake
	gcc -c $< -o $@

#all: $(BIN_DIR)/$(PRG_NAME)
#
#$(BIN_DIR)/$(PRG_NAME): $(OBJS)
#	$(CXX) $(OBJS) libmylib.dll -L. -o $(BIN_DIR)/test1
#
#
#$(OBJ_DIR)/%.o: %.c dirmake
#	$(CXX) -c $(CXXFLAGS) $< -o $@

dirmake:
	@mkdir -p $(BIN_DIR)
	@mkdir -p $(OBJ_DIR)
CXX := gcc
AR := ar
CXXFLAGS := -O3
PRG_NAME := libmylib.a
PRG_NAME_DY := libmylib.dll
BIN_DIR := bin
OBJ_DIR := obj
SOURCES :=  $(wildcard *.c)
OBJS := $(patsubst %.c,$(OBJ_DIR)/%.o,$(SOURCES))


all:  $(PRG_NAME) $(PRG_NAME_DY)

$(PRG_NAME): $(OBJS)
	$(AR) -rcs -o $(BIN_DIR)/$@ $^
$(PRG_NAME_DY): $(OBJS)
	$(CXX) -shared -fPIC -o $(BIN_DIR)/$@ $^

$(OBJ_DIR)/%.o : %.c dirmake
	$(CXX) -c $< -o $@ $(CXXFLAGS) -fPIC

dirmake:
	@mkdir -p $(BIN_DIR)
	@mkdir -p $(OBJ_DIR)

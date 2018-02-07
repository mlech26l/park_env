
SRCDIR   = src
OBJDIR   = obj
BINDIR   = bin

TARGET_LIB   = park_gym.so

OPT = -O3
CXX       = g++
# compiling flags here
CFLAGS   =  -pthread -std=c++11 $(OPT) -Wall -fPIC -I. -I/usr/include/python2.7/


LINKER   = g++ -o
# linking flags here
LFLAGS   = -pthread -Wall $(OPT)

SOURCES  := $(wildcard $(SRCDIR)/*.cpp)
INCLUDES := $(wildcard $(SRCDIR)/*.h)
OBJECTS  := $(SOURCES:$(SRCDIR)/%.cpp=$(OBJDIR)/%.o)

rm       = rm -f


all: $(BINDIR)/$(TARGET_LIB)

$(BINDIR)/$(TARGET_LIB): $(OBJECTS)
	g++ -shared $(LFLAGS) -Wl,-soname,$(TARGET_LIB) -o bin/$(TARGET_LIB) $(OBJECTS) -lpython2.7 -lboost_python
	@echo "Built lib successfully!"

$(OBJECTS): $(OBJDIR)/%.o : $(SRCDIR)/%.cpp
	$(CC) $(CFLAGS) -c $< -o $@
	@echo "Compiled "$<" successfully!"

clean:
	rm -f bin/$(TARGET_LIB)
	rm -f obj/*.o



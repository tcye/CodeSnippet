#------------------------------------------------------------------------
#	Set the Right Directories
#------------------------------------------------------------------------
DIR_OBJ = ./#obj
DIR_BIN = ./#bin
DIR_INC = ./#inc
DIR_SRC = ./#src

#------------------------------------------------------------------------
#	Set the cxxflags and dependent libs
#------------------------------------------------------------------------
CXXFLAGS = -O2 -g -Wall -fmessage-length=0 -std=c++1y -I$(DIR_INC) -fopenmp
LIBS = opencv_core opencv_highgui opencv_features2d pthread

#------------------------------------------------------------------------
#	Set the objective bin names and dependences
#------------------------------------------------------------------------
OBJ = compute_feature.o utils.cpp
BIN = compute_feature

#------------------------------------------------------------------------
#	Process the Dirs
#------------------------------------------------------------------------
LIBS := $(LIBS:%=-l%)
DIRS := $(DIR_OBJ) $(DIR_BIN)

OBJ := $(OBJ:%=$(DIR_OBJ)/%)
BIN := $(BIN:%=$(DIR_BIN)/%)

#------------------------------------------------------------------------
#	Target
#------------------------------------------------------------------------
all: $(BIN)

$(BIN): $(OBJ)
	$(CXX) $(CXXFLAGS) -o $@ $^ $(LIBS)

$(DIR_OBJ)/%.o: $(DIR_SRC)/%.cpp
	$(CXX) $(CXXFLAGS) -c -o $@ $^

#------------------------------------------------------------------------
#	Clean
#------------------------------------------------------------------------
clean:
	rm -f $(DIR_OBJ)/*.o
.PHONY: clean

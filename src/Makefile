include ../Makefile.config

LIB_TARGET=liblgmtray.a
LIB_OBJECTS=GMailXmlParser.o CURLMessageGetter.o MessageManager.o FreeDesktopTray.o Timer.o ConfigManager.o ConfigFileReader.o

TARGET=lgmtray
TARGET_OBJECTS=main.o liblgmtray.a

$(TARGET): $(TARGET_OBJECTS)
	$(CXX) -o $(TARGET) $(TARGET_OBJECTS) $(LDFLAGS)

$(LIB_TARGET): $(LIB_OBJECTS)
	ar cr $@ $(LIB_OBJECTS)

clean:
	-rm -rf $(TARGET_OBJECTS) $(TARGET) $(LIB_OBJECTS) $(LIB_TARGET)
	$(MAKE) -C unittest clean

check: $(LIB_TARGET)
	$(MAKE) -C unittest check

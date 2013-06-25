CXX = cl.exe
LINK = link.exe

CPPFLAGS = -D_WIN32 -D_USRDLL -DFOO_DLL -DFOO_EXPORTS
CXXFLAGSALL = -nologo -EHsc -GS -W3 $(CPPFLAGS)
CXXFLAGSDBG = -MDd -Od -Z7 -RTCcsu
CXXFLAGSOPT = -MD -O2
#CXXFLAGS = $(CXXFLAGSALL) $(CXXFLAGSDBG)
CXXFLAGS = $(CXXFLAGSALL) $(CXXFLAGSOPT)

LINKFLAGSALL = /nologo /DLL
LINKFLAGSDBG = /DEBUG
LINKFLAGSOPT =
#LINKFLAGS = $(LINKFLAGSALL) $(LINKFLAGSDBG)
LINKFLAGS = $(LINKFLAGSALL) $(LINKFLAGSOPT)

all: cpputil.dll

cpputil.dll: fastpool.obj im2col.obj
    $(LINK) $(LINKFLAGS) fastpool.obj im2col.obj /OUT:cpputil.dll

fastpool.obj: fastpool.cpp
    $(CXX) $(CXXFLAGS) -c fastpool.cpp
    
im2col.obj: im2col.cpp
    $(CXX) $(CXXFLAGS) -c im2col.cpp

clean:
    -erase /Q *.obj *.dll *.exp *.lib
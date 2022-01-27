
To run the above Dockerfile, run the command:
```
docker build -t samtools .
```

## Types of errors you will occur and how to fix them

The RUN install command had the following at first
```
RUN apt-get update && apt-get install -y \
wget \
make && \
rm -rf /var/lib/apt/lists/*
```

The following errors occured and more installations were needed.

configure: error: no acceptable C compiler found in $PATH
```
RUN apt-get update && apt-get install -y \
build-essential \
wget \
make && \
rm -rf /var/lib/apt/lists/*
```

The 'samtools tview' command uses the curses text user interface library.
Building samtools with tview requires curses/ncurses/etc development files
to be installed on the build machine; you may need to ensure a package such
as l*ibncurses5-dev* (on Debian or Ubuntu Linux) or ncurses-devel (on RPM-based
Linux distributions) is installed.
```
RUN apt-get update && apt-get install -y \
build-essential \
wget \
libncurses5-dev \
make && \
rm -rf /var/lib/apt/lists/*
```

Samtools uses compression routines from the zlib library <http://zlib.net>.
Building samtools requires zlib development files to be installed on the build
machine; you may need to ensure a package such as *zlib1g-dev* (on Debian or
Ubuntu Linux) or zlib-devel (on RPM-based Linux distributions) is installed.
```
RUN apt-get update && apt-get install -y \
build-essential \
wget \
libncurses5-dev \
zlib1g-dev \
make && \
rm -rf /var/lib/apt/lists/*
```

The CRAM format may use bzip2 compression, which is implemented in HTSlib
by using compression routines from libbzip2 <http://www.bzip.org/>.
Building HTSlib requires libbzip2 development files to be installed on the
build machine; you may need to ensure a package such as *libbz2-dev* (on Debian
#or Ubuntu Linux) or bzip2-devel (on RPM-based Linux distributions or Cygwin)
is installed.
```
RUN apt-get update && apt-get install -y \
build-essential \
wget \
libncurses5-dev \
zlib1g-dev \
libbz2-dev \
make && \
rm -rf /var/lib/apt/lists/*
```

Building HTSlib requires liblzma development files to be installed on the
build machine; you may need to ensure a package such as *liblzma-dev* (on Debian
or Ubuntu Linux), xz-devel (on RPM-based Linux distributions or Cygwin), or
xz (via Homebrew on macOS) is installed; or build XZ Utils from source.
Either configure with --disable-lzma (which will make some CRAM files
produced elsewhere unreadable) or resolve this error to build HTSlib.
configure: error: ./configure failed for htslib-1.9
```
RUN apt-get update && apt-get install -y \
build-essential \
wget \
libncurses5-dev \
zlib1g-dev \
libbz2-dev \
liblzma-dev \
make && \
rm -rf /var/lib/apt/lists/*
```

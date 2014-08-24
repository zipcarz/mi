mi
==-BIN = /Developer/Platforms/iPhoneOS.platform/Developer/usr/bin
2		-GCC_BIN = $(BIN)/gcc-4.2
3		-#GCC = $(GCC_BASE) -arch armv6
4		-GCC = $(GCC_BASE) -arch armv7
5		-GCC_UNIVERSAL = $(GCC_BASE) -arch armv6 -arch armv7
6		-GCC_NATIVE = gcc
7		-SDK=/Developer/Platforms/iPhoneOS.platform/Developer/SDKs/iPhoneOS4.3.sdk/
1	+GCC_BIN=`xcrun --sdk iphoneos --find gcc`
2	+GCC_UNIVERSAL=$(GCC_BASE) -arch armv7 -arch armv7s -arch arm64
3	+SDK=`xcrun --sdk iphoneos --show-sdk-path`
8	4	 
9	5	 CFLAGS = 
10		-GCC_BASE = $(GCC_BIN) -Os $(CFLAGS) -Wimplicit -isysroot $(SDK) -F$(SDK)System/Library/Frameworks -F$(SDK)System/Library/PrivateFrameworks
6	+GCC_BASE = $(GCC_BIN) -Os $(CFLAGS) -Wimplicit -isysroot $(SDK) -F$(SDK)/System/Library/Frameworks -F$(SDK)/System/Library/PrivateFrameworks
11	7	 
12	8	 all: dumpdecrypted.dylib
13	9	 

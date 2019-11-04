# tsschecker  
_tsschecker is a powerful tool to work with signing technology on iOS/tvOS/watchOS devices._

Latest compiled version can be found [here](https://github.com/s0uthwest/tsschecker/releases). Windows & Linux version are supported, but I won't compile it.

## Features  
* Allows you to get lists of all iOS/tvOS/watchOS versions for a specific device.
* Can check signing status for default iOS/tvOS/watchOS versions.
* Works without specifying any device relevant values to check signing status, but can be used to save signing tickets when given an ECID and the option `--print-tss-response` (although there are better tools to do this).
* __If you'll want to save signing tickets with recommended ApNonces, please, see [this file](https://github.com/s0uthwest/tsschecker/blob/master/nonces.txt).__

tsschecker isn't only meant to be used to check signing status, but also to explore Apple's TSS servers.
By using all of its customization possibilities, you might discover a combination of devices and iOS versions that is now getting signed but wasn't getting signed before.  

# Dependencies
*  ## Bundled Libs
  * [tss](https://github.com/libimobiledevice);
* ## External Libs
  * [libcurl](https://github.com/curl/curl);
  * [libplist](https://github.com/libimobiledevice/libplist);
  * [libfragmentzip](https://github.com/s0uthwest/libfragmentzip);
  * [openssl](https://github.com/openssl/openssl) or commonCrypto on macOS/OS X;
  * [libirecovery](https://github.com/s0uthwest/libirecovery);
* ## Submodules
  * [jssy](https://github.com/tihmstar/jssy)

## Compiling & installing
Open terminal and execute the command: `./autogen.sh && make` or use Xcode project.
The easiest way to install on macOS is using [`brew`](https://brew.sh): `brew install stek29/idevice/tsschecker-s0uthwest`.

### Some about [cURL](https://github.com/curl/curl)
* Linux: Follow [this guide](https://dev.to/jake/using-libcurl3-and-libcurl4-on-ubuntu-1804-bionic-184g) to use tsschecker on Ubuntu 18.04 (Bionic) as it requires libcurl3 which cannot coexist with libcurl4 on this OS.
* macOS: open file [Makefile.am](https://github.com/s0uthwest/tsschecker/blob/master/tsschecker/Makefile.am) and update line with LDADD: `tsschecker_LDADD = $(AM_LDFLAGS) libjssy.a /usr/lib/libcurl.4.dylib`
   It required for downloading JSON files from ipsw.me for now.

## Report an issue
You can do it [here](https://github.com/s0uthwest/tsschecker/issues).

## Credits
Creator of [original project](https://github.com/tihmstar/tsschecker) - [tihmstar](https://github.com/tihmstar).


ReadMe updated on:
     2019-06-19

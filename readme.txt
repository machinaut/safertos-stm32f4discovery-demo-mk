Makefiles for building SafeRTOS's STM32F4-discovery demo

tested with the latest linaro arm-none-eabi toolchain
(https://launchpad.net/gcc-arm-embedded) on my laptop.  Feel free to file issues
if it doesn't work for you, but I probably won't do a ton of work fixing them.

It's possible to clone this on top of your SafeRTOS demo source tree, but if you
have to ask for the commands to do that you probably shouldn't.
Instead just copy the makefiles over manually.  The directory structure matches
so 

There's a portconfig define issue thats trivial to hack around.  Not sure of a
better fix for the time being.

Right now you have to do the final link step manually.  The super-awesome linker
script in the demo code does most of the heavy lifting for you though.

Cheers
~Alex

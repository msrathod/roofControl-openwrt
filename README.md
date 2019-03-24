# roofControl-openwrt
OpenWRT packages for roofControl project

Build from source:

```bash
echo "src-git Lambda git://github.com/msrathod/roofControl-openwrt.git" >> ./feeds.conf
./scripts/feeds update -a
./scripts/feeds install -p Lambda -a
make menuconfig
```
### blynkClient

Select in menuconfig: ```Network -> Lambda -> blynkClient```

**C++** example:
```cpp
#include <BlynkApiLinux.h>
static BlynkTransportSocket blynkTransport;
BlynkSocket Blynk(blynkTransport);

const char* AUTH = "YourAuthToken";

BLYNK_WRITE(V1) {
    printf("Got a value: %s\n", param[0].asStr());
}

int main(int argc, char* argv[]) {
    Blynk.begin(AUTH);

    while (true) {
        Blynk.run();
    }

    return 0;
}
```
### roofManager

Select in menuconfig: ```Network -> Lambda -> roofManager```

## Build OpenWRT image:
```bash
make -j 8
```

## Build just blynkClient package:
```
make package/blynkClient/compile V=s
```

For a rebuild:
```
make package/blynkClient/{clean,compile,install} V=s
```
## Build just the roofManager package:
```
make package/roofManager/compile V=s
```

For a rebuild:
```
make package/roofManager/{clean,compile,install} V=s
```

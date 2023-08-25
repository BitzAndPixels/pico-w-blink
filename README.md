# pico-w-blink

Pre-requisites:
1. Install minicom:
```
brew install minicom
```
2. Verify that your `$PICO_SDK_PATH` and `$PICO_BOARD` env variables are set correctly
```sh
echo $PICO_SDK_PATH
# You should see the path for PICO SDK

echo $PICO_BOARD
# You should see either pico or pico_w
```

To run:
1. **If have pico (not pico w), make sure to comment out the folllowing line in CMakeLists.txt file**:
```
pico_cyw43_arch_none
```
2. Create build directory: 
```
mkdir build
```
3. Cd to build directory: 
```sh
cd build
```
4. Run cmake: 
```sh
cmake ..
```
5. Run make: 
```sh
make
```
6. Copy `blink.uf2` file to pico/pico w while it is BOOTSEL mode
7. Find the pico usb device
```sh
ls -la /dev | grep -i tty.usb
# You should see something like tty.usbmodem143201
```
8. Connect to your pico usb device
```sh
minicom -b 115200 -o -D  /dev/tty.usbmodem143201
```
9. You should see `Hello world!` message
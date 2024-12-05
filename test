#include "SPI.h"
#include "Cube.h"

#define RGB(red, green, blue) (rgb_t) { red, green, blue }
#define BLACK  RGB(0x00, 0x00, 0x00)
#define BLUE   RGB(0x00, 0x00, 0xff)
#define GREEN  RGB(0x00, 0xff, 0x00)
#define ORANGE RGB(0xff, 0x45, 0x00)
#define PINK   RGB(0xff, 0x14, 0x44)
#define PURPLE RGB(0xff, 0x00, 0xff)
#define RED    RGB(0xff, 0x00, 0x00)
#define WHITE  RGB(0xff, 0xff, 0xff)
#define YELLOW RGB(0xff, 0xff, 0x00)

Cube cube;

void setup(void) {
  // Serial port options for control of the Cube using serial commands are:
  // 0: Control via the USB connector (most common).
  // 1: Control via the RXD and TXD pins on the main board.
  // -1: Don't attach any serial port to interact with the Cube.
  cube.begin(0, 115200); // Start on serial port 0 (USB) at 115200 baud
}

void loop(void) {
  int index = 3;
//   cube.all(RGB(0xff, 0xf0, 0x0f)); Alle RGB beleuchten
  for(int x = 0; x <= 3; x++){
    cube.set(x, x, x, BLUE);
    cube.set(x, index, x, PURPLE);
    cube.set(index, x , x, RED);
    cube.set(x, x, index, GREEN);
    index--;
    delay(500);
    //Turn off all RGB LED, NOTE: When lights out, it only can turn off all RGB LED rather than only one of them.
    cube.all(BLACK);
    delay(500);
  }
}

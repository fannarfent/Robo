
# verk 4
[Video fyrir verk4](https://youtube.com/shorts/8abRGgqXrhs?feature=share)
```
#include "vex.h"

using namespace vex;

float threshold;

int main() {
  // Initializing Robot Configuration. DO NOT REMOVE!
  vexcodeInit();

  threshold = 30;
  while (true) {
    // If the reflectivity is greater than the threshold it will move the LeftMotor forward
    if (LineTrackerA.reflectivity() < threshold) {
      LeftMotor.spin(forward);
      RightMotor.stop();
    } else {
      // If the reflectivity is less than the threshold it will move the RightMotor forward
      LeftMotor.stop();
      RightMotor.spin(forward);
    }
    wait(5, msec);
    if (BumperH.pressing()){ break; }
  }
  }
  ```

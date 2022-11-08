# verk 3_A
[video A hluti](https://youtube.com/shorts/opc_RMykJVc?feature=share)
#include "vex.h"



using namespace vex;

## int main() {
  // Initializing Robot Configuration. DO NOT REMOVE!
  vexcodeInit();

  while (true) {
    if (LightD.brightness() > 0 && LightD.brightness() < 70) {
      Brain.Screen.clearScreen();
      Brain.Screen.setCursor(1, 1);
      Brain.Screen.print("Dark Area");
      Drivetrain.setStopping(brake);
    } 
    else if (LightD.brightness() >= 70) {
      Brain.Screen.clearScreen();
      Brain.Screen.setCursor(1, 1);
      Brain.Screen.print("Light Area");
      Brain.Screen.setCursor(2, 1);
      Brain.Screen.print(LightD.brightness());

        if (RangeFinderE.distance(mm) < 100) {
        Drivetrain.turnFor(-90, degrees);
        }   else {
        Drivetrain.driveFor(2, inches);
        }
        wait(5, msec);
    if (BumperH.pressing()){ break; }
  }

    }

    wait(5, msec);

      }

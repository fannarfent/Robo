# verk 3_A
[video A hluti](https://youtube.com/shorts/opc_RMykJVc?feature=share)

```
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
```
# verk3_B hluti
[video B hluti](https://youtube.com/shorts/yze2KHnd2Ek?feature=share)
```
# kóði 
#include "vex.h"

using namespace vex;

event checkRed = event();
event checkBlue = event();
event checkGreen = event();

void hasBlueCallback() {
  Brain.Screen.setFont(mono40);
  Brain.Screen.clearLine(1, black);
  Brain.Screen.setCursor(Brain.Screen.row(), 1);
  Brain.Screen.setCursor(1, 1);
  Vision19.takeSnapshot(Vision19__BLUEBOX);
  if (Vision19.objectCount > 0) {
    Brain.Screen.print("Blue Object Found");
  } else {
    Brain.Screen.print("No Blue Object");
  }
}

void hasRedCallback() {
  Brain.Screen.setFont(mono40);
  Brain.Screen.clearLine(3, black);
  Brain.Screen.setCursor(Brain.Screen.row(), 1);
  Brain.Screen.setCursor(3, 1);
  Vision19.takeSnapshot(Vision19__REDBOX);
  if (Vision19.objectCount > 0) {
    Brain.Screen.print("Red Object Found");
  } else {
    Brain.Screen.print("No Red Object");
  }
}

void hasGreenCallback() {
  Brain.Screen.setFont(mono40);
  Brain.Screen.clearLine(5, black);
  Brain.Screen.setCursor(Brain.Screen.row(), 1);
  Brain.Screen.setCursor(5, 1);
  Vision19.takeSnapshot(Vision19__GREENBOX);
  if (Vision19.objectCount > 0) {
    Brain.Screen.print("Green Object Found");
  } else {
    Brain.Screen.print("No Green Object");
  }
}

int main() {
  // Initializing Robot Configuration. DO NOT REMOVE!
  vexcodeInit();

  checkBlue(hasBlueCallback);
  checkRed(hasRedCallback);
  checkGreen(hasGreenCallback);
  
  while (true) {
    checkBlue.broadcastAndWait();
    checkRed.broadcastAndWait();
    checkGreen.broadcastAndWait();
    wait(1, seconds);
  }
}
```
# verk3_C
[video B hluti](https://youtube.com/shorts/lJ0PYOnbic4?feature=share)
```
#include "vex.h"

using namespace vex;

event checkGreen = event();
const int CENTER_FOV =158;
const int OFFSET_X = 35;


void hasGreenCallback() {
  Brain.Screen.setFont(mono40);
  Brain.Screen.clearLine(5, black);
  Brain.Screen.setCursor(Brain.Screen.row(), 1);
  Brain.Screen.setCursor(5, 1);
  Vision19.takeSnapshot(Vision19__GREENBOX);
  if (Vision19.objectCount > 0) {
    
    Brain.Screen.print("Green Object Found");

    Brain.Screen.print(Vision19.largestObject.width);
      if(Vision19.largestObject.width > 80){
        Drivetrain.stop();
      }
       else if(Vision19.largestObject.centerX > CENTER_FOV + OFFSET_X){
        
        Drivetrain.turnFor(right,OFFSET_X,degrees);
      }
      else if (Vision19.largestObject.centerX < CENTER_FOV - OFFSET_X) {
        Drivetrain.turnFor(left,OFFSET_X,degrees);
      }
      else {
        Drivetrain.drive(forward);}
  } 
  else {
    Drivetrain.setStopping(brake);
    Brain.Screen.print("No Green Object");
  }
}

int main() {
  // Initializing Robot Configuration. DO NOT REMOVE!
  vexcodeInit();

  checkGreen(hasGreenCallback);
  
  while (true) {
    if (BumperH.pressing()){ break; }
    checkGreen.broadcastAndWait();
    wait(1, seconds);
  }
} 
```

#include "vex.h"

using namespace vex;

int main() {
  // Initializing Robot Configuration. DO NOT REMOVE!
  vexcodeInit();
  //for loop sem bætir við + 1 hvert skipti sem þetta runnar svo það endar kringum 2.5
  for(int i = 1; i <= 2.5;i++){
    //keyrir bílin áfram 0.5m og hvert skipti margfaldast með I sem breytist í hvert skipti
    Drivetrain.driveFor(forward, 500* i, mm);
    Drivetrain.driveFor(reverse, 500 * i, mm);
  }
}

[video 1](https://youtube.com/shorts/3679Zcdfc90?feature=share)
#include "vex.h"

using namespace vex;

int main() {
  // Initializing Robot Configuration. DO NOT REMOVE!
  vexcodeInit();

  Drivetrain.driveFor(reverse, 500, mm);
  
  Drivetrain.turnFor(90,degrees);
  Drivetrain.driveFor(reverse, 500, mm);
  Drivetrain.turnFor(-90,degrees);
  Drivetrain.driveFor(reverse, 500, mm);
  Drivetrain.turnFor(-90,degrees);
  Drivetrain.driveFor(reverse, 500, mm);
  Drivetrain.turnFor(90,degrees);
  Drivetrain.driveFor(reverse, 500, mm);
  Drivetrain.turnFor(90,degrees);
  Drivetrain.driveFor(reverse, 500, mm);
  Drivetrain.turnFor(-90,degrees);
  Drivetrain.driveFor(reverse, 500, mm);
  Drivetrain.turnFor(90,degrees);
  Drivetrain.driveFor(reverse, 500, mm);
  Drivetrain.turnFor(90,degrees);
  Drivetrain.driveFor(reverse, 500, mm);
  Drivetrain.turnFor(-90,degrees);
  Drivetrain.driveFor(reverse, 500, mm);
  Drivetrain.turnFor(90,degrees);
  Drivetrain.driveFor(reverse, 500, mm);
  Drivetrain.turnFor(90,degrees);
  Drivetrain.driveFor(reverse, 500, mm);
  Drivetrain.turnFor(-90,degrees);
  Drivetrain.driveFor(reverse, 500, mm);
  Drivetrain.turnFor(-90,degrees);
  Drivetrain.driveFor(reverse, 500, mm);
  Drivetrain.turnFor(90,degrees);
  Drivetrain.driveFor(reverse, 500, mm);
  

  
}
[video 2](https://youtube.com/shorts/DawVwXNhzrE?feature=share)

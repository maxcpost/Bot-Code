# Bot-Code

This is the Code running my VEX robot for the PLTW corse P.O.E. The robot has been named Rina.


## Built With

* [ROBOTC](http://www.robotc.net/download/vexrobotics/) - Compile and Deploy the Code
* [Atom](https://code.visualstudio.com) - Code the Robot (programmed in C)
* [VEX](https://www.vexrobotics.com/) - Hardware Used


## Contributors

**Maximillian Charles**, in charge of the [Mechanical](#Mech) and physical building of the robot as well as a few aspects of the code, including the [motion profiling](#motionpfile) aspect of Rina.

**Mark Kozlyuk**, responsible for almost all of the [Code](#Code) as well as the wiring aspects of the robot and the [Sensors](#Sensors) that dictate the robots motions.


## Mechanical <a id="Mech"></a>

## Sensors <a id="Sensors"></a>

## Code <a id="code"></a>

These are the different aspects found in the code that runs the robot.


### Motion Profiling-ish <a id="motionpfile"></a>

We attempted to create a rough version of Motion Profiling. We used a sonar [Sensor](#Sensors) in order to slow the motors based on there distance from the wall. This worked extremly well and achived our ability to move faster through the corse while not hitting the wall so hard that the button sensor does not pick up the needed data. The code is very simple and looks like this
```java
task main {
  untilSonarLessThan(30,dgtl3);
	startMotor(port2, 50);
	startMotor(port3, 50);
}
```

### Pivot turn

We first tried doing a point turn however after a few test runs we ran into some flaws in the predictability of where the robot would end up, because of this we decided to use Pivot Turn. This type of turn was more predictable and the code is simply
```java
task main {
  startMotor(port3, 55);
}
```


## Copyright and License

This project is 100% open-source.

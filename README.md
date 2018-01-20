# Bot-Code

This is the Code running my VEX robot for the PLTW corse P.O.E. The robot has been named Rina.
![picture](/img/Rina.png)

## Built With

* [ROBOTC](http://www.robotc.net/download/vexrobotics/) - Compile and Deploy the Code
* [Atom](https://atom.io/) - Code the Robot (programmed in C)
* [VEX](https://www.vexrobotics.com/) - Hardware Used


## Contributors

**Maximillian Charles**, in charge of the [Mechanical](#Mech) and physical building of the robot as well as a few aspects of the code, including the [motion profiling](#motionpfile) aspect of Rina.

**Mark Kozlyuk**, responsible for almost all of the [Code](#Code) as well as the wiring aspects of the robot and the [Sensors](#Sensors) that dictate the robots motions.


## Mechanical <a id="Mech"></a>

We decided to change a few of the mechanical aspecects from what the PLTW diagram described. Our changes where done in order to achive faster speeds.

### Gears

We increased the gear ratio tremendously in order to achive faster speeds. When tested against other robots both running their motors at 100, our robot traveled twice as fast. This is helpful in our quest for being the fastest however we ran into a few other problems that were solved with [motion profiling](#motionpfile).
![picture](/img/gears.png)

### Wheels

Our wheels are four inches in diameter which is much larger than what was suggested in the diagram, however, it is needed because of the larger gears.
![picture](/img/wheels.png)


## Sensors <a id="Sensors"></a>

We used three different sensors on the robot including [button](#button), [sonar](#sonar), and line fallower. Each time we wanted the robot to make a turn we used sonar to slow the robot down and then the when the robot hits the wall it will make the desired turn.

### button

The button is a digital sensor, this means that returns a value of 0 whenever it is not pressed and then when it is pressed it returns a value of 1. We used this type of sensor in order to detect when we have hit a wall. This is probablly our most esintial sensor.
![picture](/img/button.png)

### sonar

This type of sensor was vital to the succesful operation of the button this is because the buttons return value of 1 would not register if the robot hit the wall at full speed.
![picture](/img/sonar.png)


## Code <a id="code"></a>

These are the different aspects found in the code that runs the robot.

### Motion Profiling-ish <a id="motionpfile"></a>

We attempted to create a rough version of Motion Profiling. We used a sonar [Sensor](#Sensors) in order to slow the motors based on there distance from the wall. This worked extremly well and achived our ability to move faster through the corse while not hitting the wall so hard that the button sensor does not pick up the needed data. The code is very simple and looks like this
```c
task main {
  untilSonarLessThan(30,dgtl3);
	startMotor(port2, 50);
	startMotor(port3, 50);
}
```

### Pivot turn

We first tried doing a point turn however after a few test runs we ran into some flaws in the predictability of where the robot would end up, because of this we decided to use Pivot Turn. This type of turn was more predictable and the code is simply
```c
task main {
  startMotor(port3, 55);
}
```


## Copyright and License

This project is 100% open-source.

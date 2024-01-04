# F1Tenth_GapFollow
## Introduction

Gap following is a technique used in autonomous driving or robotics where a vehicle or robot navigates through an environment by identifying and following open spaces or "gaps" between obstacles.

The basic idea is to detect and pursue the widest available space or passage in the surroundings. This involves using sensors (like Lidar, cameras, or ultrasonic sensors) to perceive the environment and identify areas that are clear of obstacles. By following these open areas, the vehicle or robot can navigate safely and efficiently.

## The Algorithm

```mermaid

flowchart TD ;
A(Start) --> ldd[Establish a look ahead distance] ;
ldd --> loop{Loop Start} ;
loop --> filter[Filter Lidar sensor data] ;
filter --> gap[Identify widest gap] ;
gap --> diff["Identify 'disparity' in sensor
            data to mark 'edges' of objects"] ;
diff --> dilate[Dilate Lidar data on either side 
                of the disparity points by a
                certain threshold by marking
                it as 'Not Gap'] ;
dilate --> center['Find the centerpoint of the widest gap'] ;
center --> command["Steering angle points towards the centerpoint
                    Speed = Exponentian_decay(Steering Angle) "] ;
command --> loop ;

```

**Vanilla:**

![image](https://github.com/imalhotra15/F1Tenth_GapFollow/assets/118845522/c12e8c26-3905-4290-96a8-7947716638fc)

![image](https://github.com/imalhotra15/F1Tenth_GapFollow/assets/118845522/c6222b33-d4fd-4fdd-9913-4b7f13079c43)

![image](https://github.com/imalhotra15/F1Tenth_GapFollow/assets/118845522/14c07bb2-5c39-4744-bc9a-e8eb647154f7)



https://github.com/imalhotra15/F1Tenth_GapFollow/assets/118845522/1232b635-21b0-4983-8219-a848ee4bb377



**Dilating Edges:**

![image](https://github.com/imalhotra15/F1Tenth_GapFollow/assets/118845522/493a722e-8d16-4f3c-b302-3be753885a30)


https://github.com/imalhotra15/F1Tenth_GapFollow/assets/118845522/ed7b720f-686f-4091-9617-73664f413df0




## Notes

This was done as a part of the coursework of CSE 568 at the University at Buffalo. The source code is not available publicly to avoid academic integrity violations. Please feel free to contact the author if you wish access to the source code.

# SPRK
Stewart Platform Research Kit
The main aim of this project is to create a Stewart Platform which will simulate the breathing motion of a human body, to help better training of a da Vinci Robotic Surgical System.
This Stewart Platform is used to simulate body organ motion due to breathing, heart beats, or peristaltic movements, to translate and rotate phantom tissue. This platform is 20cm×20cm×10cm to fit in the workspace of a da Vinci Research Kit. The platform has a range of motion of ± 1.27 cm in translation along x, y, and z, and of ± 15◦ in roll, pitch, and yaw directions. 
The design of different parts of this Stewart Platform were made on SolidWorks, and then 3D printed at WPI Makerspace Ultimaker. The 3D components are listed below. 
1. Base Platform 
2. Mounting Platform 
3. Ball Joint Housing 
4. Ball Joint Rod 
5. Servo Horns 
The mounting platform consists of a hollow section in the center to accommodate a phantom tissue, on which the operation can be performed upon. The base platform is attached to the ground and the servo motors are placed upon it. The dimensions of the 3D printed material are taken such that the platform can be accommodated in the workspace of the dVRK. The ball joint housing houses the rivet and the ball joint rod, these together mimic a prismatic joint. The servo horn is attached to the servo motors, it helps in mimicking the breathing motion of a human.
# D.O.F Analysis
The Stewart Gough platform in general has 6-D.O,F. The configuration used for creating the SPRK uses ball and revolute joints instead of prismatic and universal joints. Our Stewart platform has 14 links: six legs, six servo horns, base, and top platform. The servo horns attached to the motors act as revolute joint, and the six legs have two ball joints each on either end.
![image](https://user-images.githubusercontent.com/64325043/228122471-a39001ab-7322-4fd1-8446-6371ea274303.png)
The degrees of freedom equation when calculated are 12 D.O.F.
DoF = 6(L-1) – 3S – 5R
Where,
L = no. of links
S = no. of spherical joints
R = no. of revolute joints
DoF = 6(14-1) – 3(12) – 5(6) = 12;
To calculate the DoF, the Grubler’s criterion is used where we consider the number of passive joints in the mechanism.
Though the mechanism has 12 degrees of freedom, six of them are redundant. The equation used for calculating the DoF is:

![image](https://user-images.githubusercontent.com/64325043/228122689-c1150b28-f33b-46aa-9c3b-525eac845377.png)

λ= 6 for the spatial case.
n= number of fixed links
j= number of joints in the mechanism.
fi= relative degrees of movement per board.
If= number of passive degrees of freedom of the mechanism.

![image](https://user-images.githubusercontent.com/64325043/228122757-ae9f7210-a066-48a6-962d-06cafe86faf9.png)

The designed Stewart platform can be said to have 6-D.O.F

# Resulting Motion

A. Home Configuartion

This mode brought all the servomotors back to their home configuration, which is perpendicular to the line of axis.

B. SinWave

This motion led each servomotor to follow a sine wave pattern and was found to be the most common equation to simulate breathing motion pattern.
𝒚(𝒕) = 𝑨 𝒔𝒊𝒏(𝟐𝜫𝝎𝒕) 
A is amplitude and ω is frequency
In this mode, we can use different translation and rotational values of the platform to attain desired speed and motion. We can also configure the motors to simultaneously work at different time phases for the required motion.

C. BreathWave

We came across a blog [6], which described a better type of 
equation to simulate the motion that we required.
𝒚(𝒕) = (𝒆𝒙𝒑(𝒔𝒊𝒏(𝝎𝒕)) −𝟏𝒆)𝟐𝑨𝒆−𝟏𝒆
A is amplitude and ω is frequency
This resulted in a motion like sine wave, but it the troughs had a longer time duration than its crests. This resulted in a fast motion but hold of the pose for a longer period of time. This resulted in a more realistic motion.

D. MixWave

This mode alternated the sine wave and breathed wave

# Result: 

![image](https://user-images.githubusercontent.com/64325043/228123024-a62bc60d-f102-4641-a0df-7c6f2874bcf0.png)


# This project is inspired and referenced from : 
V. Patel, S. Krishnan, A. Goncalves and K. Goldberg, "SPRK: A low-cost stewart platform for motion study in surgical robotics," 2018 International Symposium on Medical Robotics (ISMR), Atlanta, GA, USA, 2018, pp. 1-6, doi: 10.1109/ISMR.2018.8333300.

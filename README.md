# DC-Position-Control-System

## Aim:

To control the position of motor having the following specifications using MATLAB.<br>
(J)     moment of inertia of the rotor =    3.2284E-6 kg.m^2<br>
(b)     motor viscous friction constant =    3.5077E-6 N.m.s<br>
(Ktf)    motor torque constant   =           0.0274 N.m/Amp<br>
(R)     electric resistance  =              4 Ohm<br>
(L)     electric inductance  =              2.75E-6H<br>

## Apparatus Required:

Computer with MATLAB software

## Theory: 

The speed of a DC motor is directly proportional to armature voltage and inversely proportional to flux. In field controlled DC motor the armature voltage is kept constant and the speed is varied by varying the flux of the machine. Since flux is directly proportional to field current, the flux is varied by varying field current. 

The speed control system is an electro-mechanical control system. The electrical system consists of armature and field circuit but for analysis purpose, only field circuit is considered because the armature is excited by a constant voltage. The mechanical system consists of the rotating part of the motor and the load connected to the shaft of the motor. The field controlled DC motor speed control system is shown in the below figure. For this field controlled DC motor we shall find transfer function.
       
<img width="722" height="237" alt="image" src="https://github.com/user-attachments/assets/a88f2539-99e6-4089-bd4b-5b372ec46162" /> <br>
Let              Rf = Field resistance <br>
                   Lf = Field inductance <br>
                   if = Field current <br>
                   Vf= Field voltage <br>
                   T = Torque developed by motor  <br>
                  Ktf = Torque constant <br>
                   J = Moment of inertia of rotor and load <br>
The equivalent circuit of field is shown in the below figure. <br>
                  <img width="322" height="303" alt="image" src="https://github.com/user-attachments/assets/b3ee1388-b59f-4161-ba73-161de8752ee5" /> <br>

By Kirchoff ‘s voltage law, we can write <br>
<img width="218" height="72" alt="image" src="https://github.com/user-attachments/assets/19ec25c9-2283-4331-9e6f-28b080b485f5" /> <br>
The torque of  DC motor is proportional to product of flux and armature current. Since armature current is constant in this system, the torque is proportional to flux alone, but flux is proportional to field current. <br>

                                                T ∝ if 

                                        Torque , T = Ktf if

The mechanical system of the motor is shown in the below figure. <br>
<img width="407" height="100" alt="image" src="https://github.com/user-attachments/assets/d9869ccd-dbcf-4259-a365-94842d5fe061" /> <br>

The differential equation governing the mechanical system of the motor is given by, <br>

<img width="263" height="92" alt="image" src="https://github.com/user-attachments/assets/32d5193e-7d09-4078-b6eb-8834fc47f34f" /> <br>

On taking Laplace transform of the above equations with zero initial condition we get, <br>
<img width="632" height="197" alt="image" src="https://github.com/user-attachments/assets/da012858-ee14-4f30-89bb-d23946fe9630" /> <br>
Equating equations (2) & (3) we get, <br>
<img width="917" height="182" alt="image" src="https://github.com/user-attachments/assets/134f55a4-92db-4c53-b339-ac28dc6be9e5" /> <br>
The equation (1) can be written as <br>
<img width="646" height="75" alt="image" src="https://github.com/user-attachments/assets/0e712326-1320-4138-b17c-9346319fc1c5" /> <br>
<img width="303" height="137" alt="image" src="https://github.com/user-attachments/assets/4cd5dc35-5ddd-4dc6-ae0d-9892c7b5bda2" /> <br>

## Procedure:
1.	Open MATLAB software
2.	Open a new script file.
3.	Type the program.
4.	Save and Execute the program.
5.	Analyse the output in open loop and closed loop.

## Program

```
Kt=0.024
J=3.2284e-6
B=3.5077e-6
Rf=4
Lf=2.75e-6
s=tf('s')
ol_sys=Kt/((J*s^2+B*s)*(Lf*s+Rf))
subplot(2,1,1)
step(ol_sys)
title('open loop response')
cl_sys=feedback(ol_sys,1)
subplot(2,1,2)
step(cl_sys)
title('closed loop response')
```

## Output

<img width="692" height="626" alt="image" src="https://github.com/user-attachments/assets/2cccd701-5444-455d-bc5b-6b5ae3149227" />

## Result

Thus, the position of dc motor is controlled using MATLAB. 

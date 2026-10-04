# Project Journal

## Project Information

**Project:** Vantis-X
**Team:** Jonathan Bercovici, shaurya ashu, William de Marchi
**Start Date:** 28/08/26

---

# Devlog

## First Bit 

**Author:** [Name]
**Date:** [DD/MM/YYYY]
**Time Spent:** [X hours]


---

## Devlog 1


**Author:** Jonathan
**Date:** 28/08/26
**Time Spent:** 4.89 Hours

I started doing a lot of research on the areodynamics of a flying wing and started creating a fully parametric wing with as many variables as possible so that when i use the neural network to optimise it will end up as efficent as possible

<img width="705" height="412" alt="Screenshot 2026-08-28 071347" src="https://github.com/user-attachments/assets/7a1aee39-9fe1-4f6a-86f5-920af20e9567" />


---

## Devlog 2

**Author:** Jonathan
**Date:** 29/08/26
**Time Spent:** 1 hour

just started doing some simulations on 3 airfoils the mh 60 mh 61 and the pw 51 i am maingin looking for aoifrl that have a coefficent of lift above 0.6 wih an angle of attakc as low as possible. I am testing all of the airfoils at reynodls numbers of 100k up to 500k with and aoa between -5 and + 15

<img width="272" height="440" alt="Screenshot 2026-08-29 112818" src="https://github.com/user-attachments/assets/cf724431-956d-4e2f-b308-a6b34f6ec908" />

<img width="1920" height="1200" alt="Screenshot 2026-08-29 112750" src="https://github.com/user-attachments/assets/04f4ffc1-b288-41d7-abd2-b1da2b55efbe" />

---

## Devlog 3

**Author:** Jonathan
**Date:** 30/08/26
**Time Spent:** 1.5 Hours

I finished making a hugely simplified model of the UAV with only 3 paramates
<img width="1317" height="848" alt="image" src="https://github.com/user-attachments/assets/137bc183-1d61-49de-800e-e08ecba26bdc" />

I also worked on trying to understand how open foam actually work so far i just got to simulating the desufalt airfoil. Its a lot harder than i thought

<img width="1897" height="1135" alt="image" src="https://github.com/user-attachments/assets/01650ab6-523c-42fd-aaa1-73b7774dc7ed" />


---

## Devlog 3

**Author:** Jonathan
**Date:** 1/09/26
**Time Spent:** 2.2


start learning how to wire a neural network currently i taught it to find out if a point is inside a circle this is my horrible code: 

import torch
import torch.nn as nn


torch.manual_seed(42)

x = torch.rand(1000, 2) * 2 - 1

distance = x[:, 0]**2 + x[:, 1]**2

y = (distance < 0.5).float().unsqueeze(1)

model = nn.Sequential(
    nn.Linear(2, 8),
    nn.Tanh(),
    nn.Linear(8, 8),
    nn.Tanh(),
    nn.Linear(8, 1)
)

loss_fn = nn.BCEWithLogitsLoss()

optimizer = torch.optim.Adam(
    model.parameters(),
    lr=0.01
)

for epoch in range(7000):

    prediction = model(x)

    loss = loss_fn(prediction, y)

    optimizer.zero_grad()

    loss.backward()

    optimizer.step()

    if epoch % 100 == 0:
        print("epoch:",
              epoch,
              "loss",
              loss.item()  
              )

test = torch.tensor([[ 1, 0.4]], dtype=torch.float32)

prediction = model(test)    
probability = torch.sigmoid(prediction)
print("probabulty:", probability.item())
print(prediction)
if probability > 0.5:
    print("in cicle")
else :
    print("not in curcle")



<img width="912" height="448" alt="image" src="https://github.com/user-attachments/assets/a8e50a6d-878b-4959-9034-b988d1ec6cfb" />


---
## Devlog 4

**Author:** Shaurya Ashu
**Date:** 08/09/26
**Time Spent:** 2.75 Hrs

I've started with brainstorming on some of the Key aspects of the projector with Jonathan and finalize the requirements of the project which you could find in  requirement.md . After this discussion, I started working on the gimbal for the
FPV camera and took some deign notes from the internet and then fined the gamble with two SG90S metal gear servo motors and a 19mm FPV camera holder . It has a rotation of 260 degrees and a tilt of 65-90 degrees .

<img width="1440" height="900" alt="Screenshot 2026-09-08 at 2 11 17 AM" src="https://github.com/user-attachments/assets/9a54a929-b29d-4b7c-8cbf-869d57942299" />


---

## Devlog 5

**Author:** Jonathan B
**Date:** 16/09/26
**Time Spent:** 6
<img width="649" height="360" alt="image" src="https://github.com/user-attachments/assets/cacb5321-e5a8-4773-a45c-8c33daab653e" />

i finally finishd the body now i can start working on the nerunel network for the wing



---
## Devlog 5
**Author:** Jonathan B
**Date:** 18/09/26
**Time Spent:** 2

I managed to sucesfully run my first cfd simulation and ther ersults are looking pretty prosmsing i also finished the first desing of the acutaly plane.
<img width="995" height="692" alt="image" src="https://github.com/user-attachments/assets/02231d83-833b-4489-b06a-e7eae3410999" />
<img width="3240" height="1624" alt="actual_tihng_v1_2026-Sep-18_04-33-55PM-000_CustomizedView23877549274" src="https://github.com/user-attachments/assets/9cc711c5-88ee-4f58-9302-01b2ab630b8c" />


---

## Devlog 7

**Author:** Jonathan B
**Date:** 20/09/26
**Time Spent:** 4

I  a bit more work refining the airfoil and made this really cool internal strucutre

<img width="1361" height="793" alt="image" src="https://github.com/user-attachments/assets/aecb4a17-cd2c-4c39-a27f-e5ec090cc8a6" />


---
## UAV Drone research

**Author:** William D
**Date:** 15/09/2026
**Time Spent:** 0.76 hours

Here I just simply did lots of drone research for the drone.

<img width="1895" height="972" alt="image" src="https://github.com/user-attachments/assets/c9ba5b11-e40c-42b7-8138-ec0c87997050" />


---

## Here I started research about the rockets and unity

**Author:** William D
**Date:** 16/09/2026
**Time Spent:** [3.01 hours]

I learnt how to start unity and I researched the missiles I'm going to make.

<img width="1917" height="986" alt="image" src="https://github.com/user-attachments/assets/946245a5-2eea-4c35-9f1b-4b621beaf7bd" />


---
## Designing the rocket P1

**Author:** William D
**Date:** 17/09/2026
**Time Spent:** [1.2 hours]

Here made a super thin rocket design that is pretty much just the size of the motor we are putting on the back.

<img width="1912" height="948" alt="image" src="https://github.com/user-attachments/assets/28d14c50-df99-4763-a940-50997f872b4e" />


---

## Starting my code in Wokwi

**Author:** William D
**Date:** [20/09/2026]
**Time Spent:** [0.56 hours]

I started my simulation and code in Wokwi

<img width="1908" height="938" alt="image" src="https://github.com/user-attachments/assets/7b28800a-45cf-4931-bb0e-48380b0b18ec" />



---
## Continuing coding

**Author:** William D
**Date:** [20/09/2026]
**Time Spent:** [1.9 hours]

Here I added another servo to the simulation to simulate the PWM signals for a drone motor and I added to the code and did most of it, now I have to make it work.

<img width="1917" height="852" alt="image" src="https://github.com/user-attachments/assets/f346e76a-16f6-476b-bd3f-35819a37b54b" />


---

## More research and setting up a CFD

**Author:** William D
**Date:** [20/09/2026]
**Time Spent:** [2.1 hours]

Here I did a bunch of research for guiding rockets and stabalising them, then I decided to start the CFD.

<img width="1917" height="985" alt="image" src="https://github.com/user-attachments/assets/7db9b82d-770f-4928-80cd-333958c183e6" />


---
## Troubleshooting CFD with claude

**Author:** William D
**Date:** [20/09/2026]
**Time Spent:** [1.35 hours]

Here I used claude to help me troubleshoot the CFD I was using because it wasnt working, little sucess.

<img width="1917" height="955" alt="image" src="https://github.com/user-attachments/assets/2828bc07-06de-4830-8106-7d630121cd30" />


---

## Worked on the gyroscope

**Author:** Jonathan
**Date:** 24/09/26

here you can see i made the circuit for the imu for the fc. I picked the bmi 270 becusae it is really efficent has a bunch of documetation and can be run at insane speeds
<img width="833" height="617" alt="image" src="https://github.com/user-attachments/assets/a173b7ab-ab9e-489e-89f9-703a5de93a0c" />





---
## Worked on the power for the board

**Author:** Jonathan
**Date:** 25/09/26



today i made the the usbc intefrace adn the volatge regulator. I originaly wanted to use the ams 1117 voltage reg but then i realsied that it is only a liniar volatage reg so that it is not that effiect also it means i loose quite a bit of battery voltage becuase it cant go below 3.3 volts. so in the end i went with the tps 63001drcr becusae it was perefectly for what i needed. Since it is a buck boost converter it allows there to be a 3v3 steady 3v3 even when the battery is less that 3.3 volts. This will be really usefull if i want to use a lithium ion battery so that i could get the full range of chage.
<img width="755" height="297" alt="image" src="https://github.com/user-attachments/assets/502252d3-eb56-4683-bd54-87f7eb8f9b6f" />


---

## Desinged the charger

**Author:** Jonathan
**Date:** 26/07/26

This is the circuit for the charger for the baord. It is really cool because it has a integrated power path which means that it is able to power the system while chargrin it also menas that the charger is fully disconnected fomr the main systems which means if something happens we dont have to replace the whole system.
[<img width="841" height="542" alt="image" src="https://github.com/user-attachments/assets/b1d26ecd-b832-4063-93a8-d8c0da475a77" />


---
## Added a bunch more

**Author:** Jonathan
**Date:** 27/09/26


<img width="1229" height="853" alt="image" src="https://github.com/user-attachments/assets/27a248e2-2876-4aca-815c-f13c21272e5f" />


---

## Researching more with videos

**Author:** William
**Date:** 25/09/2026
**Time Spent:** 2.5 hours

Here I looked at a bunch of rocketry videos where I learnt how to use a cfd, rocket guidance and waypoints among other things.


<img width="1170" height="962" alt="image" src="https://github.com/user-attachments/assets/527256a8-5823-4e3b-be1f-6442df565bbf" />

---
## Making my stl into ASCII

**Author:** William
**Date:** 27/09/2026
**Time Spent:** 0.8 hours

Here I converted a test stl into ASCII format for a cfd I was atempting to use.


<img width="1917" height="1078" alt="image" src="https://github.com/user-attachments/assets/67bd611e-de00-4ee8-b2fd-371bd2d79efc" />


---

## Troubleshooting and designing fins

**Author:** William
**Date:** 27/09/2026 
**Time Spent:** 1.2 hours

Here I troublehshooted why openfoam wasnt working then I started designing some fins for the rocket.

<img width="1717" height="726" alt="image" src="https://github.com/user-attachments/assets/7e706d81-df17-4628-8f00-f418fe2cd91b" />


---

## Camera and stabilising

**Author:** William
**Date:** 27/09/2026
**Time Spent:** 0.7

Here I researched cameras and stabilisation for video by watching a video


<img width="1243" height="778" alt="image" src="https://github.com/user-attachments/assets/0829f7ab-271e-427c-9f9f-5dd6b000f9ab" />

---

## Running simflow

**Author:** William
**Date:** 27/09/2026
**Time Spent:** 1.8

Here I decided to stop trying openFoam and run simflow instead.

<img width="1622" height="950" alt="image" src="https://github.com/user-attachments/assets/ac25b34c-c5b5-4452-9e17-bb32216e2e82" />


---

## Testing my rocket stl with simflow

**Author:** William
**Date:** 27/09/2026
**Time Spent:** 2.3

Here I decided to test my missile with simflow but the missile fins had different sharpnesses so that I could compare them and see which one was the best

<img width="1917" height="973" alt="image" src="https://github.com/user-attachments/assets/8401ab90-0fc3-4641-92d1-76f75629d13f" />


---

## Looking at my simflow results

**Author:** William
**Date:** 27/09/2026
**Time Spent:** 0.3

Here I just looked at the test results but they were very abnormal so I might need to retest

<img width="1917" height="953" alt="image" src="https://github.com/user-attachments/assets/06c16000-068d-48b3-9007-8327c0dc71fb" />


---

Finished Schemtic



<img width="1091" height="722" alt="image" src="https://github.com/user-attachments/assets/3f2518ad-669e-47e2-aef8-caa3c37f2a35" />
After working for what felt like ages i though i finally finished with the schematic. Then i looked at it. It did not look good. I realised there were so many problems i spent like 4 hours reading data sheets and finsing so many problems. THen i decided that there was not one single 21 pin conncotr. I looked everywher 


---

## Trying CFD again

**Author:** William D
**Date:** [03/10/2026]
**Time Spent:** 0.2hrs

Here I tried and failed at doing another cfd.

<img width="1917" height="1078" alt="image" src="https://github.com/user-attachments/assets/49428aaa-db1b-4804-a5f7-c4b3822f9367" />


---

## Making edits to the UAV

**Author:** William D
**Date:** [03/10/2026]
**Time Spent:** 2.4hrs

Here I made edits to the UAV like starting to make flaps.

<img width="1917" height="1078" alt="image" src="https://github.com/user-attachments/assets/97d418e3-02d0-40c0-a5de-20da3613dbf7" />


---

## Researching flaps and wingletes

**Author:** William D
**Date:** [03/10/2026]
**Time Spent:** 1.3hrs

Here I researched and began making more things such as wingletes, flaps and a servo model. 

<img width="1917" height="1078" alt="image" src="https://github.com/user-attachments/assets/1853adcf-2436-4420-8912-2344e6892369" />


---

## Adding to my design and running my cfd

**Author:** William D
**Date:** [03/10/2026]
**Time Spent:** 0.8hrs

Here I added to my final design test and put it into a cfd to finally find the aerodynamics of different angles for my rocket fins.

<img width="1917" height="1078" alt="image" src="https://github.com/user-attachments/assets/0632b5ed-af99-4bf7-9211-541f9f97d884" />


---

## Restarting my rocket stl then making most of my flaps

**Author:** William D
**Date:** [04/10/2026]
**Time Spent:** 2.3hrs

This time I restarted my rocket stl fins then made the majority of my flap components.

<img width="1917" height="1078" alt="image" src="https://github.com/user-attachments/assets/685b2c1d-1157-4f5a-9384-1a438f16828e" />


---

## Learning about forms Finishing flaps and most of stl then running cfd

**Author:** William D
**Date:** [04/10/2026]
**Time Spent:** 3.6hrs

Here I made my flaps aerodynamic with some things I learnt about forms and sweeps then I started to run my cfd to see if the flaps actually made the body good.

---
# Milestones

## [Milestone Name]

**Date:** [DD/MM/YYYY]

[Briefly describe what was achieved.]

---

## [Milestone Name]

**Date:** [DD/MM/YYYY]

[Briefly describe what was achieved.]

---
## [Devlog Title]

**Author:** [Name]
**Date:** [DD/MM/YYYY]
**Time Spent:** [X hours]

[Write your development log here.]

---

# Milestones

## [Milestone Name]

**Date:** [DD/MM/YYYY]

[Briefly describe what was achieved.]

---

## [Milestone Name]

**Date:** [DD/MM/YYYY]

[Briefly describe what was achieved.]
## [Devlog Title]

**Author:** [Name]
**Date:** [DD/MM/YYYY]
**Time Spent:** [X hours]

[Write your development log here.]

---

# Milestones

## [Milestone Name]

**Date:** [DD/MM/YYYY]

[Briefly describe what was achieved.]

---

## [Milestone Name]

**Date:** [DD/MM/YYYY]

[Briefly describe what was achieved.]
## [Devlog Title]

**Author:** [Name]
**Date:** [DD/MM/YYYY]
**Time Spent:** [X hours]

[Write your development log here.]

---

# Milestones

## [Milestone Name]

**Date:** [DD/MM/YYYY]

[Briefly describe what was achieved.]

---

## [Milestone Name]

**Date:** [DD/MM/YYYY]

[Briefly describe what was achieved.]
## [Devlog Title]

**Author:** [Name]
**Date:** [DD/MM/YYYY]
**Time Spent:** [X hours]

[Write your development log here.]

---

# Milestones

## [Milestone Name]

**Date:** [DD/MM/YYYY]

[Briefly describe what was achieved.]

---

## [Milestone Name]

**Date:** [DD/MM/YYYY]

[Briefly describe what was achieved.]
## [Devlog Title]

**Author:** [Name]
**Date:** [DD/MM/YYYY]
**Time Spent:** [X hours]

[Write your development log here.]

---

# Milestones

## [Milestone Name]

**Date:** [DD/MM/YYYY]

[Briefly describe what was achieved.]

---

## [Milestone Name]

**Date:** [DD/MM/YYYY]

[Briefly describe what was achieved.]
## [Devlog Title]

**Author:** [Name]
**Date:** [DD/MM/YYYY]
**Time Spent:** [X hours]

[Write your development log here.]

---

# Milestones

## [Milestone Name]

**Date:** [DD/MM/YYYY]

[Briefly describe what was achieved.]

---

## [Milestone Name]

**Date:** [DD/MM/YYYY]

[Briefly describe what was achieved.]
## [Devlog Title]

**Author:** [Name]
**Date:** [DD/MM/YYYY]
**Time Spent:** [X hours]

[Write your development log here.]

---

# Milestones

## [Milestone Name]

**Date:** [DD/MM/YYYY]

[Briefly describe what was achieved.]

---

## [Milestone Name]

**Date:** [DD/MM/YYYY]

[Briefly describe what was achieved.]
## [Devlog Title]

**Author:** [Name]
**Date:** [DD/MM/YYYY]
**Time Spent:** [X hours]

[Write your development log here.]

---

# Milestones

## [Milestone Name]

**Date:** [DD/MM/YYYY]

[Briefly describe what was achieved.]

---

## [Milestone Name]

**Date:** [DD/MM/YYYY]

[Briefly describe what was achieved.]
## [Devlog Title]

**Author:** [Name]
**Date:** [DD/MM/YYYY]
**Time Spent:** [X hours]

[Write your development log here.]

---

# Milestones

## [Milestone Name]

**Date:** [DD/MM/YYYY]

[Briefly describe what was achieved.]

---

## [Milestone Name]

**Date:** [DD/MM/YYYY]

[Briefly describe what was achieved.]
## [Devlog Title]

**Author:** [Name]
**Date:** [DD/MM/YYYY]
**Time Spent:** [X hours]

[Write your development log here.]

---

# Milestones

## [Milestone Name]

**Date:** [DD/MM/YYYY]

[Briefly describe what was achieved.]

---

## [Milestone Name]

**Date:** [DD/MM/YYYY]

[Briefly describe what was achieved.]
## [Devlog Title]

**Author:** [Name]
**Date:** [DD/MM/YYYY]
**Time Spent:** [X hours]

[Write your development log here.]

---

# Milestones

## [Milestone Name]

**Date:** [DD/MM/YYYY]

[Briefly describe what was achieved.]

---

## [Milestone Name]

**Date:** [DD/MM/YYYY]

[Briefly describe what was achieved.]
## [Devlog Title]

**Author:** [Name]
**Date:** [DD/MM/YYYY]
**Time Spent:** [X hours]

[Write your development log here.]

---

# Milestones

## [Milestone Name]

**Date:** [DD/MM/YYYY]

[Briefly describe what was achieved.]

---

## [Milestone Name]

**Date:** [DD/MM/YYYY]

[Briefly describe what was achieved.]

# Final Devlog

**Author:** [Name]
**Date:** [DD/MM/YYYY]
**Time Spent:** [X hours]

[Describe the final result, what the team accomplished, what worked, what didn't, and what you learned from the project.]

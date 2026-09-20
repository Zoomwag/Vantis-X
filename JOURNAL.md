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

## [Devlog Title]

**Author:** [Name]
**Date:** [DD/MM/YYYY]
**Time Spent:** [X hours]

[Write your development log here.]

---
## [Devlog Title]

**Author:** [Name]
**Date:** [DD/MM/YYYY]
**Time Spent:** [X hours]

[Write your development log here.]

---

## [Devlog Title]

**Author:** [Name]
**Date:** [DD/MM/YYYY]
**Time Spent:** [X hours]

[Write your development log here.]

---
## [Devlog Title]

**Author:** [Name]
**Date:** [DD/MM/YYYY]
**Time Spent:** [X hours]

[Write your development log here.]

---

## [Devlog Title]

**Author:** [Name]
**Date:** [DD/MM/YYYY]
**Time Spent:** [X hours]

[Write your development log here.]

---
## [Devlog Title]

**Author:** [Name]
**Date:** [DD/MM/YYYY]
**Time Spent:** [X hours]

[Write your development log here.]

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

---

# Final Devlog

**Author:** [Name]
**Date:** [DD/MM/YYYY]
**Time Spent:** [X hours]

[Describe the final result, what the team accomplished, what worked, what didn't, and what you learned from the project.]

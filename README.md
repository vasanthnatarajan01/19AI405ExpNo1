<h1>ExpNo 1 :Developing AI Agent with PEAS Description</h1>
<h3>Name: VASANTH N</h3>
<h3>Register Number: 212224110060</h3>


<h3>AIM:</h3>
<br>
<p>To find the PEAS description for the given AI problem and develop an AI agent.</p>
<br>
<h3>Theory</h3>
<h3>Medicine prescribing agent:</h3>
<p>Such this agent prescribes medicine for fever (greater than 98.5 degrees) which we consider here as unhealthy, by the user temperature input, and another environment is rooms in the hospital (two rooms). This agent has to consider two factors one is room location and an unhealthy patient in a random room, the agent has to move from one room to another to check and treat the unhealthy person. The performance of the agent is calculated by incrementing performance and each time after treating in one room again it has to check another room so that the movement causes the agent to reduce its performance. Hence, agents prescribe medicine to unhealthy.</p>
<hr>
<h3>PEAS DESCRIPTION:</h3>
<table>
  <tr>
    <td><strong>Agent Type</strong></td>
    <td><strong>Performance</strong></td>
     <td><strong>Environment</strong></td>
    <td><strong>Actuators</strong></td>
    <td><strong>Sensors</strong></td>
  </tr>
    <tr>
    <td><strong>Medicine prescribing agent</strong></td>
    <td><strong>Treating unhealthy, agent movement</strong></td>
     <td><strong>Rooms, Patient</strong></td>
    <td><strong>Medicine, Treatment</strong></td>
    <td><strong>Location, Temperature of patient</strong></td>
  </tr>
</table>
<hr>
<H3>DESIGN STEPS</H3>
<h3>STEP 1:Identifying the input:</h3>
<p>Temperature from patients, Location.</p>
<h3>STEP 2:Identifying the output:</h3>
<p>Prescribe medicine if the patient in a random has a fever.</p>
<h3>STEP 3:Developing the PEAS description:</h3>
<p>PEAS description is developed by the performance, environment, actuators, and sensors in an agent.</p>
<h3>STEP 4:Implementing the AI agent:</h3>
<p>Treat unhealthy patients in each room. And check for the unhealthy patients in random room</p>
<h3>STEP 5:</h3>
<p>Measure the performance parameters: For each treatment performance incremented, for each movement performance decremented</p>

## PROGRAM:
```
import random

# Define rooms and randomly assign patient temperatures
rooms = {
    "Room A": random.uniform(97.0, 103.0),
    "Room B": random.uniform(97.0, 103.0)
}

# Agent initial state
current_room = "Room A"
performance = 0

# Function to check health and treat patient
def check_and_treat(room, temp):
    global performance
    print(f"\nAgent is in {room}")
    print(f"Patient temperature: {temp:.2f}°F")

    if temp > 98.5:
        print("Patient is UNHEALTHY → Prescribing Medicine")
        performance += 10
    else:
        print("Patient is HEALTHY → No treatment needed")

# Function to move agent
def move_agent(current):
    global performance
    performance -= 1
    if current == "Room A":
        return "Room B"
    else:
        return "Room A"

# Run agent for multiple cycles
for step in range(4):

    # Sense temperature
    temperature = rooms[current_room]

    # Take action
    check_and_treat(current_room, temperature)

    # Move to other room
    next_room = move_agent(current_room)
    print(f"Moving to {next_room}")
    print(f"Current Performance Score: {performance}")

    current_room = next_room

# Final result
print("\nFinal Performance Score:", performance)
```
## OUTPUT:
<img width="1484" height="1102" alt="image" src="https://github.com/user-attachments/assets/8e2ac351-1dfd-4155-abbd-5488ed371c22" />

## RESULT:
  The PEAS description for the problem and development an AI agent were completed successfully.

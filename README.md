# game-programming-exp-06
## AIM:
To create an AI character in Unreal Engine that roams randomly within a NavMesh area and chases
the player when they come within a certain range, using Behavior Trees, Blackboard, and AI
Perception.
## PROCEDURE:
1. Setup Navigation
Add a NavMeshBoundsVolume to your level and scale it to cover the roamable area.
Press P to confirm the green nav area is visible (indicating navigable space).
2. Create AI Character
Create a Blueprint character (e.g., BP_AIEnemy ) with a skeletal mesh and AIController class.
Create an AI Controller Blueprint (e.g., BP_AIController ) and assign it to the character.
3. Enable AI Perception
In BP_AIController , add an AIPerception component.
Configure a Sight sense (set detection range, lose sight range, peripheral vision angle).
Bind OnPerceptionUpdated to update a blackboard value
(e.g., CanSeePlayer and PlayerActor ).
4. Set Up Blackboard
Create a Blackboard with the following keys:
TargetLocation (Vector)
PlayerActor (Object)
CanSeePlayer (Bool)
5. Create Behavior Tree (BT_AI)
Structure it like this:
AI Random Roam with Chase - Unreal Engine 

6. Custom Task: Find Random Location
Create a new BTTask_BlueprintBase to get a random reachable point using:
Set the result to the TargetLocation blackboard key.
7. Test the AI
Add a player character to the level.
Place the AI enemy in the map and assign its controller and behavior tree.
Press Play: the AI should roam when the player is far and chase the player when within
sight.
UNavigationSystemV1::GetRandomReachablePointInRadius()
## Output:
![image](https://github.com/user-attachments/assets/64452218-9636-47a2-bf50-7e675cd7ab96)
![image](https://github.com/user-attachments/assets/5e9eb5e2-53ba-4e3c-bf2a-2f3e5f76bfd3)
**
![image](https://github.com/user-attachments/assets/b9d4eb44-2c37-44d6-82ad-13d4cc136b2c)
**
![image](https://github.com/user-attachments/assets/54aff871-6ebc-4c3f-a5fa-815cfb2265ac)



##  Result:
The AI character roams randomly within a defined area. When the player enters its sight range, the
AI stops roaming and begins to chase the player until the player is out of sight, after which it
resumes roaming.

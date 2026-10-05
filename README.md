# GAME_PROGRAM-EX--7
NAME: Dharshini

REG NO: 212225220024
## To create an AI character in Unreal Engine that roams randomly within a NavMesh area and chases
the player when they come within a certain range, using Behavior Trees, Blackboard, and AI Perception.

## STEPS
Setup Navigation Add a NavMeshBoundsVolume to your level and scale it to cover the roamable area. Press P to confirm the green nav area is visible (indicating navigable space).
Create AI Character Create a Blueprint character (e.g., BP_AIEnemy ) with a skeletal mesh and AIController class. Create an AI Controller Blueprint (e.g., BP_AIController ) and assign it to the character.
Enable AI Perception In BP_AIController , add an AIPerception component. Configure a Sight sense (set detection range, lose sight range, peripheral vision angle). Bind OnPerceptionUpdated to update a blackboard value (e.g., CanSeePlayer and PlayerActor ).
Set Up Blackboard Create a Blackboard with the following keys: TargetLocation (Vector) PlayerActor (Object) CanSeePlayer (Bool)
Create Behavior Tree (BT_AI) Structure it like this: AI Random Roam with Chase - Unreal Engine 🎯 Aim
Procedure
Root Selector

Sequence (Chase Player)

Blackboard Check: CanSeePlayer == truTask: Find Random Location → TargetLocation Move To: TargetLocation

Custom Task: Find Random Location Create a new BTTask_BlueprintBase to get a random reachable point using: Set the result to the TargetLocation blackboard key.

Test the AI Add a player character to the level. Place the AI enemy in the map and assign its controller and behavior tree. Press Play: the AI should roam when the player is far and chase the player when within sight. UNavigationSystemV1::GetRandomReachablePointInRadius()

## Output
<img width="880" height="449" alt="image" src="https://github.com/user-attachments/assets/308e1998-ed97-41ee-b844-13962eee0c54" />
<img width="876" height="748" alt="image" src="https://github.com/user-attachments/assets/b1b7c68b-8a1e-4d6e-8928-bba5779a07d4" />
<img width="876" height="748" alt="image" src="https://github.com/user-attachments/assets/99b9d523-562b-4637-8763-33f3cb1f4004" />

The AI character roams randomly within a defined area. When the player enters its sight range, the AI stops roaming and begins to chase the player until the player is out of sight, after which it resumes roaming.

## Result
The AI character roams randomly within a defined area. When the player enters its sight range, the AI stops roaming and begins to chase the player until the player is out of sight, after which it resumes roaming.

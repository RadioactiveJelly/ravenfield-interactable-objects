# ravenfield-interactable-objects
Scripts to help map makers create interactable objects that allow for multiple conditions and behaviours.

This package contains scripts and sample objects to create your own interactables.

### -----Interactables-----

Each interactable should have a data container that has the following:

- distance (float)
	- The distance before the player can interact with the object.
- interactKey (string)
	- The key for interacting with the object.
- stringSuffix (string)
	- This is the string that appears after the interact key.
	- The text displayed is formatted as: "Press <interactKey> <stringSuffix>" (i.e. "Press F to open door")

Interactable objects also must have these targets (bold items are required):
- **interactableCanvas (gameObject)**
	- This what shows when you're near the object. It'd normally be just a canvas with a text object.
- **dataContainer (DataContainer)**
- **canvasText (text)**
	- This is what is manipulated by interactKey and stringSuffix
- **interactableBehaviours (GameObject)**
	- An empty game object holding your Interactable Behaviours. See below for how this works.
- interactableConditions (GameObject)
	- An optional target that holds conditions for your interactable.

### -----Interactable Behaviours-----

Interactable behaviours are scripts you want to run when the player actually interacts with the object.
I've left a few sample scripts here to give you an idea of how they work.
EACH SCRIPT MUST HAVE THE Interact() FUNCTION! Follow the examples.

To set up you'll need to:
1. Create an empty object in your interactable object.
2. Create an scripted behaviour object and set the script to your desired behaviours.
3. If you want multiple behaviours, you can put multiple scripted behaviour objects.
4. NOTE: Execution order is from top to bottom, be mindful of this if you need things to run in a specific order.

### -----Interactable Conditions-----

Interactable Conditions are scripts which can prevent the interactable object from being interacted with, depending on what you want.
Same as above, I've left a sample script for this.
EACH SCRIPT MUST HAVE THE CanInteract() FUNCTION! This function must also return a boolean (true/false).

As noted above, this is optional. The scripts should run fine without any conditions set.
	
To set up you'll need to:
1. Create an empty object in your interactable object.
2. Create an scripted behaviour object and set the script to your desired conditions.
3. If you want multiple conditions, you can put multiple scripted behaviour objects.
4. NOTE: Execution order is from top to bottom, be mindful of this if you need things to run in a specific order.

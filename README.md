# Inventory-System-for-Unreal-Engine

This provides a re-usable inventory system in form of a Component that can be attached to actors like players or chests in the level.

The inventory uses a grid, like those found in the Resident Evil series, to store items. If there is not enough space to pick up an item,
it cannot be added to the inventory.

## How Importing the inventory System
  * Just drag the inventory zip from the releases part of the repo into your project
  * The demo is to show you how it would work in game build

## Setting up your inventory
1. You must set up your input action you want to pull up your inventory up then you set up your player and put the BP_InventoryComponent on the player

![image](https://github.com/user-attachments/assets/3f4e3c6b-478d-4ea3-9b1b-16e80e8b7940)

2. You must create a child blueprint of BP_items to create your own and you need to override Get Default Item Object Function and after you make a child you can duplicate the blueprint and just change the dimensions, the icons, and the item class of the item you just made

![364971283-df703c5e-bed9-4f37-a875-9a6a164c1745](https://github.com/user-attachments/assets/9ec1467a-eeca-42aa-95b7-77a1dcd6d170)

3. For the inventory grid size, it is on the player under BP_InventoryComponent

    <img width="352" alt="Grid set up" src="https://github.com/user-attachments/assets/3b640c65-4ee8-496d-8cd7-08bf16256bce">

4. Add/make your own icons you will need a normal and a rotated icon
5. You will need your own assets for the items you change on the child blueprints 
  
    <img width="308" alt="StaticMesh" src="https://github.com/user-attachments/assets/739c02fd-2291-48a8-927d-99846116789c">

6. If you are using your own character you need make SpawnItemFromDrop function

   ![image](https://github.com/user-attachments/assets/7f01cff9-a3ac-4b2b-a32c-6e0684a569b8)

7. change the casts are below if you are using your own character

   WBP_InvGrid
   ![image](https://github.com/user-attachments/assets/ccbdfb40-062f-4c46-9532-55c38f07a51a)
   
   WBP_Inventory
   ![image](https://github.com/user-attachments/assets/98645569-33bc-41f8-b5cc-1deade7fa266)
 
## How the inventory system works
1. the item class isn't the actor that is placed in the world the children the item class is what is placed in the world
    * The Item class holds all the code for the children
2. The BP_InventoryComponent has some of the code the item and Inventory
   * RoomAvailble function the way it works is it is looking for room that is available
   * TryAddItem function the that works is it uses the RoomAvailble function to see if there is room if the is room it uses the AddItem
   * AddItemfunction witch it adds the item to the top left of inventory and if there is no room to add it won’t add it inventory
3. WBP_InvGrid Has some code for Inventory
    * The Paint function paints all the lines and the icons and the colored backgrounds
    * OnDrop function when you drop the item from your Inventory the item should spawn on the floor
    * Create line function is the math for the lines of the Inventory grid
    * GetItem function get the items you picked up and put it in your Inventory
    * IsRoomForItem function checks if there is enough room for the item trying to go in your Inventory
    * OnDragOver function is when you drag the item over Inventory
    * MousePosInInv function it tracks your mouse in the Inventory
    * OnPreviewKeyDown function when you press the R button it rotates your item icons 90 degrees
4. ItemObject
   * GetDimensions function it gets Dimensions of the item
   * GetIcon function get the item icon
   * GetItem function it gets the item

 ## credits 
  Reids channel 
  https://youtu.be/4CjpBoKl6s8
  I used it as a base so the code is similar but from here on out i am going to update, change it and i have plans to add on to it  
 ## Future Plans
 1. work for multi-player compatibility
 2. work for ai

There will be more to add and if you have suggestions please email
Here is my email if you have questions or suggestions jaythegamera@gmail.com

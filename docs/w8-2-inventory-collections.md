<script>hljs.highlightAll();</script>

# Inventory and Collections

---



📦 **Unity packages from today's class:**
> 
> - Class Demo: [**Inventory System (Fixed and Dynamic) using Scriptable Objects, Lists, and/or Arrays**](https://drive.google.com/file/d/1aHxO1kaaCEIQI3RIN5HpIUQEYFpmUEQH/view?usp=sharing)

<br>

📚 **Other relevant resources to today's topic:**
>
> - More on narrative and mechanical possibilities of Inventory, Collections, and Save Systems, listed under the [Requirements section of Project 3 page](./project-3.md/#inventory-collections-save-system).
> - Recommended video tutorials:
>     - Scrollable UI Panels -- could be used for your long Inventory lists! [https://www.youtube.com/watch?v=XJdtxELpbh8](https://www.youtube.com/watch?v=XJdtxELpbh8)

<br>

**Recording 1: Lecture component**

<figure>
<iframe width="100%" height="500" src="https://www.youtube-nocookie.com/embed/YYIy4m6pxU0?si=-RF8uIbONa_A7DUi" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<figcaption>
</figcaption>
</figure>

<br>

**Recording 2: Tutorial Demo component**

<figure>
<iframe width="100%" height="500" src="https://www.youtube-nocookie.com/embed/3RWoBZAZ4Ho?si=xWujJM92cxWgbeDB" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<figcaption>
</figcaption>
</figure>

<br>

---


**Zines as archival technology; containers of information and ideology**

<figure>
<div class="div-container">
    <div style="width:47.5%">
    <img src="../img/bottlesofbygonedays0.jpg">
    </div>
    <div style="width:47.5%">
    <img src="../img/bottlesofbygonedays1.jpg">
    </div>
</div>
<figcaption>-- <a href="https://www.buckinghambooks.com/book/bottles-of-bygone-days-a-guide-book-of-modern-bottles-1850-to-date/">Bottles of Bygone Days: A Guide Book Of Modern Bottles, 1850 To Date</a>. Privately printed in 1965 by Donald E. Colcleaser.
</figcaption>
</figure>

<br>

**...that can both resist and reflect contemporary histories**

<figure>
<iframe width="100%" height="500" src="https://www.youtube-nocookie.com/embed/BqxLE0zh5Xo?si=69-sojgUrz0tQ5pA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<figcaption>-- "Contemporary Collecting: DIY Publishing", a webinar with Miarosa Ciallella and Jose Guerrero. Hosted by the Bibliographical Society of America (2020).
</figcaption>
</figure>

<br>

**Video game inventory catalogue as a narrative and mechanical device**

<figure>
<img src="../img/ffxvignis.png" width="100%">
<figcaption>-- FFXV Recipe Selection Menu, including information on availability (depending on ingredient stock), effects or stat boosts, and whether it's a party member's favourite dish.</figcaption>
</figure>
<figure>
<img src="../img/ffxvnoignis.jpg" width="100%">
<figcaption>-- FFXV Recipe Selection Menu, after Ignis became severely injured after battle.</figcaption>
</figure>

<br>

**Objects of Time**

- Items as historical artefacts.
- Collection, equipment, and consumption as player expression in the present game world.
- Inventory as a keyholder for future possibilities.

<figure>
<img src="../img/necktie-cropped.avif" width="100%">
<img src="../img/discotie.jpg" width="100%">
<figcaption>-- Disco Elysium. Horrific Tie... or "Chekov's Horrific Tie"?</figcaption>
</figure>

<br>

<figure>
<img src="../img/undertaletemcollege.png" width="100%">
<figcaption>-- Undertale. Tem Shop.</figcaption>
</figure>

<br>



## Making an Inventory System in Unity

> This demo uses techniques mentioned in this gamedevbeginner article "[How to Make an Inventory System in Unity](https://gamedevbeginner.com/how-to-make-an-inventory-system-in-unity/)" 

<br>

When making inventory systems, you're typically dealing with three different elements: 

1. **Item Data**: a definition of an item, such as name, sprite icon, description, uses/functions/effects, etc. 
2. **Item Instance**: an instance of an item data that exists in your game scene, which may have unique characteristics from other instances of the same item type. 
3. **Container**: a storage unit for containing a number of items, typically in a list or array.

<br>

The setup for your inventory system will look differently depending on how your project works and what it specifically needs. This example will use a cooking game example to demonstrate:

1. how to create and store a database of items inside our project folder using **scriptable objects**, **lists** and/or **arrays**;
2. how to display our item container (or player inventory) in the UI canvas; and
3. how to **add and remove items** from our inventory during runtime.

<br>

Let's start by making a scriptable object for our item data. 

### Item Data using Scriptable Objects

#### Why use scriptable objects?

Scriptable objects are script asset templates that allow you to create instances of a script inside your project, not your scene. **Think of them as prefab templates for making multiple scripts of the same type.** However, unlike prefabs themselves, you aren't storing an entire GameObject inside your folder -- you're only storing data. And because scriptable objects live inside your project, they are accessible throughout multiple scenes in your game.

In this example, we can use scriptable objects to make a template for storing item data, and then make multiple instances of this template for defining different types of items. 

<br>

#### How to create a scriptable object

1. **Create a C# script** called "ItemData", then open it.
2. Replace `MonoBehaviour` with `ScriptableObject`. Then add the `[CreateAssetMenu]` attribute above this line -- this lets you create an instance of this scriptable object by right-clicking in your assets folder > **Create** > **Item Data**.

```csharp
using UnityEngine;

[CreateAssetMenu]
public class ItemData : ScriptableObject
{
    public string itemName;
    public Sprite icon;

    [TextArea] public string description;
        //The "TextArea" attribute enables a height-flexible
        // and scrollable text input field inside our inspector.
}

//this example only uses a single type of item data.
//depending on your project needs,
//you may consider making multiple types of item data
//according to more specialised classes
//(e.g. equipable items, consumable items)
```

<br>

<ol start="3">
<li>Save the script above, and return to the Unity Editor. Right click in your assets folder, then go to <b>Create</b> > <b>Item Data</b>.<br><br><img src="../img/scriptableobj0.jpg"><br><br>
</li>
<li>In the inspector, you can fill in the details for an item in your game. You may create a new item data asset for every possible item in your game.<br><br><img src="../img/scriptableobj1.jpg"></li>
</ol>

<br>

Next, let's make a serializable class for our item instance. 

### Item Instance

Our ItemInstance class will create a constructor method that accepts an ItemData asset to generate default values for its variables. 

```csharp
using UnityEngine;

[System.Serializable]
public class ItemInstance
{
    public ItemData itemType;
    public Sprite sprite; //we can assign the ItemData defaults in our constructor method
    public string description; //we can assign the ItemData defaults in our constructor method
    public int qty; //this data is really only used for the Inventory Array example.

    //let's say you want to be able to update/edit
    //the item data for different instances of the same item

    //you can make a constructor method that
    //takes the ItemData as a default template,
    //but you can eventually pass different information
    //into this instance's variables later on.

    public ItemInstance(ItemData itemData)
    {
        itemType = itemData;
        sprite = itemData.icon;
        description = itemData.description;
        qty = 0;
    }

    //you might customise this constructor 
    //for generating different versions of this item 
    //(e.g. pickup items with different qtys)

    public ItemInstance(ItemData itemData, int itemQty)
    {
        itemType = itemData;
        sprite = itemData.icon;
        description = itemData.description;
        qty = itemQty;
    }
}
```

### Item Container, or Inventory Manager

In my example, I've made my inventory list managers scriptable objects so that they can persist across multiple scenes. If you only have one scene in your game, you could also set it as a Monobehaviour class instead. 

(*Note: Although it appears as if the scriptable object is saving data in your folder every time you play in the Unity Editor, this information will not be persistent once the Unity build application closes.*)

<br>

There are two methods for organising your inventory system: using **lists** or **arrays**. 

#### Using Lists for Inventory Systems

The benefit of lists is that their size can change dynamically throughout runtime. Note that though lists otherwise operate very similarly to arrays, they often use different syntax for their variables and method functions that otherwise essentially do the same thing. 

<br>

**To declare a List**

```csharp
List<VariableType> listName = new List<VariableType>();
//same as: 
//"List<VariableType> listName = new();"
```

<br>

**To get the total number of items in a list**

```csharp
//instead of length, we call this a count!
int listCount = listName.Count;
```

<br>

**To access an item in a list**

```csharp
//for example, 
//to get the first element in a string list,
string str = listName[0];

//this is also how you would access
//an element in an array. 
```

<br>

**To add or remove items from a list**

```csharp
listName.Add(someObject);

listName.Remove(list[0]); 
    //using a gameObject reference
listName.RemoveAt(0); 
    //using an integer index
    //removes the first item
    //watch out for out of range errors.
listName.RemoveRange(1,2);
    //removes 2 values starting at index 1
listName.RemoveAll(x => x.CompareTag("Pickup"));
    //removes all items in the list
    //that match the condition listed.
listName.Clear()
    //removes all items in your list.
```

<br>


In my example, I've used lists to store 1 item in each inventory slot. My inventory also has a maximum capacity, so it won't be able to add more items into the inventory beyond that limit. 

```csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

//because this is a scriptable object
//i also had to create a new InventoryListManager asset
//inside my project asset folder in order to
//use this system in my game.
[CreateAssetMenu]
public class InventoryListManager : ScriptableObject
{
    public List<ItemInstance> inventory = new(); 
        // contains item instances

    public int maxCapacity = 6; 
        // maximum inventory slots available

    public bool HasSpaceForNewItem(ItemInstance itemToAdd)
    {

        //do we have an empty slot in our list?
        for (int i = 0; i < inventory.Count; i++)
        {
            if (inventory[i] == null)
            {
                //if so, let's assign this slot to the new item!
                inventory[i] = itemToAdd;
                return true;
            }
        }

        //is the size of our inventory list less than max capacity?
        if (inventory.Count < maxCapacity)
        {
            //if so, let's make a new slot, and add our new item there!
            inventory.Add(itemToAdd);
            return true;
        }

        //otherwise, we don't have space for a new item!
        Debug.Log("No space in inventory.");
        return false;
    }
}
```

<br>

Here is how the demo looks like, with another script called "InventoryListDisplay" that uses the information in our manager for in-game functionality (e.g. updating UI graphics, button functions etc.)

This is an example of a **dynamic inventory system** that can hold a number of items but without specifiying ahead of time what those items may be. 

![](./img/inventorylistdemo.gif)

<br>


#### Using Arrays for Inventory Systems

There are instances when it *may* make more sense to use an array for your purposes.

In a different version of this example, I made an **fixed inventory system** using arrays. I didn't need the resizability of a **dynamic inventory system** like in my previous example, and therefore opted to use arrays for my inventory system instead. 

```csharp
[CreateAssetMenu]
public class InventoryArrayManager : ScriptableObject
{
    public ItemInstance[] inventory; 
        // contains item instances

    public ItemData[] allPossibleItems;
        // the player either has or doesn't have the item
        // so inventory size remains fixed

        // (but visibility of item UI graphics get toggled off
        // if item qty is 0 -- see: InventoryArrayDisplay.cs)

    //initialise array, if not yet already done so.
    public void ResetInventory()
    {
        inventory = new ItemInstance[allPossibleItems.Length];
        for (int i =0; i < inventory.Length; i++)
        {
            inventory[i] = new ItemInstance(allPossibleItems[i]);
        }
    }

    //checks if we are removing the last item
    //we will use this to determine whether UI graphics for that item
    //should be switched off.
    public bool IsRemovingLastItem(ItemInstance item)
    {
        item.qty--;

        if (item.qty == 0)
        {
            return true;
        } else
        {
            return false;
        }
    }
}
```

<br>

Here is how the demo looks like, with another script called "InventoryArrayDisplay" that uses the information in our manager for in-game functionality. 

Here, because the items that will enter our inventory are predictable, we can stack same items in the same inventory slot, and mark the quantity number next to their icon. 

![](./img/inventoryarraydemo.gif)

---

## Some course reminders

- To get credit for Homeplay 2 or Project 3 Sketch, email me your submission (this can be a short written response) by end of the day this Friday (Nov 22, 11:59P).
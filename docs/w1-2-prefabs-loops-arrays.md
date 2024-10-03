<script>hljs.highlightAll();</script>

# Prefabs, Loops, Arrays
<!--
---

📦 **Unity packages from today's class:**
> 
-->

---

Before we begin...

<br>

## Review from last class

- [Transform component](https://docs.unity3d.com/Manual/GameObjects.html) and its properties
- [Vectors](https://docs.unity3d.com/Manual/UsingComponents.html) and how to use them
    - Vector math operations and method functions
    - Using vectors for procedural animation


---

## Exercise from last class

**How do we make a solar system that dynamically generates at the start of the scene:**

1. **a random number of planets and moons;**
2. **a set distance interval between each consecutive sibling planet?**


<iframe width="100%" height="315" src="https://www.youtube-nocookie.com/embed/GFa_E9BCoUg?si=qQja99oKoHmzb9t-&amp;controls=0" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<iframe width="100%" height="315" src="https://www.youtube-nocookie.com/embed/2_GG6TGaoII?si=wz_ArkzXmQFZcVxl&amp;controls=0" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

---

## Prefabs

> Read about [Prefabs](https://docs.unity3d.com/Manual/Prefabs.html) in the Unity Manual.

Prefabs allow you to **store a GameObject and its information** (including its components, property values, child objects, etc.) into your Unity project folder **as a reusable Asset**. 

This Prefab Asset can be used as a base template from which you can create and modify new Prefab instances in the scene.

<br>

### How to create a Prefab from an existing GameObject in the scene

**Click and drag the GameObject from the Scene Hierarchy into your project folder panel.**

The GameObject should now be marked with a blue icon, and have an arrow button to the right of its name that leads you to the Prefab editor.

![How To Make A GameObject Prefab](./img/makeprefab.gif)

<br>

### How to Instantiate a GameObject

We use the [Instantiate()](https://docs.unity3d.com/ScriptReference/Object.Instantiate.html) method function to **spawn new instances of a GameObject** in our scene.

```csharp
Instantiate(someGameObject);
```

<br>

You could also **pass a GameObject instance into a GameObject variable**. This allows you to reference it later in your script. 

```csharp
GameObject obj = Instantiate(someGameObject);

//let's say we want to change the position of this instance
obj.transform.position = someVector;

//or set it to a new parent
obj.transform.parent = someParentObject;

```

<br>

The Instantiate() method can also be called in other ways that allow you to **pass multiple parameters at once**. 

The Unity Scripting API lists all the different ways you can declare the [Instantiate()](https://docs.unity3d.com/ScriptReference/Object.Instantiate.html) function.

For example:

```csharp
GameObject obj = Instantiate(
    spawnThisGameObject, //GameObject
    atSomePosition, //Vector3
    atSomeQuaternionRotation, //Quaternion
    underSomeParent); //Transform

```

---

## Loops

Loop functions allow you to repeat an action multiple times. 

Watch the Unity Tutorial below to learn about: 

- **While loops**
- **Do-while Loops**
- **For Loops**

<iframe width="100%" height="315" src="https://www.youtube.com/embed/Jefkb3Gm7vE?si=tyLETphQQTI-FwwH" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<br>

... and one more video about **Foreach Loops**.

<iframe width="100%" height="315" src="https://www.youtube-nocookie.com/embed/WhACXlObR8s?si=vHWChlqbapALZ_Of&amp;controls=0" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

---

## Arrays

> Read about [Arrays](https://docs.unity3d.com/2020.1/Documentation/ScriptReference/Array.html) in the Unity Manual.

Arrays allow you to **store multiple objects in a single variable**. 

Each object in an array is attached to **an index number, starting from 0**. This index number is used when calling this object from the array. 

```csharp
string[] fruits = {"apples", "pears", "oranges"};

// string[0] will return "apples"
// string[1] ... "pears"
// string[2] ... "oranges"
```

<br> 

Every array has a **Length** property, which gives you the number elements in the array.

```csharp
string[] fruits = {"apples", "pears", "oranges"};

Debug.Log("Length of fruits array: "+ fruits.Length); 
// console will print "Length of fruits array: 3".
```

<br>

**Arrays cannot be resized while the project is running.** If you need to resize a container of objects, either recreate the array to resize it, or use a [List](https://learn.unity.com/tutorial/lists-and-dictionaries#63561975edbc2a0cf1ad33b2) instead.

<br>

### How to declare an array

**Declare the type of variable** that is being stored in the array, followed by **square brackets** [] . 

```csharp
float[] someFloats; // a private float array
private Transform[] someTransforms; // a private Transform array
public Vector3[] someVectors; // a public Vector3 array
[SerializeField] GameObject[] someGameObjects; // a private GameObject array that is visible in the Inspector.
```

<br>

You can initialise the array by:

- **using an array constructor method in your scripts;** </br><pre><code class="language-csharp hljs">// Creates an array with 5 empty elements
int[] numbers = new int[5]; 
<br>
// Initialises array with elements
numbers = {1, 2, 3, 4, 5};
<br>
//OR declare and initialise at once
int[] numbers = new int[] {1,2,3,4,5};
</code></pre><br>
- **storing elements in the Inspector**, if your array is either public OR private with a [SerializeField] attribute;<br><br><figure><img src ="../img/Int-Array-with-5-elements.webp"><figcaption></figcaption></figure><br>
- **using a method that sets the contents of an array** </br><pre><code class="language-csharp hljs">//stores all GameObjects in the scene with tag "Respawn" into the array
GameObject[] respawns = GameObject.FindGameObjectsWithTag("Respawn");</code></pre>

---

## In-class exercise

**Write a script that instantiates multiple prefabs that are:**

1. **chosen at random from an array; AND**
2. **each set at a random position within a given scope.** (i.e. nothing should be "out of bounds", OR objects should only spawn at very specific positions.)

*(Hint: Try using:*

- *array.Length;* 
- *[Random.Range()](https://docs.unity3d.com/ScriptReference/Random.Range.html);*
- *[Vector3.Distance()](https://docs.unity3d.com/ScriptReference/Vector3.Distance.html); AND/OR*
- *empty GameObjects as positional references.)*

---

## Some course reminders

- [Homeplay 1](./readings-and-homeplays.md/#homeplay-1) and [Project 1 Sketch](./project-1.md/) are both due next class.
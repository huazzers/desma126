<script>hljs.highlightAll();</script>

# Randomness, Noise, Custom Classes for Storing Data

---

📦 **Unity packages from today's class:**
> 
> - [**Perlin Noise for Animation and Terrain Generation**](https://drive.google.com/file/d/1HC1tOnao0y_MKTLlgBbiiocQBjpJaId2/view?usp=sharing)
> - [**Using Scripts for Storing Data**](https://drive.google.com/file/d/1urb4VHbFvDKvS02d1IS7qVpusmFXUJlp/view?usp=drive_link)
>       - Spawning Objects at Random Positions without Repeats
>       - Colour Scheme Randomizer


---

Before we begin...

<br>

## Review from last class

- Prefabs and Instantiation
    - Creating a prefab
    - Instantiate() method
- Arrays
    - How to declare and initialise arrays
    - How to get an element from an array
- Random.Range()

<br>

---

## Randomness

Sometimes we want to randomize the behaviour of our game, for procedurally generating levels, for adding variation to the behavior of NPCs, and more.

<br>

### Random.Range

> Read about [Random.Range](https://docs.unity3d.com/ScriptReference/Random.Range.html) in the Unity Scripting API.

There are two versions of Random.Range: 

- one that returns **a random float** within a minimum *inclusive* float and maximum *inclusive* float; <br> <br> *Note: you can make any number a float by adding an 'f' at the end.*<pre><code class="language-csharp hljs">float randomFloat = Random.Range(0.5f, 2.5f);
// returns a random float between 0.5 and 2.5, including 0.5 and 2.5
</code></pre><pre><code class="language-csharp hljs">float randomFloat = Random.Range(2f, 4f);
// returns a random float between 2 and 4, including 2 and 4.
</code></pre><br>
- and one that returns **a random integer** within a minimum *inclusive* integer and maximum *exclusive* integer. <pre><code class="language-csharp hljs">int randomInteger = Random.Range(0, 3);
// returns a random integer between 0 and 3, including 0 but excluding 3,
// ie. possible outcomes are 0, 1, and 2.
</code></pre><br>

#### Using Random.Range with Conditional Statements

We can use **Random.Range** and **conditional statements** to determine what actions happen depending on the random output number, as well as the probability of each outcome. 

<br>

For example, a coin toss can be set up using **a random integer**...

```csharp
int coinToss = Random.Range(0,2);
// the only possible outcomes are 0 and 1.

if (coinToss == 0){
    Debug.Log("Heads");
} else { // if coinToss == 1
    Debug.Log("Tails");
}
```

<br>

... or **a random float**. Both are doing the exact same thing, because the probability of either outcome is exactly the same (50% chance).

```csharp
float coinToss = Random.Range(0f,1f);
// outcome can be any decimal number between 0 to 1, including 0 and 1.

if (coinToss > 0.5f){ // if coinToss is more than 0.5f
    Debug.Log("Heads");
} else { // if coinToss is less than or equal to 0.5f
    Debug.Log("Tails");
}
```

<br>

You can also set up your outcomes with **an uneven probability**.

```csharp
float badCoin = Random.Range(0f,1f);

if (badCoin > 0.7f){ // if coinToss is more than 0.7f
    Debug.Log("Heads"); // this has a 30% chance of happening
} else { // if coinToss is less than or equal to 0.7f
    Debug.Log("Tails"); // this has a 70% chance of happening 
}
```

<br>

The above examples use **if-else statements** to select which actions to run based on what the random number is. 

<br>

You can also use **switch statements**, which are helpful for working with **a longer list of possible outcomes**. This is because switch statements evaluate all possible outcomes and proceed immediately to the relevant "case" index, instead of evaluating the conditions one by one according to the order listed in an "if-else" chain.

Switch statements will look at one variable (placed inside the parentheses), and switch across different listed outcomes (each listed as a `case` index) until it finds one that matches the current value. Each case must end off with a `break;` statement to exit the loop.

```csharp
int diceRoll = Random.Range(1,7);
//possible outcomes are 1, 2, 3, 4, 5, and 6.

switch (diceRoll)
{
    case 1: // if diceRoll == 1
        Debug.Log("Rolled a 1.");
        break; // exit loop

    case 2: // if diceRoll == 2
        Debug.Log("Rolled a 2.");
        break; // exit loop

    //etc...

    case 6: // if diceRoll == 6
        Debug.Log("Rolled a 6.");
        break; // exit loop

    default: //acts like an "else" statement to catch all other outcomes not listed above.
        Debug.Error("Invalid roll number.");
        break; // exit loop
}
```

<br>

#### Using Random.Range with Arrays

You can use Random.Range (for random integers) to **pick elements out of an array at random** by using the length of the array as the second argument. 

```csharp
string[] names = new string[]{"alfred","bruno", "cynthia","dianne","esther"};
int pick = Random.Range(0, names.Length);
Debug.Log(names[pick]); //prints one of the names in the array at random.
```

<br>

---

## Noise

We will learn about two kinds of noise: **random noise** and **perlin noise**

<br> 

### Random Noise

In random noise, the values generated are **completely random** and have **no correlation to one another**. This creates a very grainy and chaotic texture.

<figure>
    <img src="../img/noise-random.png" alt="random noise">
    <figcaption>
        -- Noise made with random noise
    </figcaption>
</figure>

<br> 

And because the random values are independent of one another, if we were to transfer one area of random noise onto another (with all other parameters kept the same), it blends in seamlessly. 

<figure>
    <img src="../img/noise-random-move.gif" alt="moving random noise from one area to another">
    <figcaption>
        -- Random noise feels uninterrupted regardless of the transposition of values.
    </figcaption>
</figure>

<br> 

### Perlin Noise

> If you're curious about the mathematical logic behind perlin noise generation, I recommend watching this Youtube video, [Perlin Noise Explained](https://youtu.be/MJ3bvCkHJtE?feature=shared&t=405) (start from 06:45). 

Sometimes in computer graphics, we want to use seemingly random values that are smoothly interpolated across one another. In these situations, we could get "smooth" random values with **Perlin Noise**.

<figure>
    <img src="../img/noise-perlin.png" alt="perlin noise">
    <figcaption>
        -- Noise made with perlin noise
    </figcaption>
</figure>

<br>

In perlin noise, **neighbouring values are related to each other** through the smooth interpolation from one area to another. Therefore, if we were to move one area of perlin noise onto another, the smooth interpolation is disrupted, and we can clearly see where one area starts and ends. 

<figure>
    <img src="../img/noise-perlin-move.gif" alt="moving perlin noise from one area to another">
    <figcaption>
        -- Transposition of values becomes very clear in perlin noise.
    </figcaption>
</figure>

<br>

### Mathf.PerlinNoise

> Read about [Mathf.PerlinNoise](https://docs.unity3d.com/ScriptReference/Mathf.PerlinNoise.html) in the Unity Scripting API.

In Unity, we can use **Mathf.PerlinNoise** to generate Perlin noise across a 2D plane. 

To use this method, we pass **two sample points along the X and Y axes in floats** into the function, and it will return **a float value between approaximately 0 and 1** which corresponds to the colour of the noise in those exact coordinates (Black is 0; White is 1.)

*(Note: return value might be slightly below 0.0 or beyond 1.0.)*

<br>

#### Using Random Seeds in Perlin Noise

Because Perlin noise is **a pseudo-random pattern** of float values (i.e. it's not *truly* random), the same sample X and Y coordinates will return the same value. 

You can use Random.Range to randomize the X or Y coordinates to sample random parts of the Perlin noise image. 

```csharp
float randomSeed; 
// Note: 
// A (random) seed is like a starting sample coordinate
// that can be passed into a pseudorandom generator like perlin noise 
// to create a replicable outcome.

void Start()
{
    randomSeedY = Random.Range(0f, 100f);
}

void Update()
{
	float x = Time.time;
	float y = randomSeed;
	float someNoiseValue = Mathf.PerlinNoise(x,y);
}
```

<br>

#### Remapping Output Range in Perlin Noise

Because the range of values in Perlin noise is limited to 0:1, we typically need to **translate this value to a diferent range**. 

For example, you could use a little algebra to remap the noise value range from 0:1 to -1:1:

```csharp
float someNoiseValue = Mathf.PerlinNoise(x,y);
float remappedNoise = (someNoiseValue * 2) - 1;
```

<br>

You could also use [Mathf.Lerp](https://docs.unity3d.com/ScriptReference/Mathf.Lerp.html) to remap the noise value from 0:1 to a different range of values.

This example below remaps noise to -255:255.

```csharp
float noise = Mathf.PerlinNoise(x,y);
float remappedNoise = Mathf.Lerp(-255,255, noise);
```

<br>

#### Animating Perlin Noise using Time.time

We can pass [Time.time] into our x or y-coordinates to "march" across the perlin noise image over time. 

```csharp
float x, y, someNoiseValue;

void Start(){
    y = 0;
}

void Update(){
	x = Time.time; //Time.time is the amount of time that has passed since the start of the application
	someNoiseValue = Mathf.PerlinNoise(x,y);
}
```

<br>

This value could be passed into any property in your scene (such as y-position) for procedural animation. 

<figure>
<img src="../img/noise-perlin-animatedspheres.gif" alt="animating spheres y-position using perlin noise">
<figcaption>-- Perlin noise value is passed into the spheres' y-position; each sphere has their perlin noise sample coordinate offset by an increment of 0.2 in the x-direction.
</figcaption>
</figure>

<br>

#### Terrain Generation with Perlin Noise

We can pass Perlin noise values into x and y positions to procedurally generate a terrain.

<figure>
<img src="../img/noise-perlin-terrain.jpg" alt="generated terrain using cubes and perlin noise">
<figcaption>-- Terrain generation using cubes and perlin noise.
</figcaption>
</figure>

```csharp
public GameObject prefab;

// Start is called before the first frame update
void Start()
{
    int seedX = Random.Range(0, 1000);
    int seedZ = Random.Range(0, 1000);

    for (float z = 0; z < 100; z++)
    { 
        for (float x = 0; x < 100; x++)
        {
            float y = Mathf.PerlinNoise((x+seedX) * 0.1f, (z+seedZ) * 0.1f) * 2f;

            if (y > 1) //threshold, only spawn when y is greater than 1
            {

                GameObject instance = Instantiate(prefab);
                instance.transform.position = new Vector3(x, y*10, z);
            }
        }
    }
}
```

<br>

---

## Custom Classes for Storing Data

Review from [our first introduction of C#](./w0-unity-csharp.md/#unity-c):

> We typically write Unity C# scripts to **make customised blueprints for accessing, organising, and implementing data** inside our game project. This is helpful for:
> 
> - storing information such as variables and functions inside an object or class;
> - programming interactive / dynamic behaviour in objects;

Sometimes we need to write **custom classes to store data and functions** about specific objects.

For example, we could have a class that describes specific properties of an object. 

```csharp
public class Cat
{
    public string name;
    public string breed;
    public float size;
    public bool hasCollar;
    public Color furColor;
    public Color eyeColor;
}
```

<br>

One way of implementing these custom classes is to use them as **small "helper" classes** inside our scripts.

For example, we may want to create a custom class that contains a variety of colour schemes. 

Because we don't need this information to be attached to a GameObject as a component, we can leave it as a non-MonoBehaviour class. In this case, it's useful to mark this class as "serializable", so that the unity editor can see it and edit it.

*(Note: if your class is already a MonoBehaviour, Unity Editor can already see and edit it, so it does not need to the Serializable attribute.)*

```csharp
[System.Serializable]
public class ColorScheme
{
	public Color mainColor;
	public Color accent;
}
```

<br>

You can include this class in **the same script as one of your MonoBehaviour classes**, or **create a new c# file** to contain it.

From here, we could store a bunch of possible color schemes in a ColorScheme array, then determine the possible color schemes in the Inspector:

```csharp
public class ColorSchemeRandomizer:MonoBehaviour
{
	public ColorScheme[] colorSchemes;
	ColorScheme SelectedColorScheme;
	void Start()
	{
		SelectedColorScheme = colorSchemes[Random.Range(0,colorSchemes.Length)];
	}
}

[System.Serializable]
public class ColorScheme
{
	public Color mainColor;
	public Color accent;
}
```

<br>

---

## Some course reminders

- [Project 1](./project-1.md) is due next Tuesday.
- Instructions on [How To Submit](./how-to-submit.md) your Projects are now updated. 
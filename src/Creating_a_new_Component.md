# Creating a new Component
To create a new Component in code is not very difficult.
Each class that extends the abstract Component class is seen as a new Component.

There are three methods that can be overwritten when creating a new Component.  

Start()
```java
//Called at the first frame of the Scene the GameObject is in
@Overwrite
public void Start()
{
    Shader shader = this.gameObject.getComponent(SpriteRenderer).getShader();
}
```

Awake()
```java
//Called when the GameObject is activated the first time (this resets when the Scene of the GameObject is unloaded)
@Overwrite
public void Awake()
{
    //We assume the SpriteRender is not a Component of our GameObject when its first created, therefore we need a refrence to work with it
    SpriteRenderer sr = this.gameObject.getComponent(SpriteRenderer);
}
```
and last but not least  
  
Update()
```java
//Called every Frame
@Overwrite
public void Update(float deltaTime)
{
    if(KeyListener.isKeyPressed(Key.W.get()))
    {
        this.gameObject.position.y += 1 * deltaTime;
    }
}
```

<h4 style="color:red;">Coming in future versions!</h4>
FixedUpdate()

```java
//Called every FixedTimestep
@Overwrite
public void FixedUpdate()
{
    //Physic calculations should be done in here to make them independent on frame time
}
```

---
Tags:
- ❔類型/⭐精選/📖圖文教材
- ❔專業領域/⌨️Coding
---
Some practices to consider:  

1.  Always use at least a top-level namespace. This helps avoid conflicts with type names in third party plugins. They can also be a great organizational tool, and help keep your class names shorter.
2.  Consider sealing all classes by default. This can help improve performance, give better static code analysis and makes a clear distinction between classes that are derived from (and are much more dangerous to modify!) and leaf classes.
3.  Consider if you want to prefer event-based programming over polling for changes every frame in Update.
4.  Consider whether or not you want to always explicitly specify access modifiers (private, internal...) or if you want to leave them out when it's the default one.
5.  Decide if you want to use expression-bodied members.
6.  Consider using the common `-ing` / `-ed` convention for event naming. For example event Scene.Opening would be invoked right before a scene opens, and Scene.Opened would be invoked right after it has opened.
7.  Consider using the single-responsibility principle to guide you when deciding how much stuff to put inside a single component. For example a Player class could easily grow to be thousands of lines long if it contains the logic for reading inputs, moving the GameObject, jumping, crouching, playing animations, etc. If this functionality is broken down into multiple classes, it can help make those classes more focused, and easier to comprehend and modify without introducing bugs. Components that only do one thing are also much more reusable.
8.  Comments can arguably sometimes be a sign of badly named variables and methods or methods that are doing too many things and should be broken into smaller pieces. When you want to add a comment, consider if you could improve readability by refactoring the code instead.
9.  Consider adding XML documentation comments to your code. These can be handy because the IDE shows them as tooltips when hovering over type and member references. Having a general overview of what a component does can help save a lot of time, because you can quickly get a good understanding of its use cases without having to read through the code. Listing out what happens in more exceptional cases (if player does not exist, will PlayerManager.PlayerName be null or empty or throw an exception?) in method/property summaries can be really useful in avoiding bugs in places where they are called. Sometimes you can also realize ways you can improve your code while writing these summaries (Maybe I should add `bool TryGetPlayerName(out string name)` instead or returning null).
10.  If you have multiple instances of the Enemy prefab, and they all share some of the same stats like Speed and MaxHp, consider extracting the shared values into a ScriptableObject asset. This can help reduce memory use, loading times and makes it easier to change values for multiple objects in one place. It can also make it easer to try out different values in play mode, and have the changes affect all instances on-the-fly.
11.  Consider using properties instead of public fields, and only exposing a public get-accessor and making set private (or not adding one at all) when possible. The less places there are that can change the state of an object, the easier it is to keep track of it all and have it not break in some edge cases.  
12.  Consider specifying exact units used in variable names (e.g. ElapsedSeconds, DurationSeconds), summaries and / or by creating unique types for different units instead of using the same primitive types for everything. Ambiguity in code is bad, and bugs can be introduced when you think something is in in pixels but it's in viewport space units instead.
13.  Consider if you want to explicitly specify numeric types with their suffix ( `60f` , `60d` ), or rely on implicit conversions.
14.  Consider if you want to prefer using `var` over explicit types. If so, are there exceptions? Using var can have benefits like reducing noise/repetition and making it easier to change types of variables later on.
15.  Consider if you want to always organize your members in some particular order (for example events always first, then fields, then properties, then constructors, then methods, then nested types...).
16.  Consider how you want to approach null-handling. Do you want to guard against null everywhere? Do you want to do this at edit time (OnValidate), at runtime (Awake) or both? Do you want to mark variables that don't need to be null checked with ``[NotNull]` ? Or maybe you only null-check variables with the `[MaybeNull]` attribute.
17.  Consider avoiding abbreviations. How much benefit are you really gaining from writing `dbg` , `rb` and `mr` instead of `debug` , `rigidbody` and `meshRenderer` ? Abbreviations can introduce additional mental overhead when reading code that would not be needed if plain English was used. An exception to this rule would be abbreviation that are so common they can be used even more than the non-abbreviated form (GUI, HUD, ID, FBI...).

Example:  
  
```CSharp
namespace MyGame.Components
{
    /// <summary>
    /// Component that moves a <see cref="Movable"/> component based on the player's movement inputs.
    /// </summary>
    public sealed class InputProvider : MonoBehaviour
    {
        [SerializeField] private Movable movable;
 
        private void OnEnable() => InputManager.MoveInputGiven += OnMoveInputGiven;
        private void OnDisable() => InputManager.MoveInputGiven -= OnMoveInputGiven;
 
        private void OnMoveInputGiven(Vector2 moveInput) => movable.MoveDirection = moveInput;
    }
}
```

```CSharp
namespace MyGame.Components
{
    /// <summary>
    /// Component that enables objects to be moved.
    /// </summary>
    [RequireComponent(typeof(Rigidbody2D))]
    public sealed class Movable : MonoBehaviour
    {
        [SerializeField] private Rigidbody2D rigidbody;
        [SerializeField] private MovableSettings settings;
 
        /// <summary>
        /// Gets or sets the direction in which this object is currently moving.
        /// <para>
        /// Magnitude of the vector is clamped between 0 and 1.
        /// </para>
        /// </summary>
        public Vector2 MoveDirection
        {
            get => rigidbody.velocity.normalized;
            set => rigidbody.velocity = value.normalized * settings.Speed;
        }
 
        private void OnValidate() => rigidbody = GetComponent<Rigidbody2D>();
    }
}
```

```CSharp
namespace MyGame.Settings
{
    /// <summary>
    /// Specifies the settings for a <see cref="Movable"/> component.
    /// </summary>
    [CreateAssetMenu]
    public sealed class MovableSettings : ScriptableObject
    {
        [SerializeField, Min(0f), Tooltip(
        "The constant speed at which the object travels when it is moving.\n\n" +
        "In units per second.")]
        private float speed;
 
        /// <summary>
        /// The constant speed at which the object travels when moving.
        /// <para>
        /// In units per second.
        /// </para>
        /// </summary>
        public float Speed => speed;
    }

```

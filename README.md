# Demo

# Madlibs App
Made for CITC-2335
### Table of Contents
- [Documentation](#documentation)
  - [For Users](#for-users)
  - [For Devs](#for-devs)
- [Credits](#credits)

## Documentation

### For Users
<details open>

<summary>Information on how to use the app.</summary>

#### How to use the app
**This still needs to be done**<br/>This should have screenshots <br/> and information on how to do stuff!
</details>

### For Devs
<details open>

<summary>Information on the project's classes</summary>

### Word.cs
The object that **Madlib.cs** uses to store information for blank spaces.<br/><br/>

**Constructors:**<br/>
| Declaration | Description |
| ----------- | ----------- |
| static Word() | This static constructor initializes the static Examples and ExtendType dictionaries when the class is first loaded. |
| public Word(string replace, string type) | This constructor initializes a new instance of the 'Word' class, setting the 'Replace' and 'Type' properties with the provided values. |

**Properties:**<br/>
| Declaration | Description |
| ----------- | ----------- |
| public string Replace { get; set; } | The word to replace the blank with. |
| public string Type { get; set; } | The type of word (noun, adjective, etc.) |
| public static Dictionary<string, string> Examples { get; set; } | A static dictionary containing examples of valid word types, used to determine which type of word should be replaced in **Madlib.cs**. |
| private static Dictionary<string, string> ExtendType { get; set; } | A static dictionary that provides more readable descriptions of word types (e.g., "adjective" for "adj"). |

**Methods:**<br/>
| Declaration | Description |
| ----------- | ----------- |
| public string GetPrompt() | Generates a user prompt based on the word type, in plain English. If the word type has an extended description in ExtendType, it uses that; otherwise, it uses the original type. |
| private bool isVowel(char c) | Helper method that checks if a given character is a vowel (used in 'GetPrompt()' to decide whether to use "a" or "an"). |


### Story.cs
It processes a line of text to extract tags and stores the remaining text as a "story" template.<br/><br/>

**Constructors:**<br/>
| Declaration | Description |
| ----------- | ----------- |
| public Story(string line) | This constructor creates a new Story object. It looks for tags in the input line (inside {}), saves them in the Tags list, and removes them from the story text. The cleaned-up text is saved in the Str property. |

**Properties:**<br/>
| Declaration | Description |
| ----------- | ----------- |
| public List<string> Tags { get; set; } | A list that stores all the tags extracted from the story text (e.g., noun, adj). |
| public string Str { get; set; } = string.Empty; | The processed story text with the tags removed. |

**Methods:**<br/>
| Declaration | Description |
| ----------- | ----------- |
| public override string ToString() | This method creates a readable string that lists the tags and the story template. It's useful for debugging or displaying the object's data. |


### Storylist.cs
It handles a collection of Story objects and provides methods to populate and display them.<br/><br/>

**Constructors:**<br/>
| Declaration | Description |
| ----------- | ----------- |
| public StoryList() | Creates a new StoryList instance. Initializes a list of Story objects by retrieving string data using the IOSystem.GetAllStrings() method and converting each string into a Story object. |
| public StoryList(string path) | This overload constructor, creates a new StoryList instance using a specific file path. Retrieves string data from the provided path using the IOSystem.GetAllStrings(path) method and converts each string into a Story object, which is then added to the Stories list. Parameters: The file path to load the string data from. |

**Properties:**<br/>
| Declaration | Description |
| ----------- | ----------- |
| public List<Story> Stories { get; set; } | A list that stores Story objects. This property holds all the stories created from the data source. The property can be used to retrieve or modify the list of stories associated with the StoryList. |

**Methods:**<br/>
| Declaration | Description |
| ----------- | ----------- |
| public override string ToString() | Combines and formats all the stories in the Stories list into a single string. Each story's details are included on a new line for readability. |


**The rest of the classes need to be finished**

### Madlibs.cs
### IOSystem.cs

</details>

## Credits

To be added

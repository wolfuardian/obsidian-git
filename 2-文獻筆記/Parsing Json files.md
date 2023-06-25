---
website: Orfeas Eleftheriou
url: https://www.orfeasel.com/
tags: ❔狀態/⚡處理中
---
In this post we’re going to see how we can parse Json files in our Unreal Engine project.

For this post, I have created an empty project using the 4.18.3 version of the engine and inside my project’s Content folder I created a folder named JsonFiles and placed the following json document:

```json
{
  "Person": {
    "_id": "5aa416eb517758cfe840035d",
    "index": 0,
    "guid": "e617dc7d-47e2-4a5c-a5cb-b5a580c94b90",
    "isActive": true,
    "balance": "$3,352.85",
    "picture": "http://placehold.it/32x32",
    "age": 20,
    "eyeColor": "green",
    "name": "Ortiz Ochoa",
    "gender": "male",
    "company": "PETICULAR",
    "email": "ortizochoa@peticular.com",
    "latitude": -53.214897,
    "longitude": -156.96938,
    "family": [
      "Orfeas",
      "Kostas",
      "Vasilis"
    ]
  }
}
```
If you’re running your UE4 project while creating the above file, a popup window will be displayed notifiying you about new assets that you may be interested in importing inside the Editor. In this menu, select the “Don’t import” option. The reason behind this option is that in case we try to import our json file inside the Editor, Unreal Engine will unsuccessfully try to convert our file into either a DataTable or a Curve. Moreover, please note in case the json file is going to be a part of your shipping build, make sure to include the folder we created on the packaging details as well.

Once you have created the mentioned file, go to your project’s .Build.cs file and add the following line (so we can access the json related functions from our code later on):

PublicDependencyModuleNames.AddRange(new string[] { "Json", "JsonUtilities" });

In order to parse and access the data from our json file, we need to do the following:

1.  Get the json file from the saved location in our project
2.  Save its contents in a FString variable
3.  Convert the FString variable to a JsonObject that is supposed by the engine
4.  Use the built-in deserialize functions  for the JsonObject

If the deserialization is completed successfully, we will be able to parse all the required data in a pretty straightforward way.

So, in order to code every aforementioned step, create a new C++ class that inherits the Actor class and add the following code inside the BeginPlay function:

```c++
void AJsonParser::BeginPlay()
{
	Super::BeginPlay();

	const FString JsonFilePath = FPaths::ProjectContentDir() + "/JsonFiles/randomgenerated.json";
	FString JsonString; //Json converted to FString
	
	FFileHelper::LoadFileToString(JsonString,*JsonFilePath);

	//Displaying the json in a string format inside the output log
	GLog->Log("Json String:");
	GLog->Log(JsonString);

	//Create a json object to store the information from the json string
	//The json reader is used to deserialize the json object later on
	TSharedPtr<FJsonObject> JsonObject = MakeShareable(new FJsonObject());
	TSharedRef<TJsonReader<>> JsonReader = TJsonReaderFactory<>::Create(JsonString);

	if (FJsonSerializer::Deserialize(JsonReader, JsonObject) && JsonObject.IsValid())
	{
		//The person "object" that is retrieved from the given json file
		TSharedPtr<FJsonObject> PersonObject = JsonObject->GetObjectField("Person");

		//Getting various properties
		GLog->Log("Balance:" + PersonObject->GetStringField("balance"));
		GLog->Log("Age:" + FString::FromInt(PersonObject->GetIntegerField("age")));
		FString IsActiveStr = (PersonObject->GetBoolField("isActive")) ? "Active" : "Inactive";
		GLog->Log("IsActive:" + IsActiveStr);
		GLog->Log("Latitude:" + FString::SanitizeFloat(PersonObject->GetNumberField("latitude")));

		//Retrieving an array property and printing each field
		TArray<TSharedPtr<FJsonValue>> objArray=PersonObject->GetArrayField("family");
		GLog->Log("printing family names...");
		for(int32 index=0;index<objArray.Num();index++)
		{
			
			GLog->Log("name:"+objArray[index]->AsString());
		}
	}
	else
	{
		GLog->Log("couldn't deserialize");
	}

}
```

Moreover, **make sure to include the JsonUtilies.h header file in your source file**. This is needed in order to access the engine’s built-in deserialize functions. At this point, if you compile your code and place your Actors inside a level, you will see the following messages on your output log:

[![](https://i0.wp.com/orfeasel.com/wp-content/uploads/2018/03/jsonoutputresult.png?resize=980%2C435)](https://i0.wp.com/orfeasel.com/wp-content/uploads/2018/03/jsonoutputresult.png)

(Click on image to enlarge in a new tab)

For more information regarding the JsonValue and JsonObject classes you should check out the Engine’s source code over [here](https://github.com/EpicGames/UnrealEngine/tree/release/Engine/Source/Runtime/Json/Public/Dom).



![image](https://github.com/user-attachments/assets/e5a45ec9-6b4b-4789-baf3-dfaa18d59f4a)
```csharp
var environment = builder.Environment.EnvironmentName;
var config = new ConfigurationBuilder().AddJsonFile($"appsettings.{environment}.json", optional: false).Build();
builder.Configuration.AddConfiguration(config);

#here this section deals with configuring the appsettings fiel 
my motto was, when I call config.GetSection() method to retrieve any value from appsettings file then
I should be able to get the value from the appsettings files for the particular environment
for eg: if I am running my app in production environment and I whenever I call config.GetSection() method thenI should get value from the "appsettings.production.json
![image](https://github.com/user-attachments/assets/e5a45ec9-6b4b-4789-baf3-dfaa18d59f4a)

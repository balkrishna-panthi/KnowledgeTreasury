
```csharp
var environment = builder.Environment.EnvironmentName;
var config = new ConfigurationBuilder().AddJsonFile($"appsettings.{environment}.json", optional: false).Build();
builder.Configuration.AddConfiguration(config);
```
#h3 what am I trying to achieve
Here the above section deals with configuring the appsettings file.
My motto was, when I call config.GetSection() method to retrieve any value from appsettings file then I should be able to get the value from the appsettings files for the particular environment only.
for eg: if I am running my app in production environment and I whenever I call config.GetSection() method thenI should get value from the "appsettings.production.json


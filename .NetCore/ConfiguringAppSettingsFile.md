

# What am I trying to achieve ?

```csharp
var environment = builder.Environment.EnvironmentName;
var config = new ConfigurationBuilder().AddJsonFile($"appsettings.{environment}.json", optional: false).Build();
builder.Configuration.AddConfiguration(config);
```
Here the above code section deals with configuring the appsettings file.
My motto was, when I call config.GetSection() method to retrieve any value from appsettings file then I should be able to get the value from the appsettings files for the particular environment only.
for eg: if I am running my app in production environment and I whenever I call config.GetSection() method thenI should get value from the "appsettings.production.json

##Lets understand it with real demo
Here are my appsettings file in different environments
![image](https://github.com/user-attachments/assets/d78c6aeb-d02a-4c36-a9d8-42c7edd4ff6c) ![image](https://github.com/user-attachments/assets/b582b7d1-633c-4dc2-9dc5-c7e480e85beb)


1. First of all  I ran my app in Development environment as shown in the image below. Then called .GetSection() method to retrieve value from appsettings file
   ![image](https://github.com/user-attachments/assets/302efdff-b3d4-4091-96ec-021bc767f101)   ![image](https://github.com/user-attachments/assets/04bda86a-3c69-4780-8e25-4b876c66a5da)

2. Second time I ran the same code in production environment and called GetSection() method
![image](https://github.com/user-attachments/assets/8919a51c-13da-43ca-8991-d77156430ff0) ![image](https://github.com/user-attachments/assets/d35e703b-140c-4c89-bcc8-f0dd2751a430)







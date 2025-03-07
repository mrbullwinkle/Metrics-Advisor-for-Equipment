# ⭐Configuring alerts and getting notifications using a hook
After an anomaly is detected by Metrics Advisor for equipment, an alert notification will be triggered based on alert setting using a hook. An alert setting can be used with multiple detection configurations, various parameters are available to customize your alert rule. 

## 1. Create a hook

Currently, Metrics Advisor for equipment supports only one type of hooks: **Web hook.** 

A web hook is the entry point for all the information available from the Metrics Advisor service, and calls a user-provided api when an alert is triggered. All alerts can be sent through a web hook.

![image](https://user-images.githubusercontent.com/36343326/176588851-4f6c3e5c-dfb7-4500-854b-07552cfb0689.png)


To create a web hook, you will need to add the following information:
![image](https://user-images.githubusercontent.com/36343326/176589224-644b7bf0-565f-4c38-aa7d-53ae9929aa98.png)


| Parameter           | Description                                                  |
| ------------------- | ------------------------------------------------------------ |
| Endpoint            | The API address to be called when an alert is triggered.     |
| Username / Password | For authenticating to the API address. Leave this black if authentication isn't needed. |
| Header              | Custom headers in the API call.                              |



After Creating, you got a hook lists.

![image](https://user-images.githubusercontent.com/36343326/176588951-7211f100-dfca-4732-9080-2fea67ecf374.png)

## 2. Alert configuration and detail

![image](https://user-images.githubusercontent.com/36343326/176591650-a9007c26-a009-4a30-8d06-d30a6f90bb47.png)
![image](https://user-images.githubusercontent.com/36343326/176591665-53329e17-851a-4ecd-bbe3-ab344d039561.png)

### Add or edit alert attached hooks

Attached hooks can be modified on the alert detail pages.

![image](https://user-images.githubusercontent.com/36343326/176591680-a4d31a3f-bd5b-49ca-9179-ac1c6806ffaf.png)

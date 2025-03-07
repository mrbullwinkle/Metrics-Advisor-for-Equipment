# ⭐Creating a model and dataset

You've ingested your dataset, and you've reviewed any issues with the job, the files, or the sensors. You've also decided which sensors are providing the data that will be used to train your model. Now it's time to move forward with creating the model.

## 1. About the left navigation panel

After you navigate to the workspace,  a navigation panel appears in the left side of the Metrics Advisor for Equipment UI. 

The first three items in the left navigation panel—**Models**, **Datasets**, **Visualization** and **Settings**. If you select:

- **Models**, you can use the models navigation bar to access all existing models, or create a new model.
- **Datasets**, you can use the datasets navigation bar to access all existing datasets, or create a new dataset.
- **Visualization**, you can use the visualization navigation bar to access a inference graphs and contribution rank.
![image](https://user-images.githubusercontent.com/36343326/176643695-d39385ed-26f3-4501-bb36-d4f79559e532.png)


## 2. Create a new model

Click **Create a new model**.
![image](https://user-images.githubusercontent.com/36343326/175043087-24453360-a2a6-41db-85c9-cee02a0d1e5c.png)

When you create a model, the model name must be unique .The model name can contain the following:

- Make sure your name don't include any invalid characters, such as spaces.

- Valid characters are: 200 characters.

- Valid characters are: 0-9, a-z, A-Z, and # $ . \ - (hyphen) _ (underscore)

- Make sure that you don't have any duplicated names.

![image](https://user-images.githubusercontent.com/36343326/175043374-999d68a9-f23b-46ed-87b5-90dd5bf08e8e.png)



## 3. Create/Select a Dataset 

#### Create a new dataset

Click **Create dataset**, on the **Create dataset** page:

- For **Dataset Granularity**, the interval between consecutive data points in your time series data. Currently Metrics Advisor for Equipment support

  - 1 min
  -  min
  - 10 min
  - 30 min
  - 1h
  - 1day

- For **Data source**, the type of data source where your time series data is stored. Choose Azure SQL or Azure Blob. 

- For **Authentication type**,  you need to assign managed identity to Metrics-Advisor-for-Equipment. [How to assign role to a resource](https://github.com/MS-AI-Platform/MetricsAdvisorMultivariate/blob/main/managed_identity.md)

- For **Server name/Database name**,enter your DB name.

- For **Data schema**, Metrics Advisor for equipment accepts tables with only three columns:

  - The first column headers of the file are a timestamp that indicates the date and time. 
  - The second column headers contain the sensor name. 
  - The third column headers show the data value from the sensor.

  Click **Load** to complete the creation, then you can find the created dataset.

![image](https://user-images.githubusercontent.com/36343326/175043003-899fdd93-d535-4804-b341-e49410653217.png)

#### Preview dataset















## 4. Training Parameters

First, you'll specify the details of your model, such as its training time range, advanced settings.

![image](https://user-images.githubusercontent.com/36343326/175045723-4cb8bc63-bf87-4748-ae04-f790e0f805d6.png)

- When selecting training time range, you'll need to configure your input data. During that process, you'll make decisions about the balance between your training dataset and your evaluation dataset, and whether or not to use data labels.

- Under training time range-include, use the time pickers to select the training dates and time that you want to include in your model.

- Under training time range-exclude, use the timepickers to select the training dates and time that you want to exclude in your model.

Optionally, There are several advanced settings to enable data ingested in a customized way:

- `sliding Window` - How many data points are used to determine anomalies. An integer between 28 and 2,880. The default value is 300. If `sliding Window` is `k` for model training, then at least `k` points should be accessible from the source file during inference to get valid results.

> **_NOTE:_**  Please keep two things in mind when choosing a `slidingWindow` value:
>
> 1. The properties of your data: whether it's periodic and the sampling rate. When your data is periodic, you could set the length of 1 - 3 cycles as the `slidingWindow`. When your data is at a high frequency (small granularity) like minute-level or second-level, you could set a relatively higher value of `slidingWindow`.
> 2. The trade-off between training/inference time and potential performance impact. A larger `sliding Window` may cause longer training/inference time. There is **no guarantee** that larger `sliding Window`s will lead to accuracy gains. A small `sliding Window` may cause the model difficult to converge to an optimal solution. For example, it is hard to detect anomalies when `sliding Window` has only two points.

- Missing data Filling Method – we will automatically fill in missing data. Options are Linear, Previous, Subsequent, and Customized, and the default value is Linear.
- However, if too much original data is missing, it might affect your results.

Choose **Create**.

## 5. Training model detail

Starting the training process. Click the **model name**, then the **Training model detail** tab gives you a chance review model details such as the model name, the dataset, and training time range.

There are four kinds of training model status.

| Status    | Description                                |
| --------- | ------------------------------------------ |
| Running   | Training is in processing.                 |
| Completed | Training is done, you can start inference. |
| Failed    | Training is failed for some reason.        |

You can click the **View details** button for the error messages when you find the training model status gets to **Failed**.


## 6. Manage datasets

#### Search datasets by name

To search datasets by name you can enter a dataset name in the search box.

#### Sort datasets

Data feeds can be sorted by using the following methods:

- by created time

#### Delete your data feed

To delete a dataset, you need to complete the following steps:

1. On the datasets list page, click 'Delete' on the data feed.

2. In the dataset details page, click 'Delete'.


![image](https://user-images.githubusercontent.com/36343326/176643089-c06e12b8-0045-4ccd-b598-1b44ba1122ee.png)


## 7. Manage models

#### Search models by name

To search models by name you can enter a model name in the search box.

#### Sort models 

Models can be sorted by using the following methods:

- by created time

#### Delete your models 

To delete a model, you need to complete the following steps:

On the **Training detail** page, click 'Delete'.

![image](https://user-images.githubusercontent.com/36343326/176643591-6121a31f-7229-43c1-9eff-28ac189cec73.png)


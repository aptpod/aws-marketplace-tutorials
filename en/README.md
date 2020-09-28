# intdash SDK for Python tutorials (for AWS Marketplace)

This is a collection of intdash SDK for Python tutorials for AWS Market Place. Please also see [Documentation of intdash SDK for Python](https://docs.intdash.jp/sdk/python/latest/en).

## Tutorials

**1_process-acquisition-data: Processing the server data using SDK**  
The code of "intdash tutorial 1C: Processing the server data using intdash SDK". This code shows how to retrieve and process the measurement data uploaded as a CSV file.

**2_upload-csv-data.ipynb: Uploading multiple CSV files using SDK**  
The code of "intdash tutorial 1D: Uploading a large amount of CSV files using intdash SDK". This code shows how to upload multiple CSV files at once and convert to measurements.

**3_save-data-as-csv: Saving data from the smartphone as CSV**  
The code of "intdash tutorial 2B: Saving the data sent from the smartphone to the PC". This code shows how to retrieve the smartphone data from intdash and save in CSV format.

**4_acquisition-image-data: Saving image data transmitted from the smartphone as image files**  
The code of "intdash tutorial 2B: Saving the data sent from the smartphone to the PC". This code shows how to retrieve the smartphone video data from intdash and save in M-JPEG format.

**5_realtime-streaming-execution-processing: Processing the smartphone data in real time and sending back to the server**  
The code of "intdash tutorial 2C: Process the data acquired from the smartphone in real time". This code shows how to process the smartphone data in real time and send it back to the server.

**0_create-signal-general-sensor: Signal definition samples for general sensor type (\*)**  

Code to register the signal definition. Signal definitions are required when converting time series data to physical values on the server side.  

(\*)  Execute only if the signal definition is not registered on the server side.  

## Preparation 

### Prepare the operating environment

This tutorial files are in Jupyter Notebook format that combines documentation and code. Therefore, the Jupyter Notebook operating environment is required to execute the code.

If you install using [anaconda](https://www.anaconda.com/), you can build a Python environment with Jupyter Notebook.

If you already have a Python environment, you can install Jupyter Notebook by using `pip`.

```
$ pip install jupyter
```

### install intdash SDK for Python

Install with the following command:

```
$ pip install intdash
```

### Creating a client

Create a client by using the authentication information (issued edge account).
When generating a client, specify **edge token** or **username/password combination** as authentication information.

Edge token

```
  import intdash

  client = intdash.Client(
	  url = "https://example.intdash.jp",
	  edge_token = "your_token",
  )
```

Username/password

```
  import intdash

  client = intdash.Client(
      url = "https://hoge.intdash.jp",
      username = "your_username_here",
      password = "your_password_here",
  )
```

### Register signal definitions

In this tutorial, there are cases where signal definitions (definition for converting time series data to physical values) are used when retrieving time series data. For details, refer to `0_create-signal-general-sensor`.

#### Tutorials that need signal definitions

* 3_save-data-as-csv
* 5_realtime-streaming-execution-processing

### Preparing the application

In this sample code, the following products are used for data transmission and data visualization. See the intdash tutorial for how to use these products.

- Data transmission: **Visual M2M Motion**
- Data visualization: **Visual M2M Data Visualizer**

This documentation records details of modeling the Zhongtianshe Watershed by SWAT+. Modeling procedures are divided into two parts according to different tools. The first is the main procedures using QSWAT+. The second is editing inputs of the model in SWAT+ Editor and running SWAT+.

## 1. QSWAT+ (v1.2.2)

### 1.1 Delineate watershed

1. Import DEM of the Zhongtianshe watershed

2. Burn in existing stream network

   - Import the real stream network for the burn-in.

   - Set the suitable channel and stream threshold to create streams.

3. Set the watershed outlet and pond/wetland to create watershed

4. Create landscape

   - Use DEM inversion method with 0.14 of the slope position threshold to create landscape units (LSUs). The ridge threshold is set as the stream threshold, which is the default value.

     <img src="https://github.com/Git160/Picture/raw/main/Zhongtianshe/1.1.3.jpg" alt="1.1.3" style="zoom:67%;" />

The details of delineating watershed as the following figure shown:

<img src="https://github.com/Git160/Picture/raw/main/Zhongtianshe/1.1Delineate watershed.jpg" alt="1.1" style="zoom:70%;" />

### 1.2  Create HRUs

1. Import landuse map and landuse table

2. Import soil map, select "usersoil" as soil data and import usersoil table

3. Read the LSU file (such as invflood0_14.tif) and select “Generate FullHRUs shapefile” to generate the full shapefile of HRUs

4. Create HRUs

   - In order to create HRUs of the whole watershed, select Single/Multiple HRUs - Filter by landuse, soil, slope - 0%, 0%, 0%

<img src="https://github.com/Git160/Picture/raw/main/Zhongtianshe/1.2.jpg" alt="1.2" style="zoom:57%;" />

## 2. SWAT+ Editor (v1.2.3) & SWAT+ (v59.3)

### 2.1 Edit inputs

1. Import climate data

   - Weather Generator: 

     Import the weather generator data (CSV files). It is noted that "using observed weather data" needs to be selected because the observed weather data is available.

     <img src="https://github.com/Git160/Picture/raw/main/Zhongtianshe/2.1wgn.jpg" alt="2.1.1" style="zoom:50%;" />

   - Weather Stations:

     Select SWAT+ format as the data format and import weather observed data. Choosing "Match files to existing stations" can match the observed data to existing wgn stations.

     <img src="https://github.com/Git160/Picture/raw/main/Zhongtianshe/2.1weather stations.jpg" alt="image-20221224133234837" style="zoom:50%;" />

2. Set Land Use Management - Management Schedules

   - import the prepared management schedules

   <img src="https://github.com/Git160/Picture/raw/main/Zhongtianshe/2.1.2.jpg" alt="2.1.2" style="zoom:57%;" />

### 2.2 Set simulation time and output

1. Set simulation time
   - For the Zhongtianshe Watershed, the warm-up period is 2011. The calibration period ranges from 2012 to 2013, and the validation period is from 2014 to 2015.

<img src="https://github.com/Git160/Picture/raw/main/Zhongtianshe/2.2.1.jpg" alt="2.2.1" style="zoom:55%;" />

<img src="https://github.com/Git160/Picture/raw/main/Zhongtianshe/2.2.2.jpg" alt="2.2.2" style="zoom:55%;" />

2. Select print object

   - Annual "losses routing unit output", "channel output" and "reservoir output" are used for calculating inputs of the Markov chain.

   - Daily "channel output" and annual "water balance basin output"are used for the model calibration and validation.

     <img src="https://github.com/Git160/Picture/raw/main/WillowRiver/2.2.2.png" alt="2.2.2" style="zoom:60%;" />

3. Write input files

   - Save changes and write the SWAT+ input files

### 2.3 Run SWAT+

1. Run SWAT+ and analyze output

2. Adjust the model parameters to calibrate and validate the model

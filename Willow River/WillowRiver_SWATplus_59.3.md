This documentation records details of modeling the Willow River Watershed by SWAT+. Modeling procedures are divided into two parts according to different tools. The first is main procedures using QSWAT+. The second is editing inputs of the model in SWAT+ Editor and running SWAT+.

## 1. QSWAT+ (v1.2.2)

### 1.1 Delineate watershed

1. Import DEM of the Willow River watershed

2. Burn in existing stream network

   - Import the real stream network for the burn-in.

   - Set the suitable channel and stream threshold to create streams.

3. Set the watershed outlet and pond/wetland to create watershed

4. Create landscape

   - Use DEM inversion method with 0.30 of the slope position threshold to create landscape units (LSUs). The ridge threshold is set as the stream threshold, which is the default value.

     <img src="https://github.com/Git160/Picture/raw/main/WillowRiver/1.1.3.png" width=50% height=50% />

The details of delineating watershed as the following figure shown:

<img src="https://github.com/Git160/Picture/raw/main/WillowRiver/1.1.png" width=50% height=50% />

### 1.2  Create HRUs

1. Import landuse map and landuse table

2. Import soil map and select SSURGO/STATSFO as soil data 

   Note: The soil database of this SWAT+ version is not complete, and we modified it according to SSURGO and altered the database.

3. Read the LSU file (such as invflood0_30.tif) and select “Generate FullHRUs shapefile” to generate the full shapefile of HRUs

4. Create HRUs

   - In order to create HRUs of the whole watershed, select Single/Multiple HRUs - Filter by landuse, soil, slope - 0%, 0%, 0%

<img src="https://github.com/Git160/Picture/raw/main/WillowRiver/1.2.png" width=50% height=50% />

## 2. SWAT+ Editor (v1.2.3) & SWAT+ (v59.3)

### 2.1 Edit inputs

1. Import climate data

   - Weather Generator: 

     We use the global SWAT+ wgn database as the weather generator data. It is noted that "using observed weather data" needs to be selected because the observed weather data is available.

     <img src="https://github.com/Git160/Picture/raw/main/WillowRiver/2.1.1.png" width=50% height=50% />

     

   - Weather Stations:

     Select SWAT+ format as the data format and import weather observed data. Choosing "Match files to existing stations" can match the observed data to existing wgn stations.

     <img src="https://github.com/Git160/Picture/raw/main/WillowRiver/2.1.1stations.png" width=50% height=50% />

2. Set Land Use Management - Management Schedules

   - import the prepared management schedules

   <img src="https://github.com/Git160/Picture/raw/main/WillowRiver/2.1.2.png" width=50% height=50% />

### 2.2 Set simulation time and output

1. Set simulation time
   - For the Willow River Watershed, a 2-year warm-up period is set. The calibration period ranges from 1 January 2012 to 31 July 2014, and the validation period is from 1 October 2010 to 31 December 2011.

<img src="https://github.com/Git160/Picture/raw/main/WillowRiver/2.2.1.png" width=50% height=50% />

2. Select print object

   - Annual "losses routing unit output", "channel output" and "reservoir output" are used for calculating inputs of the Markov chain.

   - Daily "channel output" and annual "water balance basin output"are used for the model calibration and validation.

     <img src="https://github.com/Git160/Picture/raw/main/WillowRiver/2.2.2.png" width=50% height=50% />

3. Write input files

   - Save changes and write the SWAT+ input files

### 2.3 Run SWAT+

1. Run SWAT+ and analyze output
2. Adjust the model parameters to calibrate and validate the model
   - cn2		 			pctchg	          10
   - esco                   abschg              -0.5
   - perco                 pctchg               -20
   - lat_len                pctchg              -30
   - surq_lag             absval              1.0
   - rsd_decomp      absval              0.1
   - denit_exp          absval              1.0
   - rsd_cover          absval              0.5
   - mid_n_stl           absval              12
   - n_stl                    absval              12


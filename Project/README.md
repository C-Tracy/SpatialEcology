# Modelling larval movement to estimate population connectivity of marine fish.

## Resources
OceanDrift
podaac data subscriber

## Installing Packages

```{bash}
pip install podaac-data-subscriber
conda install -c conda-forge cdo
```

## Downloading OSCAR Ocean Current Data
```{bash}
#set start and end date to your desired range
podaac-data-downloader -c OSCAR_L4_OC_third-deg -d ./data --start-date 2023-07-01T00:00:00Z --end-date 2023-07-15T00:00:00Z -e ""
```

Testing a different dataset from oscar: podaac-ops-cumulus-protected/OSCAR_L4_OC_FINAL_V2/ which only goes up to january 2021, so downloading for 2020
```
podaac-data-downloader -c OSCAR_L4_OC_FINAL_V2.0 -d ./data --start-date 1993-01-01T00:00:00Z --end-date 1993-01-08T00:00:00Z -b="-98.733454,5.930441,-59.366430,30.404161"


```

Tring one final dataset from Oscar: Near real-time (available from 1/1/2021 to present)
```
podaac-data-downloader -c OSCAR_L4_OC_NRT_V2.0 -d ./data --start-date 2021-07-01T00:00:00Z --end-date 2021-07-31T00:00:00Z -b="-98.733454,5.930441,-59.366430,30.404161" -e ""
```

## Potential method to reformat data that isn't actually working for me at the moment
```
python3
ds = Dataset("combined.nc")
time_var = ds.variables['time']
dtime = num2date(time_var[:],time_var.units)
```
Current problems with above script are ds is read-only, and when I try to create a new file that has write permissions and then redefine it as ds from the read only, I have no way to save it after creating the file.


Combining .nc files
```python3
import xarray
ds = xarray.open_mfdataset('*.nc')
ds.to_netcdf('combined.nc')
```

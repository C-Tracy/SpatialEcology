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


# Modelling larval movement to estimate population connectivity of marine fish.

## Resources
OceanDrift
podaac data subscriber

## Installing Packages

```{bash}
pip install podaac-data-subscriber
```

## Downloading OSCAR Ocean Current Data
```{bash}
#set start and end date to your desired range
podaac-data-downloader -c OSCAR_L4_OC_third-deg -d ./data --start-date 2023-07-01T00:00:00Z --end-date 2023-07-15T00:00:00Z -e ""
```

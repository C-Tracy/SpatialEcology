# Forward in time analysis in OpenDrift for July 1-14, 2023. 
Change the time variable to change the start time, and change the timedelta(hours=XX) variable to change the duration of the run.

```python3
python3

from opendrift.readers import reader_netCDF_CF_generic
from opendrift.models.pelagicegg import PelagicEggDrift
from datetime import datetime, timedelta, date
o = PelagicEggDrift(loglevel=20) 
```



The following readers are those used by the OpenDrift GUI. Most were out of range for the study area, or out of the desired timeframe
```python3
o.add_readers_from_list(['/vol/vvfelles/opendrift/forcing_data/norkyst/norkyst_aggregate.nc', '/vol/vvfelles/opendrift/forcing_data/meps/meps_aggregate.nc', '/vol/vvfelles/opendrift/forcing_data/ecmwf/ecmwf_aggregate.nc', '/lustre/storeB/project/metproduction/products/norkyst/NorKyst-800m_ZDEPTHS_his_00.nc', '/lustre/storeB/project/metproduction/products/meps/thredds/latest/meps_lagged_6_h_latest_2_5km_latest.nc', 'https://thredds.met.no/thredds/dodsC/sea/norkyst800m/1h/aggregate_be', 'https://thredds.met.no/thredds/dodsC/mepslatest/meps_lagged_6_h_latest_2_5km_latest.nc', 'https://thredds.met.no/thredds/dodsC/fou-hi/barents_eps_zdepth_be', 'https://thredds.met.no/thredds/dodsC/cmems/mywavewam3km/dataset-wam-arctic-1hr3km-be.ncml', 'https://thredds.met.no/thredds/dodsC/ww3_4km_agg', 'https://thredds.met.no/thredds/dodsC/cmems/topaz6/dataset-topaz6-arc-15min-3km-be.ncml', '/vol/vvfelles/opendrift/forcing_data/topaz6/topaz6_aggregate.nc', 'https://thredds.met.no/thredds/dodsC/aromearcticlatest/latest/arome_arctic_lagged_12_h_latest_2_5km_latest.nc', '/vol/vvfelles/opendrift/forcing_data/aromearctic/aromearctic_aggregate.nc', 'https://nrt.cmems-du.eu/thredds/dodsC/cmems_obs-wind_glo_phy_nrt_l4_0.125deg_PT1H', 'https://pae-paha.pacioos.hawaii.edu/thredds/dodsC/ncep_global/NCEP_Global_Atmospheric_Model_best.ncd', 'https://nrt.cmems-du.eu/thredds/dodsC/cmems_mod_glo_wav_anfc_0.083deg_PT3H-i', 'https://nrt.cmems-du.eu/thredds/dodsC/cmems_mod_glo_phy_anfc_merged-uv_PT1H-i', '/vol/vvfelles/opendrift/forcing_data/mercator/mercator_aggregate.nc', 'https://tds.hycom.org/thredds/dodsC/GLBy0.08/latest', 'https://tds.hycom.org/thredds/dodsC/GLBy0.08/expt_93.0/uv3z'])
```

Here you will have to change the time variable to your desired start-time that populations will be seeded at. 
```python3
import datetime
time=datetime.datetime(2023, 7, 1)


o.seed_elements(-77.15568, 17.6825, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-79.05813, 9.80292, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-86.69962, 21.00950, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-81.71461, 12.52444, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-81.77975, 24.51933, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-97.27821, 21.60944, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-97.56401, 24.54354, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-84.96775, 21.84162, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-83.09258, 14.98559, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-79.880314, 15.83924, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
```



Run the analysis, 
```python3

o.run(duration=timedelta(hours=336), time_step=3600, outfile='pelagiceggdrift_14d_Jul12023.nc')
```


Viewing results
```python3
print(o)

o.plot(fast=True)
o.animation(fast=True, color='z')
```

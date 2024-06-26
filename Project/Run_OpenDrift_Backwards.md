# Backward in time analysis in OpenDrift for all 4 time periods (4 different runs). 

Run 1
```
python3

from opendrift.readers import reader_netCDF_CF_generic
from opendrift.models.pelagicegg import PelagicEggDrift
from datetime import datetime, timedelta, date
o = PelagicEggDrift(loglevel=20)

o.add_readers_from_list(['/vol/vvfelles/opendrift/forcing_data/norkyst/norkyst_aggregate.nc', '/vol/vvfelles/opendrift/forcing_data/meps/meps_aggregate.nc', '/vol/vvfelles/opendrift/forcing_data/ecmwf/ecmwf_aggregate.nc', '/lustre/storeB/project/metproduction/products/norkyst/NorKyst-800m_ZDEPTHS_his_00.nc', '/lustre/storeB/project/metproduction/products/meps/thredds/latest/meps_lagged_6_h_latest_2_5km_latest.nc', 'https://thredds.met.no/thredds/dodsC/sea/norkyst800m/1h/aggregate_be', 'https://thredds.met.no/thredds/dodsC/mepslatest/meps_lagged_6_h_latest_2_5km_latest.nc', 'https://thredds.met.no/thredds/dodsC/fou-hi/barents_eps_zdepth_be', 'https://thredds.met.no/thredds/dodsC/cmems/mywavewam3km/dataset-wam-arctic-1hr3km-be.ncml', 'https://thredds.met.no/thredds/dodsC/ww3_4km_agg', 'https://thredds.met.no/thredds/dodsC/cmems/topaz6/dataset-topaz6-arc-15min-3km-be.ncml', '/vol/vvfelles/opendrift/forcing_data/topaz6/topaz6_aggregate.nc', 'https://thredds.met.no/thredds/dodsC/aromearcticlatest/latest/arome_arctic_lagged_12_h_latest_2_5km_latest.nc', '/vol/vvfelles/opendrift/forcing_data/aromearctic/aromearctic_aggregate.nc', 'https://nrt.cmems-du.eu/thredds/dodsC/cmems_obs-wind_glo_phy_nrt_l4_0.125deg_PT1H', 'https://pae-paha.pacioos.hawaii.edu/thredds/dodsC/ncep_global/NCEP_Global_Atmospheric_Model_best.ncd', 'https://nrt.cmems-du.eu/thredds/dodsC/cmems_mod_glo_wav_anfc_0.083deg_PT3H-i', 'https://nrt.cmems-du.eu/thredds/dodsC/cmems_mod_glo_phy_anfc_merged-uv_PT1H-i', '/vol/vvfelles/opendrift/forcing_data/mercator/mercator_aggregate.nc', 'https://tds.hycom.org/thredds/dodsC/GLBy0.08/latest', 'https://tds.hycom.org/thredds/dodsC/GLBy0.08/expt_93.0/uv3z'])

import datetime
time=datetime.datetime(2023, 7, 15)

o.seed_elements(-77.15568, 17.6825, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-86.69962, 21.00950, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-81.77975, 24.51933, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-97.27821, 21.60944, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-84.96775, 21.84162, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-83.09258, 14.98559, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-97.0168, 27.81083, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-85.73839, 30.12581, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-81.23215, 29.70185, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-80.35607, 25.15388, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-82.74734, 27.64314, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-82.23086, 9.45264, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-79.70708, 9.55347, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)

o.run(duration=timedelta(hours=-336), time_step=-3600, outfile='pelagiceggdrift_back14d_Jul152023.nc')
```

Run2
```
python3

from opendrift.readers import reader_netCDF_CF_generic
from opendrift.models.pelagicegg import PelagicEggDrift
from datetime import datetime, timedelta, date
o = PelagicEggDrift(loglevel=20)

o.add_readers_from_list(['/vol/vvfelles/opendrift/forcing_data/norkyst/norkyst_aggregate.nc', '/vol/vvfelles/opendrift/forcing_data/meps/meps_aggregate.nc', '/vol/vvfelles/opendrift/forcing_data/ecmwf/ecmwf_aggregate.nc', '/lustre/storeB/project/metproduction/products/norkyst/NorKyst-800m_ZDEPTHS_his_00.nc', '/lustre/storeB/project/metproduction/products/meps/thredds/latest/meps_lagged_6_h_latest_2_5km_latest.nc', 'https://thredds.met.no/thredds/dodsC/sea/norkyst800m/1h/aggregate_be', 'https://thredds.met.no/thredds/dodsC/mepslatest/meps_lagged_6_h_latest_2_5km_latest.nc', 'https://thredds.met.no/thredds/dodsC/fou-hi/barents_eps_zdepth_be', 'https://thredds.met.no/thredds/dodsC/cmems/mywavewam3km/dataset-wam-arctic-1hr3km-be.ncml', 'https://thredds.met.no/thredds/dodsC/ww3_4km_agg', 'https://thredds.met.no/thredds/dodsC/cmems/topaz6/dataset-topaz6-arc-15min-3km-be.ncml', '/vol/vvfelles/opendrift/forcing_data/topaz6/topaz6_aggregate.nc', 'https://thredds.met.no/thredds/dodsC/aromearcticlatest/latest/arome_arctic_lagged_12_h_latest_2_5km_latest.nc', '/vol/vvfelles/opendrift/forcing_data/aromearctic/aromearctic_aggregate.nc', 'https://nrt.cmems-du.eu/thredds/dodsC/cmems_obs-wind_glo_phy_nrt_l4_0.125deg_PT1H', 'https://pae-paha.pacioos.hawaii.edu/thredds/dodsC/ncep_global/NCEP_Global_Atmospheric_Model_best.ncd', 'https://nrt.cmems-du.eu/thredds/dodsC/cmems_mod_glo_wav_anfc_0.083deg_PT3H-i', 'https://nrt.cmems-du.eu/thredds/dodsC/cmems_mod_glo_phy_anfc_merged-uv_PT1H-i', '/vol/vvfelles/opendrift/forcing_data/mercator/mercator_aggregate.nc', 'https://tds.hycom.org/thredds/dodsC/GLBy0.08/latest', 'https://tds.hycom.org/thredds/dodsC/GLBy0.08/expt_93.0/uv3z'])

import datetime
time=datetime.datetime(2023, 7, 29)
o.seed_elements(-77.15568, 17.6825, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-86.69962, 21.00950, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-81.77975, 24.51933, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-97.27821, 21.60944, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-84.96775, 21.84162, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-83.09258, 14.98559, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-97.0168, 27.81083, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-85.73839, 30.12581, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-81.23215, 29.70185, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-80.35607, 25.15388, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-82.74734, 27.64314, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-82.23086, 9.45264, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-79.70708, 9.55347, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)

o.run(duration=timedelta(hours=-336), time_step=-3600, outfile='pelagiceggdrift_back14d_Jul292023.nc')
```



Run 3
```
python3

from opendrift.readers import reader_netCDF_CF_generic
from opendrift.models.pelagicegg import PelagicEggDrift
from datetime import datetime, timedelta, date
o = PelagicEggDrift(loglevel=20)

import datetime
time=datetime.datetime(2023, 8, 15)

o.seed_elements(-77.15568, 17.6825, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-86.69962, 21.00950, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-81.77975, 24.51933, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-97.27821, 21.60944, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-84.96775, 21.84162, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-83.09258, 14.98559, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-97.0168, 27.81083, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-85.73839, 30.12581, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-81.23215, 29.70185, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-80.35607, 25.15388, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-82.74734, 27.64314, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-82.23086, 9.45264, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-79.70708, 9.55347, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)

o.run(duration=timedelta(hours=-336), time_step=-3600, outfile='pelagiceggdrift_back14d_Aug152023.nc')
```

Run 4
```
python3

from opendrift.readers import reader_netCDF_CF_generic
from opendrift.models.pelagicegg import PelagicEggDrift
from datetime import datetime, timedelta, date
o = PelagicEggDrift(loglevel=20)

o.add_readers_from_list(['/vol/vvfelles/opendrift/forcing_data/norkyst/norkyst_aggregate.nc', '/vol/vvfelles/opendrift/forcing_data/meps/meps_aggregate.nc', '/vol/vvfelles/opendrift/forcing_data/ecmwf/ecmwf_aggregate.nc', '/lustre/storeB/project/metproduction/products/norkyst/NorKyst-800m_ZDEPTHS_his_00.nc', '/lustre/storeB/project/metproduction/products/meps/thredds/latest/meps_lagged_6_h_latest_2_5km_latest.nc', 'https://thredds.met.no/thredds/dodsC/sea/norkyst800m/1h/aggregate_be', 'https://thredds.met.no/thredds/dodsC/mepslatest/meps_lagged_6_h_latest_2_5km_latest.nc', 'https://thredds.met.no/thredds/dodsC/fou-hi/barents_eps_zdepth_be', 'https://thredds.met.no/thredds/dodsC/cmems/mywavewam3km/dataset-wam-arctic-1hr3km-be.ncml', 'https://thredds.met.no/thredds/dodsC/ww3_4km_agg', 'https://thredds.met.no/thredds/dodsC/cmems/topaz6/dataset-topaz6-arc-15min-3km-be.ncml', '/vol/vvfelles/opendrift/forcing_data/topaz6/topaz6_aggregate.nc', 'https://thredds.met.no/thredds/dodsC/aromearcticlatest/latest/arome_arctic_lagged_12_h_latest_2_5km_latest.nc', '/vol/vvfelles/opendrift/forcing_data/aromearctic/aromearctic_aggregate.nc', 'https://nrt.cmems-du.eu/thredds/dodsC/cmems_obs-wind_glo_phy_nrt_l4_0.125deg_PT1H', 'https://pae-paha.pacioos.hawaii.edu/thredds/dodsC/ncep_global/NCEP_Global_Atmospheric_Model_best.ncd', 'https://nrt.cmems-du.eu/thredds/dodsC/cmems_mod_glo_wav_anfc_0.083deg_PT3H-i', 'https://nrt.cmems-du.eu/thredds/dodsC/cmems_mod_glo_phy_anfc_merged-uv_PT1H-i', '/vol/vvfelles/opendrift/forcing_data/mercator/mercator_aggregate.nc', 'https://tds.hycom.org/thredds/dodsC/GLBy0.08/latest', 'https://tds.hycom.org/thredds/dodsC/GLBy0.08/expt_93.0/uv3z'])

import datetime
time=datetime.datetime(2023, 8, 29)

o.seed_elements(-77.15568, 17.6825, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-86.69962, 21.00950, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-81.77975, 24.51933, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-97.27821, 21.60944, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-84.96775, 21.84162, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-83.09258, 14.98559, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-97.0168, 27.81083, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-85.73839, 30.12581, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-81.23215, 29.70185, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-80.35607, 25.15388, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-82.74734, 27.64314, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-82.23086, 9.45264, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)
o.seed_elements(-79.70708, 9.55347, z=-1, radius=2000, number=500,
                time=time, diameter=0.0014, neutral_buoyancy_salinity=31.25)

o.run(duration=timedelta(hours=-336), time_step=-3600, outfile='pelagiceggdrift_back14d_Aug292023.nc')
```

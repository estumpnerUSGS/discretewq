
<!-- README.md is generated from README.Rmd. Please edit that file -->

# discretewq

<!-- badges: start -->

[![R-CMD-check](https://github.com/InteragencyEcologicalProgram/discretewq/actions/workflows/R-CMD-check.yaml/badge.svg)](https://github.com/InteragencyEcologicalProgram/discretewq/actions/workflows/R-CMD-check.yaml)
[![Codecov test
coverage](https://codecov.io/gh/InteragencyEcologicalProgram/discretewq/branch/main/graph/badge.svg)](https://codecov.io/gh/InteragencyEcologicalProgram/discretewq?branch=main)
[![DOI](https://zenodo.org/badge/309747392.svg)](https://zenodo.org/badge/latestdoi/309747392)
[![Data
DOI](https://img.shields.io/badge/Data%20publication%20DOI-10.6073/pasta/567ca1dce56cc819b1819117538bd718-blue.svg)](https://portal.edirepository.org/nis/mapbrowse?scope=edi&identifier=731)
<!-- badges: end -->

The goal of discretewq is to integrate discrete water quality data from
the San Francisco Estuary.

## Installation

You can install the latest version from [GitHub](https://github.com/)
with:

``` r
# install.packages("devtools")
devtools::install_github("InteragencyEcologicalProgram/discretewq")
```

## Usage

To obtain the full integrated water quality dataset

``` r
require(discretewq)
#> Loading required package: discretewq
Data <- wq(Sources = c("EMP", "STN", "FMWT", "EDSM", "DJFMP",
                       "SDO", "SKT", "SLS", "20mm", "Suisun", 
                       "Baystudy", "USBR", "USGS_SFBS", "YBFMP", 
                       "USGS_CAWSC", "NCRO"))

str(Data)
#> tibble [355,196 × 79] (S3: tbl_df/tbl/data.frame)
#>  $ Source                       : chr [1:355196] "DWR_NCRO" "DWR_NCRO" "DWR_NCRO" "DWR_NCRO" ...
#>  $ Station                      : chr [1:355196] "Old River at Bacon Island" "Old River at Bacon Island" "Old River at Bacon Island" "Old River at Bacon Island" ...
#>  $ Latitude                     : num [1:355196] 38 38 38 38 38 ...
#>  $ Longitude                    : num [1:355196] -122 -122 -122 -122 -122 ...
#>  $ Date                         : POSIXct[1:355196], format: "1999-03-17" "1999-03-31" ...
#>  $ Datetime                     : POSIXct[1:355196], format: "1999-03-17 09:45:00" "1999-03-31 10:00:00" ...
#>  $ Secchi                       : num [1:355196] NA NA NA NA NA NA NA NA NA NA ...
#>  $ Microcystis                  : num [1:355196] NA NA NA NA NA NA NA NA NA NA ...
#>  $ Temperature                  : num [1:355196] 12.4 13.6 12.5 17 16.4 17.1 17.8 18.4 16.2 16.2 ...
#>  $ Conductivity                 : num [1:355196] 211 217 216 284 273 172 395 446 250 252 ...
#>  $ DissolvedOxygen              : num [1:355196] 9.8 9.9 9.5 8.9 8.45 8.28 8.8 7.6 9.2 9.4 ...
#>  $ DissolvedOxygen_bottom       : num [1:355196] NA NA NA NA NA NA NA NA NA NA ...
#>  $ pH                           : num [1:355196] 7.7 NA 7.65 7.94 7.85 7.61 NA NA NA NA ...
#>  $ TurbidityNTU                 : num [1:355196] NA NA NA NA NA NA NA NA NA NA ...
#>  $ TurbidityFNU                 : num [1:355196] NA NA NA NA NA NA NA NA NA NA ...
#>  $ TotAlkalinity_Sign           : chr [1:355196] "=" "=" "=" "=" ...
#>  $ TotAlkalinity                : num [1:355196] NA NA NA NA NA NA NA NA NA NA ...
#>  $ DissAmmonia_Sign             : chr [1:355196] "=" "=" "=" "=" ...
#>  $ DissAmmonia                  : num [1:355196] NA NA NA NA NA NA 0.07 0.36 0.05 0.1 ...
#>  $ DissBromide_Sign             : chr [1:355196] "=" "=" "=" "=" ...
#>  $ DissBromide                  : num [1:355196] NA NA NA NA NA NA NA NA NA NA ...
#>  $ DissCalcium_Sign             : chr [1:355196] "=" "=" "=" "=" ...
#>  $ DissCalcium                  : num [1:355196] NA NA NA NA NA NA NA NA NA NA ...
#>  $ DissChloride_Sign            : chr [1:355196] "=" "=" "=" "=" ...
#>  $ DissChloride                 : num [1:355196] 19 21 20 31 31 27 NA NA NA NA ...
#>  $ Chlorophyll_Sign             : chr [1:355196] "=" "=" "=" "=" ...
#>  $ Chlorophyll                  : num [1:355196] NA NA NA NA NA NA NA NA NA NA ...
#>  $ Pheophytin_Sign              : chr [1:355196] "=" "=" "=" "=" ...
#>  $ Pheophytin                   : num [1:355196] NA NA NA NA NA NA NA NA NA NA ...
#>  $ DissNitrateNitrite_Sign      : chr [1:355196] "=" "=" "=" "=" ...
#>  $ DissNitrateNitrite           : num [1:355196] NA NA NA NA NA NA 0.78 1.2 0.76 0.79 ...
#>  $ DOC_Sign                     : chr [1:355196] "=" "=" "=" "=" ...
#>  $ DOC                          : num [1:355196] NA NA NA NA NA NA NA NA NA NA ...
#>  $ TOC_Sign                     : chr [1:355196] "=" "=" "=" "=" ...
#>  $ TOC                          : num [1:355196] NA NA NA NA NA NA NA NA NA NA ...
#>  $ DON_Sign                     : chr [1:355196] "=" "=" "=" "=" ...
#>  $ DON                          : num [1:355196] NA NA NA NA NA NA 0.5 0.7 0.3 0.3 ...
#>  $ DissOrthophos_Sign           : chr [1:355196] "=" "=" "=" "=" ...
#>  $ DissOrthophos                : num [1:355196] NA NA NA NA NA NA 0.04 0.17 0.06 0.06 ...
#>  $ TotPhos_Sign                 : chr [1:355196] "=" "=" "=" "=" ...
#>  $ TotPhos                      : num [1:355196] NA NA NA NA NA NA NA NA NA NA ...
#>  $ TSS_Sign                     : chr [1:355196] "=" "=" "=" "=" ...
#>  $ TSS                          : num [1:355196] NA NA NA NA NA NA NA NA NA NA ...
#>  $ VSS_Sign                     : chr [1:355196] "=" "=" "=" "=" ...
#>  $ VSS                          : num [1:355196] NA NA NA NA NA NA NA NA NA NA ...
#>  $ TKN_Sign                     : chr [1:355196] "=" "=" "=" "=" ...
#>  $ TKN                          : num [1:355196] NA NA NA NA NA NA NA NA NA NA ...
#>  $ TDS_Sign                     : chr [1:355196] "=" "=" "=" "=" ...
#>  $ TDS                          : num [1:355196] NA NA NA NA NA NA NA NA NA NA ...
#>  $ Depth                        : num [1:355196] NA NA NA NA NA NA NA NA NA NA ...
#>  $ Tide                         : chr [1:355196] NA NA NA NA ...
#>  $ Secchi_estimated             : logi [1:355196] NA NA NA NA NA NA ...
#>  $ Temperature_bottom           : num [1:355196] NA NA NA NA NA NA NA NA NA NA ...
#>  $ Field_coords                 : logi [1:355196] FALSE FALSE FALSE FALSE FALSE FALSE ...
#>  $ Conductivity_bottom          : num [1:355196] NA NA NA NA NA NA NA NA NA NA ...
#>  $ Notes                        : chr [1:355196] NA NA NA NA ...
#>  $ DissolvedOxygenPercent       : num [1:355196] NA NA NA NA NA NA NA NA NA NA ...
#>  $ pH_bottom                    : num [1:355196] NA NA NA NA NA NA NA NA NA NA ...
#>  $ DissolvedOxygenPercent_bottom: num [1:355196] NA NA NA NA NA NA NA NA NA NA ...
#>  $ TurbidityNTU_bottom          : num [1:355196] NA NA NA NA NA NA NA NA NA NA ...
#>  $ TurbidityFNU_bottom          : num [1:355196] NA NA NA NA NA NA NA NA NA NA ...
#>  $ TotAmmonia_Sign              : chr [1:355196] NA NA NA NA ...
#>  $ TotAmmonia                   : num [1:355196] NA NA NA NA NA NA NA NA NA NA ...
#>  $ TotChloride_Sign             : chr [1:355196] NA NA NA NA ...
#>  $ TotChloride                  : num [1:355196] NA NA NA NA NA NA NA NA NA NA ...
#>  $ TON_Sign                     : chr [1:355196] NA NA NA NA ...
#>  $ TON                          : num [1:355196] NA NA NA NA NA NA NA NA NA NA ...
#>  $ DissSilica_Sign              : chr [1:355196] NA NA NA NA ...
#>  $ DissSilica                   : num [1:355196] NA NA NA NA NA NA NA NA NA NA ...
#>  $ Sample_depth_surface         : num [1:355196] NA NA NA NA NA NA NA NA NA NA ...
#>  $ Sample_depth_bottom          : num [1:355196] NA NA NA NA NA NA NA NA NA NA ...
#>  $ Salinity                     : num [1:355196] 0.0994 0.1023 0.1018 0.1346 0.1293 ...
#>  $ Salinity_bottom              : num [1:355196] NA NA NA NA NA NA NA NA NA NA ...
#>  $ Sample_depth_nutr_surface    : num [1:355196] NA NA NA NA NA NA NA NA NA NA ...
#>  $ MonthYear                    : POSIXct[1:355196], format: "1999-03-01" "1999-03-01" ...
#>  $ Year                         : num [1:355196] 1999 1999 1999 1999 1999 ...
#>  $ StationID                    : chr [1:355196] "DWR_NCRO Old River at Bacon Island" "DWR_NCRO Old River at Bacon Island" "DWR_NCRO Old River at Bacon Island" "DWR_NCRO Old River at Bacon Island" ...
#>  $ Month                        : num [1:355196] 3 3 4 4 4 5 5 5 5 5 ...
#>  $ Season                       : chr [1:355196] "Spring" "Spring" "Spring" "Spring" ...
```

## Data publication

The dataset is also [published on the Environmental Data
Initiative](https://portal.edirepository.org/nis/mapbrowse?scope=edi&identifier=731),
where you can find detailed metadata. This static version of the dataset
corresponds to version 2.3.2 of the R package ([archived on
zenodo](https://zenodo.org/record/6390964)).

## Data sources

Battey, M. and S. Perry. 2023. Interagency Ecological Program: Discrete
water quality monitoring in the Sacramento-San Joaquin Bay-Delta,
collected by the Environmental Monitoring Program, 1975-2022 ver 8.
Environmental Data Initiative.
[doi:10.6073/pasta/bcff9e330b7d99a9c5c9bda5e168cfc9](https://portal.edirepository.org/nis/metadataviewer?packageid=edi.458.8)

CDFW. 2022a. Bay Study data.
<https://filelib.wildlife.ca.gov/Public/BayStudy/Access_Database/>.

CDFW. 2022b. Fall Midwater Trawl data.
<https://filelib.wildlife.ca.gov/public/TownetFallMidwaterTrawl/FMWT%20Data/>.

CDFW. 2022c. Summer Townet data.
<https://filelib.wildlife.ca.gov/public/TownetFallMidwaterTrawl/TNS%20MS%20Access%20Data/TNS%20data/>.

CDWR. 2022. Water Quality Evaluation Section, North Central Region
Office.
<https://wdl.water.ca.gov/waterdatalibrary/WaterQualityDataLib.aspx>.

Cloern, J. E., and T. S. Schraga. 2016. USGS Measurements of Water
Quality in San Francisco Bay (CA), 1969-2015 (ver. 3.0 June 2017). U. S.
Geological Survey data release.
[doi:https://doi.org/10.5066/F7TQ5ZPR](https://doi.org/10.5066/F7TQ5ZPR)

Interagency Ecological Program (IEP), S. Lesmeister, and J. Rinde. 2020.
Interagency Ecological Program: Discrete dissolved oxygen monitoring in
the Stockton Deep Water Ship Channel, collected by the Environmental
Monitoring Program, 1997-2018. ver2. Environmental Data Initiative.
[doi:10.6073/PASTA/3268530C683726CD430C81894FFAD768](https://portal.edirepository.org/nis/metadataviewer?packageid=edi.276.2)

Interagency Ecological Program (IEP), L. Damon, and A. Chorazyczewski.
2021a. Interagency Ecological Program San Francisco Estuary 20mm Survey
1995 - 2021. ver 4. Environmental Data Initiative.
[doi:10.6073/pasta/32de8b7ffbe674bc6e79dbcd29ac1cc2](https://portal.edirepository.org/nis/metadataviewer?packageid=edi.535.4)

Interagency Ecological Program (IEP), L. Damon, and A. Chorazyczewski.
2021b. Interagency Ecological Program San Francisco Estuary Spring
Kodiak Trawl Survey 2002 - 2021. ver 4. Environmental Data Initiative.
[doi:10.6073/pasta/f0e2916f4a026f3f812a0855cee74a8d](https://portal.edirepository.org/nis/metadataviewer?packageid=edi.527.4)

Interagency Ecological Program (IEP), L. Damon, T. Tempel, and A.
Chorazyczewski. 2021c. Interagency Ecological Program San Francisco
Estuary Smelt Larva Survey 2009 – 2021. ver 4. Environmental Data
Initiative.
[doi:10.6073/pasta/8e1ceb1c02fbc8b0ba7a6b58229109f2](https://portal.edirepository.org/nis/metadataviewer?packageid=edi.534.4)

Interagency Ecological Program (IEP), C. Pien, J. Adams, and N. Kwan.
2021d. Interagency Ecological Program: Zooplankton catch and water
quality data from the Sacramento River floodplain and tidal slough,
collected by the Yolo Bypass Fish Monitoring Program, 1998-2018. ver 2.
Environmental Data Initiative.
[doi:10.6073/pasta/baad532af96cba1d58d43b89c08ca081](https://portal.edirepository.org/nis/metadataviewer?packageid=edi.494.2)

Interagency Ecological Program (IEP), R. McKenzie, J. Speegle, A.
Nanninga, J.R. Cook, J. Hagen, and B. Mahardja. 2022a. Interagency
Ecological Program: Over four decades of juvenile fish monitoring data
from the San Francisco Estuary, collected by the Delta Juvenile Fish
Monitoring Program, 1976-2021. ver 9. Environmental Data Initiative.
[doi:10.6073/pasta/30a3232084be9c936c976fbb6b31c5a2](https://portal.edirepository.org/nis/metadataviewer?packageid=edi.244.9)

Interagency Ecological Program (IEP), C. Pien, and N. Kwan. 2022b.
Interagency Ecological Program: Fish catch and water quality data from
the Sacramento River floodplain and tidal slough, collected by the Yolo
Bypass Fish Monitoring Program, 1998-2021. ver 3. Environmental Data
Initiative.
[doi:10.6073/pasta/f5c4362f4a1f370723e2b9113432909f](https://portal.edirepository.org/nis/metadataviewer?packageid=edi.233.3)

O’Rear, T., J. Durand, and P. Moyle. 2022. Suisun Marsh Fish Study.
<https://watershed.ucdavis.edu/project/suisun-marsh-fish-study>.

Schraga, T. S., E. S. Nejad, C. A. Martin, and J. E. Cloern. 2020. USGS
measurements of water quality in San Francisco Bay (CA), beginning in
2016 (ver. 3.0, March 2020). U. S. Geological Survey data release.
[doi:https://doi.org/10.5066/F7D21WGF](https://doi.org/10.5066/F7D21WGF)

United States Fish and Wildlife Service, T. Senegal, R. Mckenzie, J.
Speegle, B. Perales, D. Bridgman, K. Erly, S. Staiger, A. Arrambide, and
M. Gilbert. 2022. Interagency Ecological Program and US Fish and
Wildlife Service: San Francisco Estuary Enhanced Delta Smelt Monitoring
Program data, 2016-2021 ver 8. Environmental Data Initiative.
[doi:10.6073/pasta/e1a540c161b7be56b941df50fd7b44c5](https://portal.edirepository.org/nis/metadataviewer?packageid=edi.415.8)

U.S. Geological Survey. 2022. USGS water data for the Nation: U.S.
Geological Survey National Water Information System database, accessed
October 21, 2022, at
[doi:10.5066/F7P55KJN](https://doi.org/10.5066/F7P55KJN)

USBR, R. Dahlgren, L. Loken, and E. Van Nieuwenhuyse. 2020. Monthly
vertical profiles of water quality in the Sacramento Deep Water Ship
Channel 2012-2019. <https://www.usbr.gov/mp/bdo/index.html>

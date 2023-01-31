
<!-- README.md is generated from README.Rmd. Please edit that file -->

# discretewq

<!-- badges: start -->

[![R build
status](https://github.com/InteragencyEcologicalProgram/discretewq/workflows/R-CMD-check/badge.svg)](https://github.com/InteragencyEcologicalProgram/discretewq/actions)
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
#> tibble [351,451 × 72] (S3: tbl_df/tbl/data.frame)
#>  $ Source                       : chr [1:351451] "DWR_NCRO" "DWR_NCRO" "DWR_NCRO" "DWR_NCRO" ...
#>  $ Station                      : chr [1:351451] "BET" "BET" "BET" "BET" ...
#>  $ Date                         : POSIXct[1:351451], format: "2014-05-20" "2014-06-04" ...
#>  $ Datetime                     : POSIXct[1:351451], format: "2014-05-20 11:30:00" "2014-06-04 12:45:00" ...
#>  $ Latitude                     : num [1:351451] 38 38 38 38 38 ...
#>  $ Longitude                    : num [1:351451] -122 -122 -122 -122 -122 ...
#>  $ Secchi                       : num [1:351451] NA NA NA NA NA NA NA NA NA NA ...
#>  $ Microcystis                  : num [1:351451] NA NA NA NA NA NA NA NA NA NA ...
#>  $ Temperature                  : num [1:351451] 19.7 22 22.5 22.9 23.1 24.2 22.8 22.6 21.9 21.8 ...
#>  $ Conductivity                 : num [1:351451] 562 820 995 801 860 786 775 815 805 952 ...
#>  $ DissolvedOxygen              : num [1:351451] NA NA NA NA NA NA NA NA NA NA ...
#>  $ DissolvedOxygen_bottom       : num [1:351451] NA NA NA NA NA NA NA NA NA NA ...
#>  $ pH                           : num [1:351451] 7.77 8.83 8.87 8.15 8.36 8.51 8.34 8.52 8.41 8.14 ...
#>  $ Turbidity                    : num [1:351451] 4.69 2.16 2.64 4.46 2.66 1.82 1.81 1.38 1.91 1.69 ...
#>  $ TotAlkalinity_Sign           : chr [1:351451] NA NA NA NA ...
#>  $ TotAlkalinity                : num [1:351451] NA NA NA NA NA NA NA NA NA NA ...
#>  $ DissAmmonia_Sign             : chr [1:351451] "=" "=" "=" "=" ...
#>  $ DissAmmonia                  : num [1:351451] 0.05 0.04 0.03 0.04 0.02 0.03 0.02 0.02 0.02 0.02 ...
#>  $ DissChloride_Sign            : chr [1:351451] "=" "=" "=" "=" ...
#>  $ DissChloride                 : num [1:351451] 103 176 221 173 195 174 171 183 178 214 ...
#>  $ DissCalcium_Sign             : chr [1:351451] NA NA NA NA ...
#>  $ DissCalcium                  : num [1:351451] NA NA NA NA NA NA NA NA NA NA ...
#>  $ Chlorophyll_Sign             : chr [1:351451] "=" "=" "=" "=" ...
#>  $ Chlorophyll                  : num [1:351451] 1.11 0.89 1.45 2.49 2.33 1.97 2.2 2.22 3.9 4.62 ...
#>  $ Pheophytin_Sign              : chr [1:351451] "=" "=" "=" "=" ...
#>  $ Pheophytin                   : num [1:351451] 0.92 0.52 0.35 0.52 0.8 0.54 0.45 0.51 0.83 0.96 ...
#>  $ DissBromide_Sign             : chr [1:351451] "=" "=" "=" "=" ...
#>  $ DissBromide                  : num [1:351451] 0.35 0.59 0.72 0.6 0.65 0.6 0.57 0.58 0.6 0.7 ...
#>  $ DissNitrateNitrite_Sign      : chr [1:351451] "=" "=" "=" "=" ...
#>  $ DissNitrateNitrite           : num [1:351451] 0.38 0.2 0.17 0.19 0.09 0.02 0.07 0.02 0.05 0.03 ...
#>  $ DOC_Sign                     : chr [1:351451] "=" "=" "=" "=" ...
#>  $ DOC                          : num [1:351451] 3.6 3.7 2.9 3.6 2.6 3.1 3.1 3.1 2.6 3 ...
#>  $ DON_Sign                     : chr [1:351451] "=" "=" "=" "=" ...
#>  $ DON                          : num [1:351451] 0.4 0.3 0.3 0.2 0.3 0.4 0.2 0.1 0.3 0.2 ...
#>  $ TKN_Sign                     : chr [1:351451] "=" "=" "=" "=" ...
#>  $ TKN                          : num [1:351451] 0.5 0.4 0.5 0.2 0.3 0.5 0.3 0.2 0.5 0.4 ...
#>  $ DissOrthophos_Sign           : chr [1:351451] "=" "=" "=" "=" ...
#>  $ DissOrthophos                : num [1:351451] 0.08 0.07 0.07 0.07 0.1 0.11 0.11 0.09 0.09 0.09 ...
#>  $ TotPhos_Sign                 : chr [1:351451] "=" "=" "=" "=" ...
#>  $ TotPhos                      : num [1:351451] 0.11 0.105 0.1 0.09 0.13 0.14 0.12 0.14 0.09 0.1 ...
#>  $ TOC_Sign                     : chr [1:351451] "=" "=" "=" "=" ...
#>  $ TOC                          : num [1:351451] 3.8 3.9 3 3.6 2.7 3 2.8 2.9 3.1 3.1 ...
#>  $ VSS_Sign                     : chr [1:351451] NA NA NA NA ...
#>  $ VSS                          : num [1:351451] NA NA NA NA NA NA NA NA NA NA ...
#>  $ TSS_Sign                     : chr [1:351451] "=" "=" "=" "=" ...
#>  $ TSS                          : num [1:351451] 4 2 3 4 1 1 2 1 2 2 ...
#>  $ Depth                        : num [1:351451] NA NA NA NA NA NA NA NA NA NA ...
#>  $ Tide                         : chr [1:351451] NA NA NA NA ...
#>  $ Secchi_estimated             : logi [1:351451] NA NA NA NA NA NA ...
#>  $ Temperature_bottom           : num [1:351451] NA NA NA NA NA NA NA NA NA NA ...
#>  $ Field_coords                 : logi [1:351451] FALSE FALSE FALSE FALSE FALSE FALSE ...
#>  $ Conductivity_bottom          : num [1:351451] NA NA NA NA NA NA NA NA NA NA ...
#>  $ Notes                        : chr [1:351451] NA NA NA NA ...
#>  $ DissolvedOxygenPercent       : num [1:351451] NA NA NA NA NA NA NA NA NA NA ...
#>  $ pH_bottom                    : num [1:351451] NA NA NA NA NA NA NA NA NA NA ...
#>  $ DissolvedOxygenPercent_bottom: num [1:351451] NA NA NA NA NA NA NA NA NA NA ...
#>  $ TotAmmonia                   : num [1:351451] NA NA NA NA NA NA NA NA NA NA ...
#>  $ TotChloride                  : num [1:351451] NA NA NA NA NA NA NA NA NA NA ...
#>  $ TON                          : num [1:351451] NA NA NA NA NA NA NA NA NA NA ...
#>  $ DissSilica_Sign              : chr [1:351451] NA NA NA NA ...
#>  $ DissSilica                   : num [1:351451] NA NA NA NA NA NA NA NA NA NA ...
#>  $ TDS                          : num [1:351451] NA NA NA NA NA NA NA NA NA NA ...
#>  $ Sample_depth_surface         : num [1:351451] NA NA NA NA NA NA NA NA NA NA ...
#>  $ Sample_depth_bottom          : num [1:351451] NA NA NA NA NA NA NA NA NA NA ...
#>  $ Salinity                     : num [1:351451] 0.271 0.401 0.49 0.391 0.421 ...
#>  $ Salinity_bottom              : num [1:351451] NA NA NA NA NA NA NA NA NA NA ...
#>  $ Sample_depth_nutr_surface    : num [1:351451] NA NA NA NA NA NA NA NA NA NA ...
#>  $ MonthYear                    : POSIXct[1:351451], format: "2014-05-01" "2014-06-01" ...
#>  $ Year                         : num [1:351451] 2014 2014 2014 2014 2014 ...
#>  $ StationID                    : chr [1:351451] "DWR_NCRO BET" "DWR_NCRO BET" "DWR_NCRO BET" "DWR_NCRO BET" ...
#>  $ Month                        : num [1:351451] 5 6 6 7 7 7 8 8 9 9 ...
#>  $ Season                       : chr [1:351451] "Spring" "Summer" "Summer" "Summer" ...
```

## Data publication

The dataset is also [published on the Environmental Data
Initiative](https://portal.edirepository.org/nis/mapbrowse?scope=edi&identifier=731),
where you can find detailed metadata. This static version of the dataset
corresponds to version 2.3.2 of the R package ([archived on
zenodo](https://zenodo.org/record/6390964)).

## Data sources

CDFW. 2020a. Bay Study data. <ftp://ftp.wildlife.ca.gov/BayStudy/>.

CDFW. 2020b. Fall Midwater Trawl data.
<ftp://ftp.wildlife.ca.gov/TownetFallMidwaterTrawl/FMWT%20Data/>.

CDFW. 2020c. Summer Townet data.
[ftp://ftp.wildlife.ca.gov/TownetFallMidwaterTrawl/TNS MS Access
Data/TNS
data/](ftp://ftp.wildlife.ca.gov/TownetFallMidwaterTrawl/TNS%20MS%20Access%20Data/TNS%20data/).

CDWR. 2022. Water Quality Investigations Section, North Central Region
Office.
<https://wdl.water.ca.gov/waterdatalibrary/WaterQualityDataLib.aspx>.

Cloern, J. E., and T. S. Schraga. 2016. USGS Measurements of Water
Quality in San Francisco Bay (CA), 1969-2015 (ver. 3.0 June 2017). U. S.
Geological Survey data release.
[doi:https://doi.org/10.5066/F7TQ5ZPR](https://doi.org/10.5066/F7TQ5ZPR)

Interagency Ecological Program (IEP), L. Damon, T. Tempel, and A.
Chorazyczewski. 2020a. Interagency Ecological Program San Francisco
Estuary 20mm Survey 1995 - 2020. Environmental Data Initiative.
[doi:10.6073/PASTA/DA7269F6B68975232A2665B211E57229](https://portal.edirepository.org/nis/mapbrowse?scope=edi&identifier=535&revision=2)

Interagency Ecological Program (IEP), L. Damon, T. Tempel, and A.
Chorazyczewski. 2020b. Interagency Ecological Program San Francisco
Estuary Spring Kodiak Trawl Survey 2002 - 2020. Environmental Data
Initiative.
[doi:10.6073/PASTA/2EDAAA415ABE672008E0AF7542AA5D31](https://portal.edirepository.org/nis/mapbrowse?scope=edi&identifier=527&revision=2)

Interagency Ecological Program (IEP), L. Damon, T. Tempel, and A.
Chorazyczewski. 2021c. Interagency Ecological Program San Francisco
Estuary Smelt Larva Survey 2009 – 2021. Environmental Data Initiative.
[doi:10.6073/PASTA/696749029898FEF9AD268435BEE54D3D](https://portal.edirepository.org/nis/mapbrowse?scope=edi&identifier=534&revision=3)

Interagency Ecological Program (IEP), S. Lesmeister, and J. Rinde. 2020.
Interagency Ecological Program: Discrete dissolved oxygen monitoring in
the Stockton Deep Water Ship Channel, collected by the Environmental
Monitoring Program, 1997-2018. Environmental Data Initiative.
[doi:10.6073/PASTA/3268530C683726CD430C81894FFAD768](https://portal.edirepository.org/nis/mapbrowse?packageid=edi.276.2)

Interagency Ecological Program (IEP), M. Martinez, and S. Perry. 2021.
Interagency Ecological Program: Discrete water quality monitoring in the
Sacramento-San Joaquin Bay-Delta, collected by the Environmental
Monitoring Program, 1975-2020. Environmental Data Initiative.
[doi:10.6073/PASTA/31F724011CAE3D51B2C31C6D144B60B0](https://portal.edirepository.org/nis/mapbrowse?scope=edi&identifier=458&revision=4)

Interagency Ecological Program (IEP), R. McKenzie, J. Speegle, A.
Nanninga, J. R. Cook, J. Hagen, and B. Mahardja. 2020c. Interagency
Ecological Program: Over four decades of juvenile fish monitoring data
from the San Francisco Estuary, collected by the Delta Juvenile Fish
Monitoring Program, 1976-2019. Environmental Data Initiative.
[doi:10.6073/PASTA/41B9EEBED270C0463B41C5795537CA7C](https://portal.edirepository.org/nis/mapbrowse?packageid=edi.244.4)

Interagency Ecological Program (IEP), C. Pien, and N. Kwan. 2022.
Interagency Ecological Program: Fish catch and water quality data from
the Sacramento River floodplain and tidal slough, collected by the Yolo
Bypass Fish Monitoring Program, 1998-2021. ver 3. Environmental Data
Initiative.
[doi:10.6073/pasta/f5c4362f4a1f370723e2b9113432909f](https://portal.edirepository.org/nis/mapbrowse?packageid=edi.233.3)

Interagency Ecological Program (IEP), C. Pien, J. Adams, and N. Kwan.
2021. Interagency Ecological Program: Zooplankton catch and water
quality data from the Sacramento River floodplain and tidal slough,
collected by the Yolo Bypass Fish Monitoring Program, 1998-2018. ver 2.
Environmental Data Initiative.
[doi:10.6073/pasta/baad532af96cba1d58d43b89c08ca081](https://portal.edirepository.org/nis/mapbrowse?packageid=edi.494.2)

O’Rear, T., J. Durand, and P. Moyle. 2020. Suisun Marsh Fish Study.
<https://watershed.ucdavis.edu/project/suisun-marsh-fish-study>.

Schraga, T. S., E. S. Nejad, C. A. Martin, and J. E. Cloern. 2020. USGS
measurements of water quality in San Francisco Bay (CA), beginning in
2016 (ver. 3.0, March 2020). U. S. Geological Survey data release.
[doi:https://doi.org/10.5066/F7D21WGF](https://doi.org/10.5066/F7D21WGF)

United States Fish And Wildlife Service, C. Johnston, S. Durkacz, and
others. 2020. Interagency Ecological Program and US Fish and Wildlife
Service: San Francisco Estuary Enhanced Delta Smelt Monitoring Program
data, 2016-2020. Environmental Data Initiative.
[doi:10.6073/PASTA/764F27FF6B0A7B11A487A71C90397084](https://portal.edirepository.org/nis/mapbrowse?packageid=edi.415.3)

U.S. Geological Survey. 2022. USGS water data for the Nation: U.S.
Geological Survey National Water Information System database, accessed
October 21, 2022, at
[doi:10.5066/F7P55KJN](https://doi.org/10.5066/F7P55KJN)

USBR, R. Dahlgren, L. Loken, and E. Van Nieuwenhuyse. 2020. Monthly
vertical profiles of water quality in the Sacramento Deep Water Ship
Channel 2012-2019.

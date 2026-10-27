---
title: "VicWaCI: Identifying synoptic types associated with wet/dry spells in Victoria"
author: "Carly Tozer"
date: "2026-10-27"
output: 
  html_document: 
    keep_md: true
---






``` r
#MONTHLY DATASETS
#reading in monthly rainfall datasets
Vic <- nc_open("/Users/toz008/Documents/VICWaCI/VicWaCI_inputData/agcd_v2-0-4_precip_total_victoria_monthly_1900-2025.nc")
NE <- nc_open("/Users/toz008/Documents/VICWaCI/VicWaCI_inputData/agcd_v2-0-4_precip_total_north-east-victoria_monthly_1900-2025.nc")
NW <- nc_open("/Users/toz008/Documents/VICWaCI/VicWaCI_inputData/agcd_v2-0-4_precip_total_north-west-victoria_monthly_1900-2025.nc")
SE <- nc_open("/Users/toz008/Documents/VICWaCI/VicWaCI_inputData/agcd_v2-0-4_precip_total_south-east-victoria_monthly_1900-2025.nc")
SW <- nc_open("/Users/toz008/Documents/VICWaCI/VicWaCI_inputData/agcd_v2-0-4_precip_total_south-west-victoria_monthly_1900-2025.nc")

#The start date is taken from the netcdf metadata
start_date <- as.Date("1900-01-16")
time <- ymd(start_date)+ dhours(ncvar_get(Vic,'time'))

Vic <- ncvar_get(Vic, "precip") 
NE <- ncvar_get(NE, "precip")
NW <- ncvar_get(NW, "precip")
SE <- ncvar_get(SE, "precip")
SW <- ncvar_get(SW, "precip")
```


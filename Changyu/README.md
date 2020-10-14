- `CountryName` - `country`
- `CountryCode` - `ISO_A3`
- `RegionName` - `province`
- `RegionCode` - (none, will generate by hand)
- `Date` - `date_start`

-----

# C

## `C1_School closing`

```python
if df_corona_net_china.type != "Closure and Regulation of Schools":
    return blank
else: 
    # check subtype
    if df_corona_net_china.compliance == "Voluntary":
        return 1
    elif df_corona_net_china.compliance == "Mandatory":
        if "all categories on the same date": 
            return 3
        else:
            return 2

sub_types = {
 'Higher education institutions (i.e. degree granting institutions)',
 'Preschool or childcare facilities (generally for children ages 5 and below)',
 'Primary Schools (generally for children ages 10 and below)',
 'Secondary Schools (generally for children ages 10 to 18)'
}
```
##  `C1_Flag` 


## `C2_Workplace closing`

```python
if df_corona_net_china.type != "Restriction and Regulation of Businesses":
    return blank
else: 
    # check subtype
    if df_corona_net_china.compliance == "Voluntary":
        return 1
    elif df_corona_net_china.compliance == "Mandatory":
        if all categories on the same date: 
            return 3
        else:
            return 2
        
sub_types = {
 'All or unspecified non-essential businesses',
 'Bars',
 'Mining and quarrying',
 'Non-Essential Commercial Businesses',
 'Other Non-Essential Businesses',
 'Personal Grooming Businesses (e.g. hair salons)',
 'Restaurants',
 'Retail Businesses'
}
```

## `C3_Cancel public events` 
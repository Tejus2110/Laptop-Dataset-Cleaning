#Laptop Data Set Cleaning
Basis Dataset Summary.
# Dataset Summary:
---
---
- Column info:
    - `company`: contains information about the company name of laptop.
    - `typename`: contains information about the type of laptop.
    - `screen_size`: contains information about the display size in inches.
    - `screen_resolution`: contains information about screen resolution and other display related info.
    - `processor`: contains information about the processor used in the laptop.
    - `ram`: ram size used in the laptop.
    - `memory` : ssd/hdd information.
    - `gpu` : graphics card related information.
    - `os` : operating system used.
    - `weight`: weight of laptop in kg.
    - `price`: price of laptop.

# Data Assessing
- Both manual and programatic.
---

- Table - df1

### Dirty Data (Data Quality)
---
- `company`: column contains some null values. * <i><u>Issue : Completeness</u></i>
- `typename`: column contains null values. * <i><u>Issue : Completeness</u></i>
- `screen_size`:
  - column contains null values. * <i><u>Issue : Completeness</u></i>
  - ? is present at some values. * <i><u>Issue : Validity</u></i>
- `screen_resolution`: null values. * <i><u>Issue : Completeness</u></i>
- `processor`:
  - column contains null values. * <i><u>Issue : Completeness</u></i>
- `ram`: null values and data type is string. * <i><u>Issue : Completeness and Accuracy</u></i>
- `memory` :
  - null values * <i><u>Issue : Completeness</u></i>
  - some values have string attached to it - flash storage - which represents ssd kind of storage. * <i><u>Issue : Consistency</u></i>
- `gpu`: null values * <i><u>Issue : Completeness</u></i>
- `os`:
  - null values * <i><u>Issue : Completeness</u></i>
  - some models have android as os - (its valid) * 
  - some models dont come with preinstalled os.
  - consistency issue in names of os used. 
- `weight` :
  - remove the kg string. * <i><u>Issue : Accuracy </u></i>
  - convert to numeric form. * <i><u>Issue: Accuracy</u></i>
  - some values have values - 4,6,11 kg. some values have very low weight * <i><u>Issue : Accuracy</u></i>
  - some values have ? * <i><u>Issue : Validity</u></i>

### Untidy Data (Structural Problem)
---
- `scrren_resolution` : more column can be made from this column
- `cpu` : more columns can be made from this column.
- `memory`: some columns have both the values for ssd and hdd. - split into two columns.
- `gpu`: name can be extracted separately

# Step #1

Produce an estimate of the Electrical bill for the period between dates Agust 10th-September 8th.

## INPUTS

- CSV with consumed energy
- Contracted MaxPower: **4.6kW** 
- Prices:
    - Energy Peak: 0.224€/kWh
    - Energy Flat: 0.127€/kWh
    - Energy Valley: 0.084€/kWh
    - Power Peak: 31.949€/kW year
    - Power Valley: 2.701€/kW year

## OUTPUT

`~39.60€`

## Formulas

The *cost of power* is: `(PricePowerPeak + PricePowerPeak) * ContractedMaxPower * 30/365`

The *cost of consumed energy* is: `PriceEnergyX * ConsumedEnergyX` where `X` is the peak, flat or valley depending on the hour of the day:

- Peak: Mon-Fri [10.00-14.00) [included, excluded)
- Peak: Mon-Fri [18.00-22.00) 
- Flat: Mon-Fri [08.00-10.00) 
- Flat: Mon-Fri [14.00-18.00) 
- Flat: Mon-Fri [22.00-24.00) 
- Valley: Mon-Fri [00.00-08.00)
- Valley: Sat-sun (all day)

Data of consumed energy is on `ROOT/consumed_energy/infoenergia-0074895-08092021.csv`.

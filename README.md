# Persian Quantity Extraction using Regex

This GitHub repository contains a codebase for extracting quantities in the Persian language using regular expressions (regex). The code is designed to identify various types of quantities, such as length, mass, pressure, volume, temperature, area, speed, force, energy, power, torque, time, density, frequency, degree, acceleration, debi, debi-v, data-storage, and data-transfer. The extracted quantities are structured in JSON format, providing information about the type, item, amount, unit, marker, and span of each identified quantity.

## Quantities Covered
The code is capable of detecting the following types of quantities:

- Length
- Mass
- Pressure
- Volume
- Temperature
- Area
- Speed
- Force
- Energy
- Power
- Torque
- Time
- Density
- Frequency
- Degree
- Acceleration
- Debi
- Debi-v
- Data-storage
- Data-transfer

## Output Structure
The output JSON structure for each extracted quantity follows this format:

```json
{
    "type": "طول",
    "item": " پارچه",
    "amount": 3,
    "unit": "متر",
    "marker": "سه متر پارچه",
    "span": [
        0,
        12
    ]
}
```

- `type`: Describes the type of quantity (e.g., طول for length).
- `item`: Specifies the item or object associated with the quantity (e.g., پارچه for cloth).
- `amount`: Represents the numeric amount of the quantity (e.g., 3).
- `unit`: Indicates the unit of measurement for the quantity (e.g., متر for meters).
- `marker`: Provides the full phrase or marker representing the quantity (e.g., سه متر پارچه).
- `span`: Denotes the character positions within the input text where the quantity was found (start and end).

Please note that `unit`, `amount`, and `item` may be absent from the output if they are not applicable to a particular quantity.

## Supported Patterns
The code can detect various patterns in Persian text to identify quantities. Some examples of supported patterns include:

- Keyword + [Adjective]: عرض کم/سریع
- Amount + Unit + [Item]: سه متر پارچه
- Keyword + Amount: ضلع ۵
- ...

## Example Usage
Here's an example of how to use the code to extract quantities from Persian text:

```python

input = "دو کیلوگرم آرد خرید . یک ساعت صبر کرد."
quantities = MeasurementExtractor.run(input)
print(quantities)
```

Output:
```json
[
    {
        "type": "وزن",
        "item": " آرد",
        "amount": 2,
        "unit": "کیلوگرم",
        "marker": "دو کیلوگرم آرد",
        "span": [
            0,
            14
        ]
    },
    {
        "type": "زمان",
        "item": "",
        "amount": 1,
        "unit": "ساعت",
        "marker": "یک ساعت",
        "span": [
            22,
            29
        ]
    }
]
```

## Contributors

- Marzia Nouri
- [Mohammad Delkhah](https://github.com/TheGrayed)

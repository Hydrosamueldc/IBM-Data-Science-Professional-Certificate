## Dataset Overview – Automobile Data Set

This notebook uses the **Automobile Dataset** from the **UCI Machine Learning Repository**.  
It contains various specifications of automobiles along with their price and insurance risk rating.  
By working with this dataset, I explore **data acquisition, cleaning, and analysis techniques**.

---

###  Dataset Links

- **Dataset Description (UCI Repository):**  
  https://archive.ics.uci.edu/ml/datasets/automobile

- **Direct CSV/Data File:**  
  https://archive.ics.uci.edu/ml/machine-learning-databases/autos/imports-85.data

---

### Data Information

- **Data Type:** CSV (Comma Separated Values)  
- **Total Instances (Rows):** 205  
- **Total Attributes (Columns):** 26  
- **Missing Values:** Yes (represented with `'?'`)

---

### Column Descriptions — Automobile Dataset

| Column Name           | Description |
|-----------------------|-------------|
| symboling             | Insurance risk rating of the vehicle. Ranges from -3 (safe) to +3 (risky). |
| normalized-losses     | Normalized average loss payment per insured vehicle (used in insurance risk calculations). |
| make                  | Manufacturer/brand of the car (e.g., Toyota, BMW, Honda). |
| fuel-type             | Type of fuel used by the vehicle — either *gas* or *diesel*. |
| aspiration            | Method to induce air into the engine — *std (standard)* or *turbo* (turbocharged). |
| num-of-doors          | Number of doors in the car — *two* or *four*. |
| body-style            | Shape or design type of the car (sedan, hatchback, wagon, convertible, hardtop). |
| drive-wheels          | Type of drivetrain — *fwd (front-wheel drive)*, *rwd (rear-wheel drive)*, or *4wd (four-wheel drive)*. |
| engine-location       | Position of the engine within the car — *front* or *rear*. |
| wheel-base            | Distance between the front and rear axles (in inches). |
| length                | Overall length of the vehicle (in inches or mm). |
| width                 | Overall width of the vehicle. |
| height                | Overall height of the vehicle. |
| curb-weight           | Weight of the car without passengers or cargo. |
| engine-type           | Engine configuration (e.g., ohc, dohc, l, ohcv, rotor). |
| num-of-cylinders      | Number of cylinders in the engine (e.g., four, six, eight). |
| engine-size           | Engine displacement size (in cubic centimeters - cc). |
| fuel-system           | Type of fuel delivery system (e.g., mpfi, 2bbl, spdi, idi). |
| bore                  | Diameter of the engine cylinder (in inches/mm). |
| stroke                | Distance the piston moves inside the cylinder (in inches/mm). |
| compression-ratio     | Ratio of the maximum to minimum cylinder volume; affects engine efficiency and power. |
| horsepower            | Power output of the engine (in HP). |
| peak-rpm              | Engine's maximum revolutions per minute. |
| city-mpg              | Fuel efficiency in city driving — miles per gallon. |
| highway-mpg           | Fuel efficiency on highways — miles per gallon. |
| price                 | Price of the car in USD. |



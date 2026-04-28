# Aviation Accident Analysis

## Project Overview
This analysis was commissioned by an aviation insurance firm to identify aircraft makes and models that minimize financial and liability risks. The study focuses on identifying professional airplane builds that exhibit:
1. Low rates of total aircraft destruction (Hull Loss).
2. Low likelihood of fatal or serious passenger injuries (Occupant Survivability).

The dataset includes global aviation accident records from 1948 to 2023, though this study specifically filters for the modern era (last 40 years) to ensure all recommendations reflect aircraft still in active service.

## Methodology & Data Pipeline

### 1. Data Cleaning
-Recency Filter: Only accidents from 1983 onwards were analyzed to represent a 40-year active aircraft lifetime.
-Build Quality: Excluded amateur-built aircraft to focus on professional manufacturing standards.
-Vehicle Type: Restricted findings to Airplanes, excluding helicopters, gliders, and balloons.
Statistical Robustness: Results were filtered to include only models with sufficient sample sizes (N >= 10 for Large jets; N >= 50 for Small aircraft) to ensure claims are statistically significant.

### 2. Feature Engineering
-Severe Injury Rate: Created as a ratio of (Fatal + Serious Injuries) / Total Occupants.
-Destruction Indicator: A binary metric derived from the NTSB `Aircraft.damage` column.
-Size Classification: Aircraft were segmented into Small  and Large based on manufacturer and FAR operating descriptions.


## Key Insights & Findings

### Top Recommended Makes/Models
| Category | Recommended Make/Model | Safety Profile |
| Large Jet | Airbus A300 / Boeing 777| Near-zero destruction rates and high occupant survivability. |
| Regional| Embraer EMB145 / Beech 1900D | Best-in-class performance for regional turboprop/jet operations. |
| Small/GA | Cessna 180A / Piper PA-20 | Lowest severe injury fractions among light aircraft. |

### Environmental Risk Factors
The analysis identified two primary variables that override aircraft build quality in terms of risk:
- Weather: Accidents in IMC (Instrument Meteorological Conditions) result in a 3.3x higher destruction rate than those in clear weather (VMC).
- Phase of Flight: Maneuvering and Initial Climb are the deadliest phases, while Landing and Taxi incidents represent high-frequency but low-severity risks.



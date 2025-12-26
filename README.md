# Uber-Analysis-for-Newyork-city-Python-Dashboard

Uber Analysis for Newyork city Python Dashboard


Dashboard Link: 

Uber_Analysis.ipynb.


Summary 

Demand is geographically concentrated in Midtown & Lower Manhattan, extending into Upper Manhattan and Brooklyn.
Seasonality exists: Trips rise from January to June, peaking in June.
Operational heterogeneity across bases: B02764 is the largest and most variable; B02512 and B02765 are smaller and stable.
Temporal patterns:

Daily lows: 2–5 AM
Morning peak: 7–10 AM (commuters)
Evening peak: 17–21, strongest on Friday/Saturday


Weekday segmentation confirms** Friday/Saturday dominance** and midweek softness.

![Image](https://github.com/user-attachments/assets/8e5081d9-a311-4245-8956-cb921d8110d6)


Recommendations (Actionable)


Supply Positioning

Pre-position vehicles in Midtown & Lower Manhattan before 7–10 AM and 17–21 PM.
Use micro-zones and dynamic rebalancing into Brooklyn during shoulder hours to reduce idle time.



Pricing & Incentives

Introduce peak multipliers on Fri/Sat evenings and Sunday late nights.
Offer midweek discounts (Tue/Wed) to stimulate demand; add driver bonuses for late-night coverage.



Base Management

For B02764: Implement variance controls (shift rostering, minimum guaranteed hours) to reduce volatility.
For smaller bases (B02512/B02765): Scale drivers during seasonal peaks; cross-base pooling for overflow.



Forecasting & Planning

Build hourly-weekday-month demand models and base-specific capacity models (mixture distributions for large bases).
Schedule fleet maintenance in Jan–Feb to minimize service impact.



Marketing & Partnerships

Coordinate with event calendars (sports, concerts, conferences) — geo-fence pickups and tailor targeted promos in hot zones.



1) Heatmap (Spatial Hotspots)
What it shows:

![Image](https://github.com/user-attachments/assets/cba58847-d2c0-4644-a33e-d81057cf3c1c)

A geographic heatmap with intense activity centered around New York City (particularly Midtown and Lower Manhattan) and visible gradients into Upper Manhattan and parts of Brooklyn.
Key observations:

Midtown Manhattan is the hottest zone — consistent with dense commercial areas, transit hubs, and tourism.
Lower Manhattan also shows strong intensity — likely driven by financial district, commuter inflows/outflows.
Upper Manhattan and Brooklyn have meaningful but comparatively lower heat — residential + some commercial corridors.
The heat bleeds outward along major corridors, hinting at commuter flows and airport/bridge connectivity.

Implications:

Supply allocation: Prioritize driver positioning and surge management in Midtown/Lower Manhattan during peak windows.
Geo-targeted promotions: Incentivize pickups in lighter zones (Brooklyn/Upper Manhattan) to reduce deadhead miles and balance demand.
Traffic-aware pricing/ETA modeling: Expect longer ETAs in core hotspots; dynamic pricing can be tuned by micro-zones.


2) Bar Chart — Trips by Month

What it shows:
Trip counts by month from January through June.
Key observations:

![Image](https://github.com/user-attachments/assets/77aa96e9-c4e8-415f-88cf-8ad493236338)

June has the highest trips (~20K). Clear seasonality: volumes rise from winter to late spring/early summer.
January is the lowest (~14K). Gradual growth through Feb–Mar–Apr–May into June.
The stepwise increase suggests positive trend likely due to better weather, tourism, and events.

Implications:

Seasonal staffing & fleet planning: Ramp supply April–June.
Marketing timing: Launch promo campaigns pre-summer to capture rising demand.
Maintenance scheduling: Plan more maintenance in Jan–Feb (lowest demand windows).


3) Box Plot — Active Vehicles by Dispatching Base Number
What it shows:
Distribution (median, quartiles, and spread) of active vehicle counts for bases B02512, B02765, B02764, B02682, B02617, B02598.
Key observations:

![Image](https://github.com/user-attachments/assets/490f0dbc-198d-42b4-957b-8aac87eed340)

B02764 has significantly higher medians and upper ranges (up to ~4,300) — it’s the largest operation by active vehicles.
B02512 and B02765 show lower medians and tighter spreads — smaller fleets or more stable operations.
B02617/B02682/B02598 sit in the middle — moderate fleets, some variability.
Outliers indicate occasional spikes/drops, possibly event days or operational constraints.

Implications:

Scaling strategy: Best-in-class capacity is at B02764; others could emulate its scheduling & driver acquisition.
Risk management: Wider spreads at large bases could mean volatility; monitor driver availability and compliance.
SLA alignment: Assign time-sensitive trips to bases with tighter spreads (more predictable availability).


4) Violin Plot — Active Vehicles by Dispatching Base Number
What it shows:
Full distribution shapes of active vehicles per base (kernel density).
Key observations:

![Image](https://github.com/user-attachments/assets/9a20b556-18b8-4d55-bf61-ba4129d91d14)

B02764 again shows a broad, multi-modal density — active vehicles vary widely across periods (suggesting dynamic shift planning).
B02512 has a narrow, lower-density shape — small, consistent fleet.
B02617 and B02682 show moderate, peaked distributions, indicating stable mid-range operations.

Implications:

Operational design: Large bases might run multiple shifts or event-driven waves (multi-modality).
Forecasting: Base-specific models needed — e.g., use mixture models for B02764 and simpler distributions for B02512.
Resource balancing: Redirect overflow demand from volatile bases to stable ones when feasible.


5) Line Chart — Hourly Trips by Weekday
What it shows:
Trip volumes by hour (0–23) across Weekdays (Mon–Sun).
Key observations:

![Image](https://github.com/user-attachments/assets/41f6f608-07f5-4ddc-9c8e-bff199bfeecc)

Early morning lows (2–5 AM) across all days — typical quiet hours.
Morning ramp (7–10 AM) — commuter surge visible on weekdays.
Midday dip/slower growth (11–14) — moderate activity.
Evening peak (17–21) — strongest on Friday/Saturday, with Sunday showing unique late-night patterns (0–1 AM high) possibly from Saturday night spillover.
Saturday and Friday have higher evening peaks than Mon–Thu.

Implications:

Shift design: Increase fleet availability 7–10 AM and 17–21 PM, especially Fri/Sat evenings.
Pricing strategy: Consider higher dynamic pricing in evening peaks and weekend nights.
Driver incentives: Boost incentives for late-night weekend coverage and morning commuter windows.


6) Grouped Bar Chart — Trips by Month segmented by Weekday
What it shows:
Within each month (Jan–Jun), trips are segmented by weekday.
Key observations:

![Image](https://github.com/user-attachments/assets/3bdf6245-8fe8-42e0-9473-61713c463ed0)

Friday and Saturday consistently rank among top days in most months; Sunday stays strong but slightly below Saturday in some months.
January is the lowest across all weekdays — confirming seasonality.
May/June show peak counts across most weekdays — consistent with chart #2.
Tuesday/Wednesday are often lower relative to other days — typical midweek pattern.


Implications:

Weekday-specific staffing: Heaviest staffing Fri–Sat–Sun in May–June.
Promo targeting: Midweek promotions (Tue/Wed) to lift utilization; weekend promos can be focused on upsell (premium categories).
Event sync: Align operations with month-specific events (parades, sports, festivals) that inflate Fri/Sat numbers.



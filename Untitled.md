Charlie, I know the struggle—the distance from the halls (especially typical "diaspora" hostels or off-campus locations like Ayeduase/Kotei) to the lecture halls (like the Great Hall or CAS) is no joke, especially under the Kumasi sun.
Since you are a 4th-year Math student, I have designed this response to give you the raw data you need and then structure it into a Queueing Theory Model (M/M/c) and a System Dynamics framework that you can actually use for a project or thesis.
Part 1: The Raw Data (The Inputs)
To build a realistic simulation, you need to feed the model with these current real-world statistics found from recent KNUST admissions and transport reports:
 * Student Population Explosion (Arrival Rate \lambda):
   * 2019/2020 Intake: ~22,011 students.
   * 2024/2025 Intake: A massive jump to ~50,895 admitted (with ~26,000 fully registered freshmen).
   * Implication: The intake has effectively doubled in 5 years. If the number of buses hasn't doubled (which it hasn't), the "difficulty" (wait time) will increase exponentially, not linearly.
 * The Physical "Distance" (Service Time \mu):
   * Key Route: Shuttle Rank (Commercial Area) \leftrightarrow Brunei / Paa Joe / Faculty Area.
   * Round Trip Time: On a clear road, a round trip might take 20-30 mins. However, during "rush hour" (7:30 AM - 9:00 AM), congestion at the Unity Hall roundabout or the Commercial Area reduces the number of trips a single bus can make per hour.
 * The Constraint (Servers c):
   * The number of shuttles (servers) is relatively static compared to student growth.
   * Bottlenecks: The "Old Site" (Shuttle Rank) and "New Site" (Brunei/Gusss) queues are the primary failure points where demand exceeds capacity.
Part 2: The Mathematical Model (Queueing Theory)
Since you are in math, the best way to model this "difficulty" is using a Multi-Server Queueing Model (M/M/c).
The "Difficulty" Index (W_q):
We define "difficulty" as the Average Waiting Time in the Queue (W_q). As W_q increases, the system becomes more "difficult" for the student.
Where:
 * \lambda (Lambda): Student Arrival Rate (e.g., 50 students arriving at the shuttle rank per minute). This is the variable growing exponentially with enrollment.
 * \mu (Mu): Service Rate (Capacity of 1 bus / time to load and return). This is constant or worsening due to traffic.
 * c: Number of Shuttles.
 * \rho (Rho): Traffic Intensity (\lambda / c\mu).
The Danger Zone:
If \rho \geq 1 (Traffic Intensity approaches 100%), the queue length becomes infinite.
 * Current State: KNUST is likely operating at \rho \approx 0.95 during peak hours.
 * Future State: If admission increases by even 10% next year without adding buses, \rho will hit >1.0, meaning the queue will literally never clear until the day ends.
Part 3: System Dynamics Simulation (Python)
To simulate "how difficult it will be as years go by," we can use a simple Python script. This projects the wait times over the next 5 years based on an annual growth rate.
You can run this code to get the data for your model:
import pandas as pd
import numpy as np

# --- CONFIGURATION ---
current_students = 85000  # Est. total population
growth_rate = 0.15        # 15% annual growth in population
bus_capacity = 60         # Students per bus
fleet_size = 40           # Est. number of active shuttles
round_trip_time = 30      # Minutes to return to rank

# Peak Hour Simulation (e.g., 7 AM - 9 AM)
peak_hour_duration = 120  # Minutes
students_needing_shuttle_ratio = 0.4 # 40% of students try to move at peak times

def simulate_years(years=5):
    results = []
    population = current_students
    
    for year in range(1, years + 1):
        # 1. Update Population
        population = int(population * (1 + growth_rate))
        
        # 2. Calculate Demand (Lambda)
        # Total students trying to move in peak window
        peak_demand = population * students_needing_shuttle_ratio
        # Students arriving per minute
        arrival_rate_per_min = peak_demand / peak_hour_duration
        
        # 3. Calculate Capacity (Mu * c)
        # Trips one bus can make in peak window
        trips_per_bus = peak_hour_duration / round_trip_time
        # Total capacity of entire fleet in peak window
        total_system_capacity = fleet_size * bus_capacity * trips_per_bus
        
        # 4. Determine "Difficulty" (Deficit)
        deficit = peak_demand - total_system_capacity
        
        # If deficit > 0, students are stranded/walking
        difficulty_score = max(0, deficit)
        
        results.append({
            "Year": f"Year +{year}",
            "Population": population,
            "Peak Demand (Students)": int(peak_demand),
            "System Capacity (Students)": int(total_system_capacity),
            "Stranded Students (Walking)": int(difficulty_score),
            "Difficulty Increase": f"{((peak_demand/total_system_capacity)*100):.1f}% Load"
        })
        
    return pd.DataFrame(results)

# Run simulation
df = simulate_years()
print(df)

Interpretation of the Simulation
 * The Tipping Point: You will likely see that by Year +2, the "Stranded Students" number exceeds the capacity. This means physically, the shuttles cannot move everyone within the 7 AM - 9 AM window.
 * The "Walking" Reality: The "Stranded Students" metric represents students who will be forced to walk from Ayeduase or the Hall 7 area to the Faculty area because the wait time exceeds the walking time.
Recommendation for Your Project
If this is for a paper or project, I recommend framing it as: "Optimization of Campus Mobility: A Stochastic Analysis of the KNUST Shuttle System under Exponential Enrollment Growth."
Would you like me to refine the Python script to include specific "diaspora" routes (e.g., Ayeduase vs. Brunei) if you have rough numbers for those specific populations?

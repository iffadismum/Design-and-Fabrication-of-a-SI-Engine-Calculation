# Design-and-Fabrication-of-a-SI-Engine-Calculation
import math

# Constants and Input Data
bore_diameter = 4.3  # Bore diameter (cm)
stroke_length = 5.35  # Stroke length (cm)
thickness_gasket = 0.2  # Thickness of engine head gasket (cc)
upper_side_length = 0.2  # Length left on upper side of piston (cm)
fuel_consumption_volume = 3  # Fuel consumed in ml
time_duration = 3 + (14 / 1000)  # Time duration in minutes (3 minutes 14 milliseconds)
fuel_density = 0.703  # Density of Octane 93 at 25°C in g/ml
engine_speed_rpm = 2000  # Engine speed in RPM (average)

# Calculations

# Step 1: Displacement Volume Calculation
displacement_volume = (math.pi * (bore_diameter / 2) ** 2 * stroke_length)  # in cubic centimeters (cc)
print(f"Displacement Volume (cc): {displacement_volume:.2f}")

# Step 2: Volume left on the upper side of piston
upper_side_volume = math.pi * (bore_diameter / 2) ** 2 * upper_side_length  # in cubic centimeters (cc)
print(f"Volume Left on Upper Side of Piston (cc): {upper_side_volume:.2f}")

# Step 3: Clearance Volume Calculation
void_volume = 2.638  # Intersected void volume calculated using SolidWorks (cc)
clearance_volume = void_volume + thickness_gasket + upper_side_volume
print(f"Clearance Volume (cc): {clearance_volume:.2f}")

# Step 4: Total Volume Calculation
total_volume = displacement_volume + clearance_volume
print(f"Total Volume (cc): {total_volume:.2f}")

# Step 5: Compression Ratio Calculation
compression_ratio = total_volume / clearance_volume
print(f"Compression Ratio: {compression_ratio:.2f}:1")

# Step 6: Fuel Consumption Rate
fuel_consumption_rate = fuel_consumption_volume / time_duration  # ml per minute
print(f"Fuel Consumption Rate (ml/min): {fuel_consumption_rate:.3f}")

# Step 7: Mass Flow Rate Calculation
mass_flow_rate = fuel_consumption_rate * fuel_density  # g per minute
print(f"Mass Flow Rate (g/min): {mass_flow_rate:.3f}")

# Step 8: Engine Speed in RPM
print(f"Engine Speed (RPM): {engine_speed_rpm}")

# Output summary
print("\nEngine Design and Performance Summary:")
print(f"Displacement Volume: {displacement_volume:.2f} cc")
print(f"Clearance Volume: {clearance_volume:.2f} cc")
print(f"Total Volume: {total_volume:.2f} cc")
print(f"Compression Ratio: {compression_ratio:.2f}:1")
print(f"Fuel Consumption Rate: {fuel_consumption_rate:.3f} ml/min")
print(f"Mass Flow Rate: {mass_flow_rate:.3f} g/min")
print(f"Engine Speed: {engine_speed_rpm} RPM")

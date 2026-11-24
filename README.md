# Experiment 4 : Yearly Revenue Growth Visualization Using Matplotlib

## Aim

To visualize the yearly trend of company revenue and expenses from 2017 to 2023 using Matplotlib by plotting multi-line charts with customized markers, labels, legends, gridlines, and point annotations.

## Algorithm

1. **Start** the program.
2. **Import Libraries**: Import `matplotlib.pyplot` as `plt` for plotting and `numpy` as `np` for numeric array generation and index lookup.
3. **Initialize Dataset**:
   * Generate an array `years` spanning `2017` to `2023` using `np.arange(2017, 2024)`.
   * Define lists `revenue` and `expenses` representing annual amounts in Lakhs.
4. **Configure Figure & Plot Lines**:
   * Initialize a figure canvas of size $8 \times 5$ inches using `plt.figure(figsize=(8, 5))`.
   * Plot `revenue` against `years` as a solid green line with circular markers (`marker='o'`).
   * Plot `expenses` against `years` as a dashed red line (`linestyle='--'`) with square markers (`marker='s'`).
5. **Format Chart Aesthetics**:
   * Add a bold chart title (`plt.title()`) and axis labels (`plt.xlabel()`, `plt.ylabel()`).
   * Enable dashed semi-transparent gridlines (`plt.grid()`) and place the legend in the upper-left corner (`plt.legend(loc='upper left')`).
6. **Annotate Peak Values**:
   * Find the indices of maximum revenue and maximum expenses using `np.argmax()`.
   * Highlight both peak data points on the chart with directional arrows and text callouts using `plt.annotate()`.
7. **Adjust Layout & Display**:
   * Prevent label clipping via `plt.tight_layout()` and render the final plot with `plt.show()`.
8. **Stop** the program.

## Functions and Methods Used

| Category | Function / Method | Purpose / Description |
| :--- | :--- | :--- |
| **Numerical Operations** | `np.arange()` | Generates evenly spaced integer years (`2017` through `2023`) |
| | `np.argmax()` | Returns the array index of the maximum revenue and expense values |
| **Line Plotting** | `plt.figure()` | Initializes a new figure window with custom dimensions |
| | `plt.plot()` | Draws line plots with customized markers, colors, line styles, and widths |
| **Chart Formatting** | `plt.title()`, `plt.xlabel()`, `plt.ylabel()` | Adds descriptive title and axis labels with custom font sizes |
| | `plt.grid()`, `plt.legend()` | Adds background gridlines and displays series labels in the upper left |
| **Annotations & Display** | `plt.annotate()` | Places text labels with arrows pointing to peak revenue and expense points |
| | `plt.tight_layout()`, `plt.show()` | Optimizes spacing to avoid overlapping elements and renders the figure |

## Program / Code  

# Company Revenue and Expense Visualization using Matplotlib  

import matplotlib.pyplot as plt  
import numpy as np  

# Step 1: Create dataset  
years = np.arange(2017, 2024)  

revenue = [120, 150, 180, 210, 250, 290, 340]  
expenses = [80, 100, 120, 140, 160, 190, 220]  

print("Years:", years)  
print("Revenue:", revenue)  
print("Expenses:", expenses)  

# Step 2: Plot Revenue and Expenses  
plt.figure(figsize=(8, 5))  

plt.plot(years, revenue, color='green',  
         marker='o', linewidth=2, label='Revenue')  

plt.plot(years, expenses, color='red',  
         linestyle='--', marker='s',  
         linewidth=2, label='Expenses')  

# Step 3: Add title, labels and grid  
plt.title("Company Revenue and Expense Analysis",  
          fontsize=14, fontweight='bold')  

plt.xlabel("Year")  
plt.ylabel("Amount (Lakhs)")  

plt.grid(True, linestyle='--', alpha=0.5)  

# Step 4: Add legend  
plt.legend(loc='upper left')  

# Step 5: Find and annotate highest revenue and expense  
max_revenue_index = np.argmax(revenue)  
max_expense_index = np.argmax(expenses)  

plt.annotate(  
    "Highest Revenue",  
    xy=(years[max_revenue_index], revenue[max_revenue_index]),  
    xytext=(2019, 320),  
    arrowprops=dict(arrowstyle='->', color='green')  
)  

plt.annotate(  
    "Highest Expense",  
    xy=(years[max_expense_index], expenses[max_expense_index]),  
    xytext=(2019, 240),  
    arrowprops=dict(arrowstyle='->', color='red')  
)  

# Step 6: Adjust layout and display plot  
plt.tight_layout()  
plt.show()  

## Output
Years: [2017 2018 2019 2020 2021 2022 2023]

Revenue: [120, 150, 180, 210, 250, 290, 340]

Expenses: [80, 100, 120, 140, 160, 190, 220]

Highest Revenue: 340 Lakhs (2023)

Highest Expense: 220 Lakhs (2023)

Graph displayed successfully.
<img width="1031" height="742" alt="image" src="https://github.com/user-attachments/assets/ff5030a3-f733-47a7-83e4-20a2f162b7ee" />



## Result

The program successfully creates datasets for yearly company revenue and expenses and renders an annotated multi-line comparison chart using Matplotlib.

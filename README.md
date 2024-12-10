# HW-#1: Global Temperature Dashboard: Linking Charts and Adding Interactivity

The goal of this extra credit assignment is to give you practice building linked visualizations using D3.js. By completing this assignment, you will learn how to:

- Visualize aggregated data with a Bar Chart.
- Create a time-series visualization using a Line Chart.
- Dynamically link multiple visualizations for interactivity.
- Implement tooltips and animations to enhance usability.

Below is an example of what your finished dashboard will look like:

## Overview
The starter code for this assignment includes a basic HTML structure with two empty panels:

- A left panel, where you will implement a Bar Chart visualization to show the average temperature of major cities for a specific year.
- A right panel, where you will implement a Line Chart visualization to display the temperature trend over time for the selected city from the Bar Chart.

Your task is to preprocess the dataset, create these visualizations, and implement dynamic linking between the two panels. The starter code provides the framework, but you will need to build both visualizations and add the required interactivity.

## Data Description

We will use the **Global Land Temperatures by Major City** dataset, which contains the following relevant columns:

- `City`: The name of the city.
- `Country`: The country of the city.
- `AverageTemperature`: The monthly average temperature (in °C).
- `dt`: The date (YYYY-MM-DD) when the temperature was recorded.

You will preprocess the dataset to:

- Group data by city and year for the Bar Chart.
- Extract time-series data for the Line Chart.

In the completed version of this assignment, the left panel will display a Bar Chart showing the average temperatures of major cities for a selected year. The right panel will feature a Line Chart that displays the temperature trend over time for the selected city from the Bar Chart. The two visualizations will be dynamically linked: clicking a bar in the Bar Chart updates the Line Chart with relevant data. Tooltips will provide additional details for both visualizations, and smooth transitions will enhance the interactivity. The dashboard will allow users to explore and compare insights across various cities seamlessly.

## To complete the assignment

- Clone this code template to your local machine.
- Start a local server and open the `index.html` page.
- Modify the given code according to the instructions below to achieve the requested interface.
- Commit and push the code back to this repository to submit it.

## Step 0: Starting code

When you first run the page, you should see a blank dashboard with two panels. Add your name and email to the top, and then create a Javascript file to contain all your JS/D3 logic. You should name the file using your ASURITE. For example, Dr. Bryan's JS file would be named `cbryan16.js`. Link to this file in your index.html.

## Step 1: Displaying a Bar Chart

When the page first loads, the left panel should be empty. After the dataset is loaded, you should display a Bar Chart in the left panel showing the average temperatures of major cities for a selected year. Each bar will represent the temperature of a city.

- First, preprocess the dataset to organize it for the Bar Chart:
  - Group by year and city.
  - Calculate the average temperature for each city in the selected year.
- Use the `d3.scaleBand()` and `d3.scaleLinear()` functions to create the Bar Chart:
  - The X-axis should represent cities.
  - The Y-axis should represent average temperatures.
- Assign colors to bars based on the temperature range using a sequential D3 color scale (e.g., `d3.interpolateCool`).
- Add tooltips that display the following information for each bar:
  - City name.
  - Average temperature.
- Add interactivity:
  - When the user clicks on a bar, filter the data and update the Line Chart in the right panel with relevant time-series data.
- Style the Bar Chart:
  - Add a 1-pixel black border (`stroke-width=1`) to each bar.
  - Add small spacing between bars for better visual clarity.

## Step 2: Displaying a Line Chart

When the page first loads, the right panel should be empty. After the user clicks on a bar in the Bar Chart, a Line Chart should appear in the right panel, displaying the temperature trend over time for the selected city.

- First, preprocess the dataset to extract time-series data:
  - Convert the `dt` column into a JavaScript `Date` object.
  - Filter data for the selected city.
  - Structure the data as an array of objects in the format: `{ date: Date, temperature: Number }`.
- Use the `d3.line()` function to create the Line Chart:
  - The X-axis should represent time (e.g., years).
  - The Y-axis should represent average temperature.
- Style the chart:
  - Use a responsive SVG that fits within the `#linechart_div` container.
  - Add axis labels for time (X-axis) and temperature (Y-axis).
  - Use a smooth line path with rounded corners.
- Add tooltips to display:
  - The exact date and temperature for a hovered data point.
  - Use a `div` element that follows the mouse cursor and disappears when the mouse moves away.
- Add interactivity:
  - Dynamically update the Line Chart when a bar in the Bar Chart is clicked:
    - Clear the current chart.
    - Filter the dataset to show time-series data for the selected city.
    - Redraw the chart with a smooth transition for the line.
  - Update the chart's title dynamically to reflect the selected city (e.g., "Temperature Trend for Paris").

## Step 3: Add animation to the two charts

- Add smooth transitions for:
  - Bar height changes in the Bar Chart when new data is loaded.
  - Line Chart updates when switching between selections.
- Use easing functions (e.g., `d3.easeCubic`) to enhance visual appeal.

## Step 4: Finalize the dashboard

- Add a title above each visualization panel:
  - "Average Temperatures for Cities" for the Bar Chart.
  - "Temperature Trend Over Time" for the Line Chart.
- Test all interactions:
  - Verify that clicking a bar in the Bar Chart updates the Line Chart.
  - Ensure tooltips and animations work smoothly.

## Extra Credit

You can receive up to four extra credit points for this assignment. Each bullet point is worth up to two points (depending on quality of implementation).

- **Linked Highlighting**:
  - **Bar Chart to Line Chart**:
    - When the user hovers over a bar in the Bar Chart, highlight the corresponding points in the Line Chart that relate to the selected city.
  - **Line Chart to Bar Chart**:
    - When the user hovers over a point in the Line Chart, highlight the corresponding bar in the Bar Chart.
- **Drill-Down in Bar Chart**:
  - Enable filtering by year using a dropdown or slider.

## Grading

This assignment is worth 10 points. 

- Step 0 is worth 1 point.
- Step 1 is worth 3 points.
- Step 2 is worth 3 points.
- Step 3 is worth 3 points.
- The Extra Credit is worth up to 4 bonus points.

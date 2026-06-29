# Ride-Hailing Excel Dashboard

In this project, I aim to analyze ride-hailing booking data to help operations and business teams understand why rides fail to complete, where demand is concentrated, and how revenue and cancellations behave throughout the day. The dashboard is built entirely in Excel on a single sheet, using a Freeze Pane layout, KPI cards, and Pivot Charts.

## Dataset description

This dataset contains 15,000 rows and 21 original columns. The data was relatively clean, so the focus was on structuring it for analysis rather than heavy cleaning.

## Original Columns:

1-Date: The date the booking was made.

2-Time: The time the booking was made.

3-Booking ID: Unique identifier for each ride booking.

4-Booking Status: The final status of the booking (Completed, Cancelled by Customer, Cancelled by Driver, No Driver Found, Incomplete).

5-Customer ID: Unique identifier for each customer.

6-Vehicle Type: The type of vehicle booked (Auto, Go Mini, Go Sedan, Bike, Premier Sedan, eBike, Van).

7-Pickup Location: The location where the ride was requested.

8-Drop Location: The destination of the ride.

9-Avg VTAT: Average Vehicle Turnaround Time, the time taken for the driver to reach the pickup point.

10-Avg CTAT: Average Customer Turnaround Time, the time taken to complete the ride after pickup.

11-Cancelled Rides by Customer: Flag indicating whether the customer cancelled the ride.

12-Reason for cancelling by Customer: The reason given by the customer for cancelling.

13-Cancelled Rides by Driver: Flag indicating whether the driver cancelled the ride.

14-Driver Cancellation Reason: The reason given by the driver for cancelling.

15-Incomplete Rides: Flag indicating whether the ride was not completed.

16-Incomplete Rides Reason: The reason the ride was left incomplete.

17-Booking Value: The revenue generated from the ride.

18-Ride Distance: The distance covered during the ride.

19-Driver Ratings: The rating given to the driver.

20-Customer Rating: The rating given to the customer.

21-Payment Method: The method used to pay for the ride (UPI, Cash, Credit Card, Debit Card, Wallet).

## Dashboard Design

The dashboard is built on a single sheet using a Freeze Pane layout, so the KPI cards stay visible while the charts and tables are explored. It is organized into three sections:

1-Overview: Total Revenue, No Driver Found rate, Cancellation Rate, Non-completion rate, and Completion Rate, shown as KPI cards at the top of every section.

2-Ride Activity and Locations: Ride volume and cancellations throughout the day, alongside the top 10 pickup locations with an hour filter.

3-Vehicle and Cancellation Breakdown: Vehicle distribution, and cancellation reasons by vehicle for both customers and drivers.

4-Payment and Status Distribution: Payment method split, final ride status breakdown, and customer cancellation reasons.

## Data Preparation Steps

### Overview:

The following steps outline how the data was structured to support the Pivot Charts and Pivot Tables used across the dashboard.

#### Steps:

1-Built Pivot Tables directly on the raw data for straightforward aggregations, such as Vehicle Distribution, Payment Methods Distribution, and Ride Final Status.

2-Built helper Pivot Tables behind the scenes for the more layered visuals, such as Ride Activity Throughout the Day (grouping bookings, customer cancellations, and driver cancellations by hour) and the cancellation reason breakdowns by vehicle type.

3-Used a Pivot Table with a slicer to power the Top 10 Pickup Locations chart, filtered by hour.

4-Calculated the KPI card values (No Driver Found rate, Cancellation Rate, Non-completion rate, Completion Rate) from the Booking Status counts as a share of total bookings.

5-Sorted the Vehicle Distribution chart from highest to lowest by right-clicking a value inside the Pivot Table and choosing Sort Largest to Smallest, since sorting the underlying source range directly has no effect on a chart that is linked to a Pivot Table rather than a regular range.

## Data Visualization and Analysis

### KPI Cards:

Total Revenue, No Driver Found rate, Cancellation Rate, Non-completion rate, and Completion Rate are displayed as KPI cards at the top of the dashboard, giving an at-a-glance read on overall performance before drilling into any section.

### Charts:

Ride Activity Throughout the Day:
Description: This line chart tracks the count of bookings, customer cancellations, and driver cancellations across each hour of the day, highlighting the morning and evening demand peaks.
<br>
[![image alt](https://github.com/Muustafa11/Ride-Hailing-Excel-Dashboard/blob/main/Ride%20Activity%20Throughout%20the%20Day.png?raw=true)](https://github.com/Muustafa11/Ride-Hailing-Excel-Dashboard/blob/main/Ride%20Activity%20Throughout%20the%20Day.png)

<br>
<br>
Top 10 Pickup Locations:
Description: This bar chart ranks the busiest pickup locations and includes an hour slicer, allowing the same chart to be filtered down to any specific hour.

Vehicle Distribution:
Description: This bar chart shows the booking count for each vehicle type, with Auto and Go Mini leading demand.

Customer Cancellation Reasons by Vehicle:
Description: This bar chart breaks down customer cancellation reasons (AC not working, change of plans, driver asked to cancel, driver not moving towards pickup, wrong address) across each vehicle type.

Drivers Cancellation Reason by Vehicle:
Description: This bar chart breaks down driver cancellation reasons (customer related issue, more than permitted people, personal and car related issues, customer coughing or sick) across each vehicle type.

Payment Methods Distribution:
Description: This pie chart shows the split of payment methods used, with UPI as the dominant method.

Ride Final Status:
Description: This pie chart shows the share of rides that were completed versus cancelled by customer, cancelled by driver, incomplete, or had no driver found.

Customer Cancellation Reason:
Description: This pie chart shows the share of each cancellation reason given by customers across all cancelled rides.

# Conclusion

In this project, I structured and analyzed 15,000 ride-hailing bookings to understand the drivers behind cancellations, incomplete rides, and revenue performance. The dashboard shows that only 62% of bookings are completed, with cancellations and no-driver-found situations accounting for a meaningful share of lost rides, mostly concentrated around wrong addresses, changed plans, and drivers not reaching the pickup point. The hourly ride activity and pickup location breakdowns highlight where and when demand is highest, while the vehicle-level cancellation analysis points to where operational fixes would have the biggest impact. Together, these insights can help ride-hailing operations teams prioritize driver allocation and address the most common cancellation triggers.

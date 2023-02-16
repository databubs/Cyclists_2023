# Cyclists_2023
Loaded ALL 12 CSV files into R (Last 12 months)
Merged them all in R and got merged_data now the analyzing part is fun for visulizations

# Coding Part

library(ggplot2)

clean_data <- merged_data[!is.na(merged_data$ride_length), ]

quickest_ride <- min(clean_data$ride_length)
slowest_ride <- max(clean_data$ride_length)

# Create a data frame to store the ride length and label information
ride_lengths <- data.frame(length = c(quickest_ride, slowest_ride),
                           label = c("Quickest Ride", "Slowest Ride"))

# Create a pie chart
ggplot(ride_lengths, aes(x = "", y = length, fill = label)) +
  geom_bar(stat = "identity", width = 1) +
  coord_polar("y", start=0) +
  theme_void() +
  labs(title = "Quickest and Slowest Ride Lengths")
  
 

library(tidyverse)
library(plotly)
library(palmerpenguins)

penguin_graph <- ggplot(data = penguins, aes(x = bill_length_mm, y = bill_depth_mm)) +
  geom_point(aes(size = body_mass_g, 
                 color = species),
             alpha = 0.4) +
  scale_color_manual(values = c("purple","orange","black")) +
  theme_minimal() +
  labs(x = "bill length (mm)",
       y = "bill depth mm",
       title = "Penguin measurements")
penguin_graph
ggplotly(penguin_graph, tooltip = c("species"))


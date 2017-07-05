# Unit-4-Exercise-1
## ggplot2 work with the titanic dataset through DataCamp

### Read the csv file into R and assign to "titanic"
titanic <- read.csv(file = "titanic.csv")

### Load ggplot2 into the workspace
library(ggplot2)

### 1 - Check the structure of titanic
str(titanic)

### 2 - Plot the distribution of sexes within the classes of the ship
ggplot(titanic, aes(x = Pclass, fill = Sex)) + 
  geom_bar(position = "dodge")

### 3 - Plot 2, add facet_grid() layer
ggplot(titanic, aes(x = Pclass, fill = Sex)) + 
  geom_bar(position = "dodge") +
  facet_grid(. ~ Survived)

### 4 - Define an object for position jitterdodge to use below
posn.jd <- position_jitterdodge(0.5, 0, 0.6)

### 5 - Use the plot from 3, but add the posn.jd as the position
ggplot(titanic, aes(x = Pclass, y = Age, color = Sex)) + 
  geom_point(size = 3, alpha = 0.5, position = posn.jd) +
  facet_grid(. ~ Survived)

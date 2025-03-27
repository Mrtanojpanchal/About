Practical 3: Perform the data classification using classification algorithm using R/Python.

Code: rainfall <-
c(799,1174.8,865.1,1334.6,635.4,918.5,685.5,998.6,784.2,985,882.8,1071) 
# Convert it to a time series object. rainfall.timeseries <-
ts(rainfall,start = c(2012,1),frequency = 12) 
print(rainfall.timeseries) png(file = "rainfall.png") 
plot(rainfall.timeseries) dev.off() 




Practical 4: Perform the data clustering using clustering algorithm using R/Python.
Code: 
newiris <- iris 
newiris$Species <- NULL (kc <- kmeans(newiris,3)) 
table(iris$Species,kc$cluster) 
plot(newiris[c("Sepal.Length","Sepal.Width")],col=kc$cluster
) 




Practical 5: Perform the Linear regression on the given data warehouse data using R/Python. 
Code: 

A. Create Relationship Model and get the Coefficients :
Code: 
x <-
c(151,174,138,186,128,136,179,163,152,131) y 
<- c(63,81,56,91,47,57,76,72,62,48) relation <-
lm(y~x) print(summary(relation)) 

B. Predict the weight of new persons :
Code:
x <- c(151,174,138,186,128,136,179,163,152,131)
 <- c(63,81,56,91,47,57,76,72,62,48)
relation <-lm(y~x)
a <- data.frame(x=170)
result <- predict(relation,a)
print(result)
print(relation)



C. Visualize the Regression Graphically :
x <- c(151, 174, 138, 186, 128, 136, 179, 163, 152, 131) # Height in cm y 
<- c(63, 81, 56, 91, 47, 57, 76, 72, 62, 48) 
png(file = "linearregression.png") 
plot(x, y, 
 col = "blue", 
 main = "Height & Weight Regression", 
 xlab = "Height in cm", 
ylab = "Weight in Kg", 
 pch = 16, 
 cex = 1.3) 
abline(lm(y ~ x), col = "red") 
dev.off() 



Practical 6: Perform the logistic regression on the given data warehouse data using 
R/Python.
Code:
ir_data <- iris 
str(ir_data) 
levels(ir_data$Species) 
sum(is.na(ir_data)) 
ir_data <- ir_data[1:100,] 
<- sample(1:100, 80)
# Create training (test) and control datasets ir_test 

<- ir_data[samp,] 

ir_ctrl <- ir_data[-samp,] 

# Install and load ggplot2 package

install.packages("ggplot2") library(ggplot2) 

# Install and load GGally package

install.packages("GGally") library(GGally) 

# Create pair plot of test dataset ggpairs(ir_test) 

# Define dependent and independent variables

y <- ir_test$Species

x <- ir_test$Sepal.Length 

# Fit logistic regression model

glfit <- glm(y ~ x, family = 'binomial') 

# Display model summary summary(glfit) 

# Create new data frame for prediction

newdata <- data.frame(x = ir_ctrl$Sepal.Length) 
predicted_val <- predict(glfit, newdata, type = "response") 
prediction <- data.frame(ir_ctrl$Sepal.Length, ir_ctrl$Species, predicted_val)
qplot(prediction[,1], round(prediction[,3]), col = prediction[,2], 
xlab = 'Sepal Length', ylab = 'Prediction using Logistic Regression')





Practical 8A: Perform data visualization Perform data visualization using Python on any 

sales data
Code:
import pandas as pd 
from matplotlib import pyplot as plt plt.rcParams["figure.figsize"] 
= [8.00, 4.50] plt.rcParams["figure.autolayout"] = True columns = 
["Item_name", "Qty_sold"] 
df = pd.read_csv(r'C:\Users\LENOVO\OneDrive\Desktop\Sales.csv', 
usecols=columns) print("Contents in csv file:", df)
plt.plot(df.Item_name, df.Qty_sold) plt.show()

# 📝 Programming Assignment 4: Data Wrangling and Visualization 
> [!NOTE]
> #### This GitHub repository contains two engaging problems designed to enhance your skills in Python Data Wrangling and Visualization. Each problem focuses on real-world scenarios, encouraging users to apply their knowledge in analyzing and presenting different data frames and creating stunning visuals for these data frames using practical library such as ```matplotlib.pyplot```. 

## 📚 About Data Wrangling and Visualization 
Data Wrangling, also known as data munging, is the process of transforming and preparing raw data into a format that is suitable for analysis. This involves cleaning, filtering, transforming, and aggregating data to make it more organized and structured. On the other hand, Data Visualization is the process of creating graphical representations of data to better understand and communicate insights and patterns. Effective data visualization helps in identifying trends, outliers, and correlations, making it easier to draw meaningful conclusions from the data.
### ✨ Why Matplotlib? 
> ###### 🔹 Popular library for creating static and interactive visualizations.

> [!IMPORTANT]
> For this code, it is necessary to have the following file saved on the default user folder. Otherwise, the code won't have a file to read resulting in an expected error.
> 
> [board2.xlsx](https://github.com/user-attachments/files/17029022/board2.xlsx)



## 📑 Description of the Given Problems
### 1️⃣ ECE Board Exam Problem
Using data wrangling and data visualization technique with storytelling, analyze the data and present different (i) data frames; and (ii) visuals using the dataset given.
> [!TIP]
> ##### 🎯 **Write a code that can load a file then print it.**
> ###### ✅ *Load the corresponding ```.xlsx``` file into a data frame named ```boards``` using ```pandas.```*

#### 💻 *Code:*
###### *Below shows the code that loads and prints the ```.xlsx``` file into a data structure:*
```Ruby
# Used to access pandas library
import pandas as pd

# Assigns function as boards and it loads the file. It then prints the data structure
boards = pd.read_excel("board2.xlsx")
boards
```
###### *The code should display the following output:*
![image](https://github.com/user-attachments/assets/91a4d068-b076-41cd-8b97-bae6f117944d)

```Ruby
# Filter boards dataframe to select Instrumentation students from Luzon with Electronics score > 70
Instru = boards.loc[(boards['Hometown'] == 'Luzon') & (boards['Track'] == 'Instrumentation') & (boards['Electronics'] > 70), ['Name','GEAS','Electronics']]
Instr
```
###### *The code should display the following output:*
![image](https://github.com/user-attachments/assets/c2b030c7-7d60-4bc0-9822-f9e9e8499ff5)

```Ruby
# Calculates average score for each student, rounded to 2 decimal places
boards['Average'] = round(boards[['Math', 'Electronics', 'GEAS', 'Communication']].mean(axis=1),2)

# Filter boards dataframe to select female students from Mindanao with average score >= 55
Mindy = boards.loc[(boards['Hometown'] == 'Mindanao') & (boards['Gender'] == 'Female') & (boards['Average'] >= 55), ['Name','Track','Electronics', 'Average']]
Mindy
```
###### *The code should display the following output:*
![image](https://github.com/user-attachments/assets/0e7d171f-7e47-4325-b63b-23e7b7023ebb)

### 2️⃣ ECE Board Exam: Data Visualization
Create a visualization that shows how the different features contributes to average grade. Does chosen track in college, gender, or hometown contributes to a higher average score.

#### 💻 *Code:*
###### *Below shows the code for Data Visualization:*
```Ruby
# Used to access matplotlib.pyplot library
import matplotlib.pyplot as plt

# Creates bar chart to visualize the average score by Hometown
plt.figure(figsize=(10,4))
plt.bar(boards['Hometown'],boards['Average'])
```
###### *The code should display the following output:*
![image](https://github.com/user-attachments/assets/94ae1bd1-f8ef-407e-99fd-5d5d31c6b2c6)
###### *The bar graph shows that Luzon yields the highest number of students with the highest average score, followed by Visayas, with Mindanao yielding the lowest.*

```Ruby
# Creates bar chart to visualize the average score by Track
plt.figure(figsize=(10,4))
plt.bar(boards['Track'],boards['Average'])
```
###### *The code should display the following output:*
![image](https://github.com/user-attachments/assets/b15e2f69-e81e-4702-a611-6d49eee697d8)
###### *The bar graph displays an increasing order with instrumentation benig the lowest, followed by Communication, with Microelectronics as the highest.*

```Ruby
# Creates bar chart to visualize the average score by Gender
plt.figure(figsize=(10,4))
plt.bar(boards['Gender'],boards['Average'])
```
###### *The code should display the following output:*
![image](https://github.com/user-attachments/assets/b24bd02e-5d20-4f1f-9496-bc9e401082bb)
###### *The bar graphs reveals that females performed better on the ECE Board Exam than the males.*


## 🔐 Closing Remarks
Thank you for exploring this GitHub repository dedicated to Python Data Wrangling and Visualization. I hope that this may serve as a supplementary learning material for anyone interested in learning Python. Feel free to experiment with this code!

## 👨‍💻 Author
#### *Zildjan Zatyr C. Ponce | 2ECE - A* 
#### *University of Santo Tomas*
#### *September 17, 2024*

## 🔑 Version History
- 1.01
  - REAADME file was completed
  - ```.ipnyb``` file was added
- 1.00
  - This repository was established
  - README.md was created

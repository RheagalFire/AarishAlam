# Car Price Prediction

![img](https://i.ytimg.com/vi/ThfWXIjVe2s/maxresdefault.jpg)

**Skills Required**

- Python
  - Numpy
  - Pandas
  - Matplotlib
  - Sklearn 
  - Seaborn
  

- ML Algorithms
   - Linear Regression 
   - SVM
   - Random Forest 
   - XgBoost
   - Decision Tree
 
## How to handle the Data?

 Initially a lot of data cleaning will be required since the data contains a lot of null value . This step is pretty much important since the accuracy of our prediction may depend significantly upon how we handle the missing data . Therefore statistical approach towards data cleaning and removing outliers is suggested.

Some of the important operations that i have done in the [notebook](https://github.com/RheagalFire/Car-Price-Prediction-using-different-algo/blob/master/Car-Prediction/Car-Prediction.ipynb) is given below .

1. **Typecasting** 
  - objects need to be first typecasted to strings to further typecast them to integers`.astype(str).astype(int)`
  - strings can be directly typecasted to integers.

	Refer to the official documentation for typecasting in python [here](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.astype.html).

2. **Finding Outliers**
	
	Outliers are the anomalies present in the data that unnecesarily increases the rate of error.
	To improve efficiency of our model, we should not train it on these type of data's.
	
	- Boxplot Method Of removing Data
		![](https://www.simplypsychology.org/boxplot.jpg?ezimgfmt=rs:382x196/rscb24/ng:webp/ngcb24)

        Values gretar than 1.5 IQR from Q3 and less than 1.5 IQR from Q1 are called outliers and needs to be removed.
    - Finding IQR directly 
    
        `Q1 = DataFrame['column_name'].quantile(0.25)`
        `Q3 =DataFrame['column_name'].quantile(0.75)`
        `IQR = Q3 - Q1`
        `left_outliers=print(Q1 - (1.5 * IQR))`
        `right_oulier=sprint(Q3 + (1.5 * IQR))`
3. **Label Encoding**

    categorical data needs to be converted to numerical data to be fed to our model , this can be achieved by importimg label_encoder from sklearn library .

    ![image_2](https://miro.medium.com/max/772/1*QQe-4476Oy3_dI1vhb3dDg.png)
    
	read more from the [official documentation](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.LabelEncoder.html) of this library .  

4. **Evalaution Metrices**
   - Mean Square Error:MSE is calculated by the sum of square of prediction error which is real output minus predicted output and then divide by the number of data points. It gives you an absolute number on how much your predicted results deviate from the actual number. You cannot interpret much insights from one single result but it gives you an real number to compare against other model results and help you select the best regression model.
   
	![image_3](https://miro.medium.com/max/680/1*aFBAjR7kzWirbqORnYa43Q.png)
   
	- Mean Absolute Error:Mean Absolute Error(MAE) is similar to Mean Square Error(MSE). However, instead of the sum of square of error in MSE, MAE is taking the sum of absolute value of error.
   
	![image_4](https://miro.medium.com/max/623/1*tu6FSDz_FhQbR3UHQIaZNg.png)





 


# Car Price Prediction


## Tooling

- Python
  - Numpy
  - Pandas
  - Matplotlib
  - Sklearn 
  - Seaborn
  
## Concepts

- ML Algorithms
   - Linear Regression 
   - SVM
   - Random Forest 
   - XgBoost
   - Decision Tree
 
## How to handle the Data?

 Initially a lot of data cleaning will be required since the data contains a lot of null values. This step is important since the accuracy of our prediction may depend significantly upon how we handle the missing data. Therefore statistical approach towards data cleaning and removing outliers is suggested.

Some of the important operations that i have done in the [notebook](https://github.com/RheagalFire/Car-Price-Prediction-using-different-algo/blob/master/Car-Prediction/Car-Prediction.ipynb) is given below.

1. **Typecasting** 
  - objects need to be first typecasted to strings to further typecast them to integers`.astype(str).astype(int)`
  - strings can be directly typecasted to integers.

2. **Finding Outliers**
	
	Outliers are the anomalies present in the data that unnecesarily increases the rate of error.
	To improve efficiency of our model, we should not train it on such datapoints.
	
	- [Boxplot Method Of removing Data](https://www.simplypsychology.org/boxplot.jpg?ezimgfmt=rs:382x196/rscb24/ng:webp/ngcb24)

        Values greater than 1.5 IQR from Q3 and less than 1.5 IQR from Q1 are called outliers and needs to be removed.
    - Finding IQR directly 
    
        ```python
        Q1 = DataFrame['column_name'].quantile(0.25)
        Q3 =DataFrame['column_name'].quantile(0.75)
        IQR = Q3 - Q1
        left_outliers=print(Q1 - (1.5 * IQR))
        right_oulier=sprint(Q3 + (1.5 * IQR))
        ```
1. **Label Encoding**

    categorical data needs to be converted to numerical data to be fed to our model , this can be achieved by importimg label_encoder from sklearn library.

    ![image_2](https://miro.medium.com/max/772/1*QQe-4476Oy3_dI1vhb3dDg.png)
    
	[Read more.](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.LabelEncoder.html)

4. **Evaluation Metrices**
   - Mean Square Error:MSE is calculated by the sum of square of prediction error which is real output minus predicted output and then divide by the number of data points. It gives you an absolute number on how much your predicted results deviate from the actual number. You cannot interpret much insights from one single result but it gives you an real number to compare against other model results and help you select the best regression model.
   
	![image_3](https://wikimedia.org/api/rest_v1/media/math/render/svg/e258221518869aa1c6561bb75b99476c4734108e)
   
	- Mean Absolute Error:Mean Absolute Error(MAE) is similar to Mean Square Error(MSE). However, instead of the sum of square of error in MSE, MAE is taking the sum of absolute value of error.
   
	![image_4](https://learn.64bitdragon.com/articles/mathematics/statistics/mean-absolute-error/mae.png)
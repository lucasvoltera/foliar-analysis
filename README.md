# Leaf Analysis

## Overview

Leaf analyses are procedures aimed at assessing the concentration of nutrients in leaf samples. These analyses play a significant role in identifying factors that may hinder productivity, such as deficiencies, toxicity, or nutrient imbalances. Thus, it is possible to monitor the effectiveness of fertilization by observing plant responses and nutrient uptake. However, conducting leaf analyses across an entire harvest is laborious and costly. Therefore, a viable alternative is to employ Machine Learning techniques to estimate the quantity of nutrients across the entire plantation. In this approach, information from satellite images, capturing different spectral bands, and results from leaf analyses of select samples at various coordinates are used to create a model. This model learns the relationship between nutrient concentration in leaves and the characteristics of satellite images. Consequently, it becomes possible to estimate nutrient concentration in the plantation, enhancing crop productivity by exercising more control over fertilizer application.

## Results

The first challenge of the project was to discard all coordinates of images that were outside the farm area. Then, an even greater challenge emerged, which was to find a way to create more leaf samples for the image coordinates. The solution to this problem was to use kriging methods to interpolate the points spatially and obtain the closest possible values. The result of the interpolation can be seen in the figure below.

![image](https://github.com/lucasvoltera/foliar-analysis/assets/62965997/83b67681-28b3-42b1-8c12-29f027685615)

After the interpolation and coordinate filtering, a 10-fold cross-validation was conducted, where each fold represents a slice of the farm area. In this process, the Absolute Percentage Error (APE) of the results was calculated in each of the K tests across different models. These results were stored and compared side by side with the nutrient concentration values and model errors, as depicted in the figure below.

![image](https://github.com/lucasvoltera/foliar-analysis/assets/62965997/98647625-2069-4f28-88c9-69584fe4009a)

Different models were tested, and several metrics were extracted from them. Two of these metrics were the Mean Squared Error (MSE) (taken from both the test and training sets) and the Mean Absolute Percentage Error (MAPE). All models performed exceptionally well, predicting results very close to the actual values. For instance, many models achieved a MAPE below 1%, as depicted in the figure below.

![image](https://github.com/lucasvoltera/foliar-analysis/assets/62965997/91a6d2b8-9d2b-4f08-bd4d-0e5f8bb7562d)

## Conclusion

The models yielded excellent results, indicating their ability to estimate the concentration of each nutrient in the leaves very accurately. This can greatly assist farmers in identifying any issues with their crops, by detecting nutrient irregularities and correcting them through proper fertilization. Ultimately, the models ensure higher agricultural productivity, leading to increased profits from the harvests.

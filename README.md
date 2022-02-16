# Digit Recognition using Artificial Neural Networks
The research question of interest is to correctly predict the hand written digit. This has applications in automatic mail sorting or identifying forms based upon the form number such as tax forms and U.S. government standard form series. 

The code can be run interactively through a [Google Colab Notebook]().

## Research design and modeling methods
I utilize an 80/20 train/validate split. I train and fit 4 models with the combination of 1 layer or 2 and nodes of 100 or 500. The independent variables are divided by 255 to properly scale the data for the models. For each model I utilize an early stopping mechanism. If the validation loss increases after two epochs, the fitting stops. This ensures the model isn't over-fitted to the training set. I then check the model against the validation set and generate a confusion matrix and the accuracy/precision/f1-stat for each of the classes.
 
## Results and evaluation
| Metric | Model 1 | Model 2 | Model 3 | Model 4|
|---     | ---     | ---     | ---     | ---    |
| Layers | 1 | 1 | 2 | 2 |
| Nodes | 100 | 500 | 100 | 500 |
| Time (minutes) | 5min 52s | 4min 6s | 10min 34s | 4min 50s |
| Validation Accuracy | 0.973 | 0.975 | 0.973 | .974 |
| Test Accuracy | 0.970 | 0.972 | 0.969 | 0.972 |

Examining the table above, we can see that both Model 2 and Model 4 both out perform Model 1 and Model 3 in both the test accuracy and validation accuracy. Both of these models use 500 nodes in the hidden layer(s) but have different number of layers. It appears to squeeze additional accuracy out of the model appears to be more dependent on the number of nodes chosen than the number of layers. 

## Conclusion
Prior to picking model 2 or model 4 for production, I would want to run more extensive time tests to see what the average is. While Model 2 was ~45 seconds faster than Model 4, this was only a single run and other processes running on my virtual linux box could cause a slower training time between the two models.

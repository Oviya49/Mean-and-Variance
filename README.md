#  Mean and variance of a discrete  distribution


# Aim : 

To find mean and variance of arrival of objects from the feeder using probability distribution


# Software required :  

Python and Visual components tool

# Theory:

The expectation or the mean of a discrete random variable is a weighted average of all possible
values of the random variable. The weights are the probabilities associated with the corresponding values. 
It is calculated as,

![image](https://user-images.githubusercontent.com/103921593/192938463-e34177f4-f188-48a0-bda2-8f6d1d660ed2.png)

The variance of a random variable shows the variability or the scatterings of the random variables.
It shows the distance of a random variable from its mean. It is calcualted as

![image](https://user-images.githubusercontent.com/103921593/192938695-99fedc01-34d5-4d36-84df-5880e766ed0c.png)


# Procedure :

1. Construct frequency distribution for the data

2. Find the  probability distribution from frequency distribution.

3. Calculate mean using 
   
   ![image](https://user-images.githubusercontent.com/103921593/192940431-03b81777-c54d-4286-b4f4-82dfe7666b4c.png)

4. Find  
   
      ![image](https://user-images.githubusercontent.com/103921593/192940255-2d9dd746-6875-4a6d-877b-6da6cdb96ab1.png)

5.  Calculate variance using 
  
      ![image](https://user-images.githubusercontent.com/103921593/192942852-913550a9-fabe-4a55-b956-0487b18bbd97.png)


# Experiment :

![image](https://user-images.githubusercontent.com/103921593/229993174-5b67e57e-3e01-4ac4-9f83-410a932b22bf.png)

# Program :
![ovi](https://github.com/Oviya49/Mean-and-Variance/assets/153576803/5930e60f-bfa1-4136-ad5e-ebd5099c2575)

import numpy as np
L = [int(i) for i in input().split()] # Enter the data as a list of integers separated by spaces
N = len(L) # The number of data points
M = max(L) # The maximum value in the data
x = list() # A list of possible values of arrival
f = list() # A list of frequencies of each value
for i in range(M+1):
    c = 0 # A counter for the frequency
    for j in range(N):
        if L[j] == i: # If the data point matches the value
            c = c + 1 # Increment the counter
    f.append(c) # Append the frequency to the list
    x.append(i) # Append the value to the list
sf = np.sum(f) # The sum of frequencies
p = list() # A list of probabilities of each value
for i in range(M+1):
    p.append(f[i]/sf) # Calculate the probability as frequency divided by sum of frequencies
mean = np.inner(x, p) # Calculate the mean as the inner product of values and probabilities
EX2 = np.inner(np.square(x), p) # Calculate the expected value of square of values
var = EX2 - mean**2 # Calculate the variance as the difference between expected value of square and square of mean
SD = np.sqrt(var) # Calculate the standard deviation as the square root of variance
print("The Mean arrival rate is %.3f" %mean) # Print the mean
print("The Variance of arrival from feeder is %.3f" %var) # Print the variance
print("The Standard deviation of arrival from feeder is %.3F" %SD) # Print the standard deviation




# Output : 
![image](https://github.com/Oviya49/Mean-and-Variance/assets/153576803/30a26c19-281d-4951-b546-ccb0dada5fed)


# Results :
The mean and variance of arrivals of objects from feeder using probability distribution are calculated.


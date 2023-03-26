# Implementing_Optimization_Methods
Consider the following cost function:

![image](https://user-images.githubusercontent.com/125180530/227792203-0334b509-daae-4d3a-b5be-5a41bd72f99f.png)

* First with the use of the 'mesh' function we plot f(x) for:

![image](https://user-images.githubusercontent.com/125180530/227792215-f106f555-ec08-43a8-bd50-8d028cc269e2.png)

It's better to plot the function in the dB domain to have better insight into the changes in f(x). The resulting plot is:

![image](https://user-images.githubusercontent.com/125180530/227792226-9b9c60a4-4be4-4970-96cd-62126ace63c8.png)

* With the 'contour' command we plot the levels of potential:

![image](https://user-images.githubusercontent.com/125180530/227792237-12d5b8ee-c7df-4246-ac3d-0eea02089e28.png)

* By calculating the gradient vector and Hessian matrix we can show that the cost function is convex:

![image](https://user-images.githubusercontent.com/125180530/227792253-be46e008-f6e7-4e31-a074-a3289bdf07d6.png)

![image](https://user-images.githubusercontent.com/125180530/227792263-27d37076-3fb5-4e88-9902-42932abacee3.png)

![image](https://user-images.githubusercontent.com/125180530/227792275-6da3193a-f7bd-4373-a075-697847cd69ec.png)

![image](https://user-images.githubusercontent.com/125180530/227792279-f1992ab2-9641-4a4b-971a-9aa8663c15c4.png)

* Set the calculated gradient to zero to calculate the minimum point:

![image](https://user-images.githubusercontent.com/125180530/227793061-cad90ac5-6b90-4e34-bb76-2879f3dca6ab.png)

![image](https://user-images.githubusercontent.com/125180530/227793077-e577ff7d-84f2-4d14-9f56-f8166307afea.png)

As you see we solve the optimization problem just by calculating the gradient vector. Now we want to use different methods for this aim:

## Steepest Descend
For the initial point that is shown below and for two values of mu, implement this method. 

![image](https://user-images.githubusercontent.com/125180530/227793265-6b5f5344-93f9-45b7-82ba-dffb5004b417.png)

![image](https://user-images.githubusercontent.com/125180530/227793295-e588c512-f739-474a-a7fc-99dcabfd360b.png)

Steepest Descend method obey the following formula for each step of the algorithm:

![image](https://user-images.githubusercontent.com/125180530/227793385-d34fd151-aaeb-431c-b0cc-c8cf418da959.png)

The results of the implementation are as follows:

![image](https://user-images.githubusercontent.com/125180530/227793626-5fc8782b-7802-4908-ba86-bd89dc44da70.png)

![image](https://user-images.githubusercontent.com/125180530/227793649-e2b56afc-22eb-45b8-96ec-611c54a238bc.png)

![image](https://user-images.githubusercontent.com/125180530/227793670-6c4fb5ec-9181-4911-83fe-7cc6c5140985.png)

![image](https://user-images.githubusercontent.com/125180530/227793683-357c5f33-1e16-4b79-a6dd-551bbe9e962d.png)

![image](https://user-images.githubusercontent.com/125180530/227793690-8368cbc6-e713-4957-a5df-5a7000878451.png)

![image](https://user-images.githubusercontent.com/125180530/227793702-d9894dd4-f420-4075-b6ec-e0bec19b8808.png)

***Conclusion***
We can see that in both cases the algorithm converges and the minimum values reached in this method are the same as the minimum values that are reached through calculations.

One point is that the number of iterations needed to reach the final answer when mu is 0.01 is greater than mu = 0.1. In other words, the convergence rate in the first case is higher than in th second one. 

## Newton
For the same initial point, implement Newton's method. This method has the same formula as Steepest Decsend but with a little difference:

![image](https://user-images.githubusercontent.com/125180530/227794109-e138d30d-4c75-4f92-acc5-eaf8b831d138.png)

We have the following result after implementing this method:

![image](https://user-images.githubusercontent.com/125180530/227794291-4c2d324b-6b51-429e-b022-11ac92e4f059.png)

![image](https://user-images.githubusercontent.com/125180530/227794309-be3bfcb7-f0ae-4ecc-91fd-d73cf5928e97.png)

***Conclusion***
One remarkable point is the number of iterations needed to reach the final answer. It's obvious that this number is much less than in the Steepest Descend method. It's because the step value that the algorithm passes to reach the next x is obtained by the Hessian matrix. Intuitively, we use parabolic to reach the next value for x in Netwon's method. So, we expect to have a higher convergence rate in comparison with the Steepest Descend method.

## Alternation Minimization
Just like the previous methods start with the previous initial point. Implementation of this method consists of two steps. In each step we consider one of the variables to be fixed and calculate the minimum of cost function for the other variable. So, we have:

![image](https://user-images.githubusercontent.com/125180530/227797215-85b33a6a-4240-49a9-9560-2f532bd17191.png)

![image](https://user-images.githubusercontent.com/125180530/227797224-b8d7c2da-8a36-476f-ba64-b631801be13d.png)

If we start with the mentioned initial point then we will reach the final answer that we obtained in the previous methods.

![image](https://user-images.githubusercontent.com/125180530/227797237-62067f91-6140-4f78-ad38-7129c777f8f6.png)

Now we do the implementation by the formulas we calculated. The result is shown below:

![image](https://user-images.githubusercontent.com/125180530/227797307-eaafa8da-9c6f-43ca-b4ef-0fcad0f0ecd4.png)

Now we want to show the convergence path in the contoured space. So, the result will be as follows:

![image](https://user-images.githubusercontent.com/125180530/227797409-556f9a85-d371-4513-931c-7b2cd82cd7ec.png)

## Gradient Projection
Consider the mentioned initial point as before and also consider the below constraint:

![image](https://user-images.githubusercontent.com/125180530/227797580-820b4365-b528-4f16-9b79-9ea4fd686ad4.png)

With the use of the Gradient Projection method and by considering the mentioned constraint find the minimum point of the cost function with Gradient Descend algorithm for:

![image](https://user-images.githubusercontent.com/125180530/227797660-4e8a6033-e596-4e02-bb3f-5688099d6d56.png)

The result of the implementation is a little different from other methods and this is because we have to consider the constraint as well.

![image](https://user-images.githubusercontent.com/125180530/227797738-f8d5cd3a-57b7-43c1-b4c0-85cc99965967.png)

Now by the Lagrange algorithm, we solve the problem considering the constraint in the Gradient Projection method and show that the result is the same and the implementation of this method was valid.

![image](https://user-images.githubusercontent.com/125180530/227797989-9de92a70-f385-4713-b095-482e8300b48c.png)

![image](https://user-images.githubusercontent.com/125180530/227797999-c819361a-1ad1-4baf-aa2a-12c58279412b.png)

![image](https://user-images.githubusercontent.com/125180530/227798008-66f001f8-e4b9-4cd7-adbc-e8ad4ee00c0e.png)

![image](https://user-images.githubusercontent.com/125180530/227798012-7e894aa7-f891-4008-9677-b944e48350fd.png)

By solving the above system we have 4 solutions. Two imaginary solutions and two real solutions. Just one of the real solutions has a lower value for cost function and that is the final answer to the problem:

![image](https://user-images.githubusercontent.com/125180530/227798127-b1aa65c7-8533-4e49-8585-3c452d97201c.png)

As you can see the result is merely the same as we reached with the implementation of the Gradient Projection method. 

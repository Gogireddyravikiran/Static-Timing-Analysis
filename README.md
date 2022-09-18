# Static-Timing-Analysis
Static timing analysis (STA) is a method of validating the timing performance of a design by checking all possible paths for timing violations. STA breaks a design down into timing paths, calculates the signal propagation delay along each path, and checks for violations of timing constraints inside the design and at the input/output interface.

## Timing Path

![image](https://user-images.githubusercontent.com/110079770/190552665-bf99cee6-aba9-40b2-a0a8-101de7b8d329.png)

## Example Of Timing Paths

![image](https://user-images.githubusercontent.com/110079770/190560524-e101803d-cb67-4fc0-9532-a50b12e61c36.png)

## Types Of Checks to be Performed 

## Types Of Setup/Hold Analysis 

![image](https://user-images.githubusercontent.com/110079770/190888247-335fa2a4-0370-498c-a171-d0b9fdbfb558.png)

## Slew/Transition Analysis
 
``` 
Two Types Slew/Transition Analysis.
1)Data(max/min)
2)clock(max/min)

```

## Load Analysis

```
Two Types Of Load Analysis
1)Fanout(max/main)
2)Capacitance(max/min)
```

![image](https://user-images.githubusercontent.com/110079770/190888536-3eb65ad6-2489-4fc1-8686-4ec74db1e40d.png)


## Clock Analysis
```
Two Types of Clock Analysis
1)Skew : Difference between the latencies (L1,L2,L3,L4 etc.,) are refferred to as skew.
2)Pulse Width : This type of analysis is performed due to the clock tree network that has parasitic elements in the clock network path we need to see upto which point the pulse width gets degraded to.

```

### Types of Analysis to be performed in Static Timing Analysis

![image](https://user-images.githubusercontent.com/110079770/190888864-7ccf1b68-cd84-4078-8af2-c052c35e5c7e.png)



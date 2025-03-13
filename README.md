- Name: Valentino Vieri Zhuo
- Class: Pemrograman Lanjut A
- NPM: 2306206446


# Module 5 - Java Profiling

## JMeter Pre-Profiling Test Plan Result Screenshot

## GUI:
### 1. /all-student-name endpoint:
![](https://github.com/Mabacore101/adpro-skadi/blob/main/images/preprof1.1.png)
![](https://github.com/Mabacore101/adpro-skadi/blob/main/images/preprof1.2.png)
![](https://github.com/Mabacore101/adpro-skadi/blob/main/images/preprof1.3.png)
![](https://github.com/Mabacore101/adpro-skadi/blob/main/images/preprof1.4.png)

### 2. /highest-gpa endpoint:
![](https://github.com/Mabacore101/adpro-skadi/blob/main/images/preprof2.1.png)
![](https://github.com/Mabacore101/adpro-skadi/blob/main/images/preprof2.2.png)
![](https://github.com/Mabacore101/adpro-skadi/blob/main/images/preprof2.3.png)
![](https://github.com/Mabacore101/adpro-skadi/blob/main/images/preprof2.4.png)

## CLI:
### 1. /all-student-name endpoint:
![](https://github.com/Mabacore101/adpro-skadi/blob/main/images/preprof3.png)

### 2. /highest-gpa endpoint:
![](https://github.com/Mabacore101/adpro-skadi/blob/main/images/preprof4.png)

## JMeter Post-Profiling Test Plan Result Screenshot

## GUI:
### 1. /all-student-name endpoint:
![](https://github.com/Mabacore101/adpro-skadi/blob/main/images/postprof1.1.png)
![](https://github.com/Mabacore101/adpro-skadi/blob/main/images/postprof1.2.png)
![](https://github.com/Mabacore101/adpro-skadi/blob/main/images/postprof1.3.png)
![](https://github.com/Mabacore101/adpro-skadi/blob/main/images/postprof1.4.png)

### 2. /highest-gpa endpoint:
![](https://github.com/Mabacore101/adpro-skadi/blob/main/images/postprof2.1.png)
![](https://github.com/Mabacore101/adpro-skadi/blob/main/images/postprof2.2.png)
![](https://github.com/Mabacore101/adpro-skadi/blob/main/images/postprof2.3.png)
![](https://github.com/Mabacore101/adpro-skadi/blob/main/images/postprof2.4.png)

## CLI:
### 1. /all-student-name endpoint:
![](https://github.com/Mabacore101/adpro-skadi/blob/main/images/postprof3.png)

### 2. /highest-gpa endpoint:
![](https://github.com/Mabacore101/adpro-skadi/blob/main/images/postprof4.png)



## JMeter Measurement Comparison (Pre-Profiling vs Post-Profiling)
After refactoring my code, I can see there's some improvements in JMeter measurements. For /all-student-name endpoint, the average time was 3040ms before profiling and now it's 1019ms after profiling. The speedup for /all-student-name endpoint is about 66,48%. That's more than half of the original time. For /highest-gpa endpoint, the average time was 345ms before profiling and now it's 591ms in JMeter. Now, the code should've improved because in IntelliJ profiling, the slowest method which is findStudentWithHighestGpa was 266ms before profiling and 200ms after profiling, which is around 24% speedup. Now, the discrepancy from JMeter measurement is due to concurrency and load from JMeter. In IntelliJ, the method is executed on a single thread, so there's no contention. On the other hand, JMeter uses concurrency which might cause some thread to experience resource contention. This is the reason why JMeter shows a slowdown while IntelliJ profiler shows a speedup.


## Reflection

### 1. What is the difference between the approach of performance testing with JMeter and profiling with IntelliJ Profiler in the context of optimizing application performance?
In the context of optimizing application performance, JMeter acts like a load test or stress test on the system. JMeter will simulate an actual load in real life and records the systems response time under a specific load. On the other hand, IntelliJ Profiler acts like an internal performance checker. IntelliJ Profiler will check method method execution times, CPU usage, memory execution, etc. In conclusion, JMeter is a stress test, while IntelliJ Profiler is an internal performance checker.

### 2. How does the profiling process help you in identifying and understanding the weak points in your application?
Profiling rocess help me in identifying and understanding the weak points in my application by giving a detailed description on which part of the code takes a long time. The information by the profiler helps me identify which methods take the longest time. After that, I can go to the specific part of the code and start refactoring.

### 3. Do you think IntelliJ Profiler is effective in assisting you to analyze and identify bottlenecks in your application code?
I think IntelliJ Profiler is an effective tool in assisting me to analyze and identify bottlenecks in my application code. This is true because IntelliJ Profiler highlights which method takes the longest time so that I can see it and refactor it. Besides that, IntelliJ Profiler have a small fire logo on the left hand side of the method, so that I can see exactly how long each method takes to run. 

### 4. What are the main challenges you face when conducting performance testing and profiling, and how do you overcome these challenges?
The main challenges I face when conducting performance testing and profiling is reading the data and facing the fact that JMeter can show a discrepancy in performance. I overcome the first challenge by carefully reading the data from the diagram. After some time, I've realize how to read the data and understand it well enough. For the second challenge, I overcome it by realizing that JMeter and IntelliJ Profiler measures performance in a different way. If IntelliJ Profiler shows an increase in performance while JMeter shows a decrease in performance, that's completely normal because JMeter uses multithread and resource contetntion becomes a thing that doesn't exist or not as profound in IntelliJ Profiler.

### 5. What are the main benefits you gain from using IntelliJ Profiler for profiling your application code?
The main benefits I gain from using IntelliJ Profiler for profiling my application code is that the profiler is integrated into the IDE, so I don't have to use multiple apps to profile and run my code. Besides that, IntelliJ Profiler also gives numerical data after each application run and stop. This helps in analyzing which part of the code takes a long time and which one doesn't. Finally, IntelliJ Profiler have a nice feature wwhich is showing the exectution time of each method on the left hand side which helps me see how long each method took.

### 6. How do you handle situations where the results from profiling with IntelliJ Profiler are not entirely consistent with findings from performance testing using JMeter?
For this module, I leave the issue as is because after refactoring, my code is much faster in IntelliJ Profiler and it's much more maintainable. However, this maintainability causes a much serious resource contention in JMeter. There's nothing much I can do at this point, but just leave it as is because maintainability is much prefered over unmaintanable code that performs well.

### 7. What strategies do you implement in optimizing application code after analyzing results from performance testing and profiling? How do you ensure the changes you make do not affect the application's functionality?
I simplify the method implementation for the resource intensive part of my code after analyzing results from performance testing and profiling. I've remove the many loops into a basic return line that returns the required data. Although, there's still a loop when using findAll and max, the changes does optimize the code by more than 20% in IntelliJ Profiler. I try to rerun the program again and then see whether the output is the same as the output before refactoring. By doing this, I can check whether a change in implementation causes a change in the result.

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

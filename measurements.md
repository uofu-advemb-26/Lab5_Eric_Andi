# Measurements
We set out delay to 100 ms and our busy loop as an empty for loop counting to 10,000. Therefore, our expected period is 200 ms without delay.
## Sleep
Before the busy loop, we measured the period at 199.99 ms. After the busy loop, we measured the period at 201.59 ms. So that means we measured a total delay of 1.6 ms every period, or 0.8 ms every toggle. 

## Timer Delay
Before the busy loop, we measured the period at 199.99 ms. After the busy loop, we measured the period at 199.99 ms. So, introducing the busy loop did not add any delay when using a timer for counting time.

## Task Delay
Before the busy loop, we measured the period at 199.99 ms. After the busy loop, we measured the period at 199.99 ms. We expected to get a noticable delay here, like we did for the sleep methodolody of timekeeping after introducing a busy loop, but we didn't. 

## GPIO Interrupt


## Task Delay with two threads
When we added a second thread with the same priority that only had a while(1) loop in its body, and set the task delay to 1 ms, the period of the output was 2 ms. This means that the second task didn't add any delay to the period.

When we added an additional thread (now up to three threads, two of which are a while(1) loop), the period increased to 4ms. This is double the expected period. 
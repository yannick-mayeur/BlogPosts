# WEEK SIX

## What I did

This week I got reintroduced to JUnit, having forgotten most of what I learned
about it as the IUT. Junit is a unit testing framework. It is used to test the
different methods of a programm to see whether or not the intended behavior is
working. It is often said that a method that is not tested is a method with
bugs, and after a week of testing this saying probably is true.

My job this week was to improve the test coverage of Eclipse January. You can
calculate the coverage of a programm using the EclEmma plugin. I worked on the
DatasetUtils class, improving the coverage from 47% to almost 58%, and fixing
bugs in two methods (https://github.com/eclipse/january/pull/178 and
https://github.com/eclipse/january/pull/188).

Seeing that bugs can even be is untested code written by people that know a lot
more what they are doing than I am, really showed me the importance of testing.

## How I did it

This is a test I have written for the method "crossings", writing this test
helped me point out some unexpected behaviour in the way it works.
```java
@Test
public void testCrossings3() {
	Dataset yAxis = DatasetFactory.createFromObject(new Double[] {
			0.5, 1.1, 0.9, 1.5 });
	Dataset xAxis = DatasetFactory.createFromObject(new Double[] {
			1.0, 2.0, 3.0, 4.0 });
	List<Double> expected = new ArrayList<Double>();
	expected.add(2.5);
	List<Double> actual = DatasetUtils.crossings(xAxis, yAxis, 1,
			0.5);
	assertEquals(expected, actual);
}
```
This shows what the values are looking like:
![behaviour](https://cloud.githubusercontent.com/assets/14848887/26053575/49820a9c-3961-11e7-80be-c7cc338d7a1e.png)

The expected behaviour of the method as written in the test would be that the 3
crossing points would be merged into one at 2.5, but this wasn't what was
happening, indeed the code was using ">" instead of ">=". If not tested this
bug would probably never have been discovered.

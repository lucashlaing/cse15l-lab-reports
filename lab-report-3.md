# Lab Report 3
## Part 1 : Bugs


For bugs, we will be looking at the  `reversed` method from week 4. It is suppsoed to reverse the array that is passed in as a parameter. For example, an array with the elements `{1, 2}` should change to be `{2, 1}` after a call to the  `reversed` method with said array as an argument. However, this method does not work as intended.


### A failure-inducing input
```
  @Test 
	public void testReverseInPlace() {
    int[] input1 = { 3,5,1 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 1,5,3 }, input1);
	}
```


## An input that does not cause a failure 

```
	@Test 
	public void testReverseInPlace2() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}
```


### The intial code that was causing the failure
```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```


### The fixed version of the code
```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length/2; i += 1) {
      int temp = arr[arr.length- i - 1];
      arr[arr.length- i - 1] = arr[i];
      arr[i] = temp;
    }
  }
```


The problem with the inital code was taking the elements from the end of the array and putting them to the front of the array. However, once we get to the second half of the array, we realize that the elements initally at the start of the array have been overwritten and therefore cannot be copied to the back. This just creates an array which is like a palindrome. Our code fixes the problem because we only go till half the array. We start from both ends and swap each of these elements with one another. This ensures we have all the data we need and nothing gets overwritten before it is put into another spot.


## Part 2: Researching Commands


For this part, we will be looking at the command `grep`.

### `grep -i`

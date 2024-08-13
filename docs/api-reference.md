# API Reference

## API

```
public static void findNeedles(String haystack, String[] needles) {
if (needles.length > 5) {
System.err.println("Too many words!");
} else {
int[] countArray = new int[needles.length];
for (int i = 0; i < needles.length; i++) {
String[] words = haystack.split("[ \"\'\t\n\b\f\r]", 0);
for (int j = 0; j < words.length; j++) {
if (words[j].compareTo(needles[i]) == 0) {
countArray[i]++;
}
}
}
for (int j = 0; j < needles.length; j++) {
System.out.println(needles[j] + ": " + countArray[j]);
}
}
}
```

## Method Signature

`public static void findNeedles(String haystack, String[] needles)`

## Description

The findNeedles method searches a given text (i.e., the Haystack string) for occurrences of the words specified in the Needles array. It counts the occurrences of each word in the text and prints the counts. Use the following steps to call the API: 

1. Define the Haystack string.
2. Define the Needles array.
3. Call the findNeedles method.
4. View the output.

## Parameters

- Haystack: The given text (i.e., string) in which to search for occurrences of the words specified in the Needles array
- Needles: An array of strings representing the words to search for in the Haystack string

## Return Type

This method does not return a value; instead, it prints the counts of occurrences for each word in the Needles array.

## Exceptions

If the length of the needles array exceeds 5 , then the method will print the "Too many words!" error message.

## Example

The following sections contain example code for calling the API and its expected output.

### Usage

String haystack = "The courageous horse swam through the raging river.";
String[] needles = {"courageous", "horse", "raging"};
findNeedles(haystack, needles);

### Output

courageous: 1
horse: 1
raging: 1

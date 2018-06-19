# TDChallenge

This is a personal challenge project, whose purpose is to validate a file with phones and identify the appropriate area codes for each.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites

To run the project, you will need to clone it to your workspace and have jdk installed at least in version 6 onwards and have the maven for build it. In addition, you will need to create a text file with the phone numbers in the project's root directory with the following pattern:

```
+351960000000
00351960000000
+00112
```
Finally, copy the file area_codes.txt to the root directory of the project as well.

### Executing

To run the program, you will have two options, the first will be through the configuration of running your IDE, informing as the initialization parameter, the name of the phone file, for example:

```
arquivo_telefones.txt
```

the second way, is generating the TDChallenge-0.0.1-SNAPSHOT.jar file in the project's target folder and copying that file to a chosen directory along with the phone file and area_codes.txt. After doing this run the java as follows:

```
java -jar TDChallenge-0.0.1-SNAPSHOT.jar arquivo_telefones.txt
```

The output of the program will be the number of valid area codes in a sequential way, as in the example below:

```
1:3
55:2
341:5
```

## Running the tests

To run the tests, you can through your IDE send the command to run all the unit tests of the project in the junit tests menu. Anyway, the tests will run automatically when building the project through Maven.

### Break down into end to end tests

The tests were configured to test from the sorting algorithm such as:

```
	@Test
	public void sortTest() {
		QuickSortAlgorithmImpl quickSort = new QuickSortAlgorithmImpl();
		ArrayList<String> numberList = new ArrayList<>();
		numberList.add("10");
		numberList.add("3");
		numberList.add("6");
		ArrayList<String> result = quickSort.sort(numberList);
		Assert.assertEquals(result.get(0), "3");
		Assert.assertEquals(result.get(1), "6");
		Assert.assertEquals(result.get(2), "10");
	}
```
Even the validation algorithm, such as:

```
@Test
	public void validateTelephoneNumberTest() {
		String telephone1 = "+559988 12 34   55";
		String telephone2 = "+ 112";
		ArrayList<String> telephoneList = new ArrayList<>();
		LinkedHashMap<String, Integer> areaCodes = new LinkedHashMap<String, Integer>();
		telephoneList.add(telephone1);
		telephoneList.add(telephone2);
		areaCodes.put("1", 0);
		areaCodes.put("55", 0);
		TelephoneNumberValidator telephoneNumberValidator = new TelephoneNumberValidator();
		LinkedHashMap<String, Integer> result = telephoneNumberValidator.validate(telephoneList, areaCodes);
		Assert.assertEquals(result.get("1").toString(), "0");
		Assert.assertEquals(result.get("55").toString(), "1");
	}
```
Having coverage above 92% of code

## Deployment

Add additional notes about how to deploy this on a live system

## Built With

* [Maven](https://maven.apache.org/) - Dependency Management

## Versioning

For versioning, i used the gitHub platform. For more details, (https://github.com/)

## Authors

* **Egilson Cabral** - [TDChallenge](https://github.com/egilsoncabral/TDChallenge)


# hackerrank-java-basic-cert-answer

## Type Counter
Identify the different types present in an input string and report their counts. Each of the substrings, separated by one or more spaces, is one of either the String, Integer, or Double type. Print the results on 3 lines in the order shown in the example. If a type does not occur, report that type with a count of 0.

Example.
sentence = "can you give me 10 bucks puff in 7.5 or 7"

Expected output is:
string 8
integer 2
double 1

There is a single space between the type and the count.

function's name is "typeCounter" and it has a parameter called "sentence" and its type is String.

Constraints:

The length of sentence <= 30000 characters,
sentence has fewer than 1000 words.
One or more space characters separate the substrings to analyze.
Each string type substring consists of lowercase English letters only.
Each numeric type substring consists of digits from 0 to 9, and .(decimal point) only

### Answer:

    public static void typeCounter(String sentence) {
        // check if the sentence length is valid
        if (sentence.length() > 30000) {
            System.out.println("Invalid input. Sentence length must be less than or equal to 30,000 characters.");
            return;
        }

        int strCount = 0, intCount = 0, doubleCount = 0;

        String[] words = sentence.split("\\s+");

        // check if the number of words is valid
        if(words.length > 1000) {
            System.out.println("Invalid input. Sentence must have less than 1,000 words.");
            return;
        }
        
        for (String word : words) {
            try {
                Double.parseDouble(word);

                // check if the word is a valid number
                if(word.matches("[0-9\\.]+")) {
                    if (word.contains(".")) {
                        doubleCount++;
                    } else {
                        intCount++;
                    }
                } else {
                    System.out.println("Invalid input. Numeric substrings can include digits and the decimal point only.");
                    return;
                }
            } catch (NumberFormatException e) {
                // check if the word is a valid string
                if(word.matches("[a-z]+")) {
                    strCount++;
                } else {
                    System.out.println("Invalid input. String substrings can include lowercase letters only.");
                    return;
                }
            }    
        }

        System.out.println("string " + strCount);
        System.out.println("integer " + intCount);
        System.out.println("double " + doubleCount);
    } 



## 1
class BitPuzzle {
  public static void main(String[] args) {
    int mask = 0x000F;
    int value = 0x2222;
    System.out.println(value & mask);
  }
}

what is the output?
### Answer: The output of your code will be 2.

## 2
interface Syrupable {
void getSugary();
}

abstract class Pancake implements Syrupable {}

class BlueBerryPancake implements Pancake{
public void getSurgary() {;}
}
class SourdoughBlueBerryPancake extends BlueBerryPancake {
void getSurgary(int s) {;}
}

for this code, please choose correct one from the following:

Compilation succeeds.
Compilation fails due to an error on line2.
Compilation fails due to an error on line4.
Compilation fails due to an error on line6.
Compilation fails due to an error on line7.
Compilation fails due to an error on line9.
Compilation fails due to an error on line10.

### Answer: Compilation fails due to an error on line4.

## 3
try {
Float f1 = new Float("3.0");
int x = f1.intValue();
byte b = f1.byteValue();
double d = f1.doubleValue();
System.out.println(x + b + d);
}
catch(NumberFormatException e) {
System.out.println("bad number");
}

please select correct answer from the following:

9.0
bad number
Compilation fails on line 9
Compilation fails on line 11

### Answer: 9.0

## 4
what is a covariant return type?

pick correct one:
1. The overriding method can have derived type as the return type instead of the base type
2. The overriding method can have base type as the return type instead of the derived type
3. The return type is of the class type Covariant
4. The return type is void

### Answer: 1. The overriding method can have derived type as the return type instead of the base type

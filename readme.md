# NATO Alphabet Generator

## **[100 Days of Code: The Complete Python Pro Bootcamp for 2023](https://www.udemy.com/course/100-days-of-code/)**

By Dr. Angela Yu

*Day 26 of 100:* List Comprehension and the NATO Alphabet

## Project Specs

Using the **[Pandas Library](https://pandas.pydata.org/docs/user_guide/index.html)**, develop an application that converts a word to the *(International) Radiotelephony Spelling Alphabet*, more commonly known as the **[NATO phonetic alphabet](https://en.wikipedia.org/wiki/NATO_phonetic_alphabet)**, used for clearly communicating the letters of the Roman alphabet.

This application is written with Python 3.11.

![alt text](https://github-readme.s3.us-west-1.amazonaws.com/NATOAlphabet.png)

### Main Features
This simple application asks the user to enter a word for NATO translation, and is engaged in the PyCharm run console.

## Usage & Requirements

This project uses one library package:
- Pandas

### Workflow
Data is read from the `nato_phonetic_alphabet.csv` file using the Pandas `.read_csv()` library function and stored into a dictionary: 

```
data = pandas.read_csv("nato_phonetic_alphabet.csv")
nato_dict = {row.letter:row.code for (index, row) in data.iterrows()}
```

Then we create a `generate_phonetic()` function that captures the user input and then using a `try / except / else` block, we attempt to translate the word into its appropriate NATO alphabet parts:

```angular2html
def generate_phonetic():
    word = input("Please enter a word for NATO Translation: ").upper()
    try:
        result = [nato_dict[letter] for letter in word]
    except KeyError:
        print("Sorry, only letters in the alphabet please.")
        generate_phonetic()
    else:
        print(result)
```

If the user entered any input other than letters (such as spaces or numbers), the program captures this error, informs the user of the issue, and then restarts the program from the beginning.

# Getting Started

All the commands below should be typed into the Python terminal of your IDE (I use PyCharm for my Python Development).

First, clone the repository from Github and switch to the new directory:

    $ git clone git@github.com:shelbyblanton/nato-alphabet.git
    
Then open the project in PyCharm.

In the `main.py` file, click on the word `pandas` in the import statement at the top of the page. Then click on the red exclamation point and click `Install Package Pandas` to load the library:

![alt text](https://github-readme.s3.us-west-1.amazonaws.com/Install-Pandas.png)

**Setup is complete!** 

Click Run in PyCharm to see the app in action.


# Author & Credits

Programmed by **[M. Shelby Blanton](https://www.linkedin.com/in/shelbyblanton/)** under the instructional guidance of **[Dr. Angela Yu](https://www.udemy.com/user/4b4368a3-b5c8-4529-aa65-2056ec31f37e/)** via **[Udemy.com](udemy.com)**.

Project URL: http://www.cs.nyu.edu/~ym943/cgi-bin/vocab.cgi

Overview

In this assignment, we will create a web application to help learn vocabulary words. The web site freevocabulary.com contains a list of about 5,000 words and short definitions. I have extracted this list into the file /home/unixtool/data/vocab.dat. Your task is to write a CGI script that presents and grades a vocabulary quiz.  You will learn Python and CGI scripting in this assignment, which will lead you to the final project.  For details on how to set up CGI at CIMS.

Quiz Creation

The first step of this assignment is to create the quiz. Your CGI script will pick ten random words from the data file, and for each of these present four definitions (one correct and three incorrect ones). The user will pick the correct definition by using an appropriate HTML form element (such as radio or drop down menu). After submitting the form, your CGI script will grade the answers and report back to the user which answers were correct and which were incorrect.
The file has three fields in it: word, part of speech, and definition using | as a delimiter. Here is an example line:
      muddle|v.|To confuse or becloud, especially with or as with drink. 
To implement quiz creation, we suggest reading in the entire data file and picking 40 random entries: 16 nouns (n), 12 verbs (v), and 12 adjectives (adj). These words will be used to generate 4 noun questions, 3 verb questions and 3 adjective questions. Don't pick any of the same entry twice! You may want to consider Python's handy random.shuffle function.
To generate the quiz, you will pick 4 entries of the same part of speech at a time.  The definitions for each of these 4 entries will be the possible options in the quiz that the user will select from.  The word for one of the 4 entries will be chosen at random and made the question.  For example, consider the following selected entries:
illegitimate|adj.|Unlawfully begotten.
natal|adj.|Pertaining to one's birth.
pugnacious|adj.|Quarrelsome.
nefarious|adj.|Wicked in the extreme.
If we randomly picked "pugnacious" as the word, something like the following would be displayed:
pugnacious:
  ◎ Unlawfully begotten.
  ◎ Pertaining to one's birth.
  ◎ Quarrelsome.
  ◎ Wicked in the extreme.

Quiz Grading

When the form is submitted, your CGI script will grade the test and report the results.
In order to do this, you will want to store the correct answer as a hidden form element in the generated quiz. When the quiz is submitted, your CGI script will compare the hidden form elements to the user selected form elements.
The rendered page should display (1) a summary of how many answers were correct, (2) a list of the correct words in green and (3) a list of the incorrect words in red.

Implementation

This is a Python scripting assignment, so you are required to write your CGI script in Python. You should implement all functionality as a single script (quiz presentation vs. grading can be decided based on CGI variables). Do not have Python call external commands. You are welcome to us as many html files or python modules as you'd like, but they should all be used by the single main CGI script.

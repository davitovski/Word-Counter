# Word-Counter
This code counts the occurrences of each word in a given text or document. It tokenizes the input text, removes any punctuation marks, converts all words to lowercase, and creates a dictionary with word frequencies.

import string

def count_words(text):
    text = text.lower()
    text = text.translate(str.maketrans("", "", string.punctuation))
    words = text.split()
    word_count = {}
    for word in words:
        if word in word_count:
            word_count[word] += 1
        else:
            word_count[word] = 1
    return word_count

input_text = "This is a sample text. It contains some words. The words may repeat."
word_frequency = count_words(input_text)
for word, count in word_frequency.items():
    print(f"{word}: {count}")


<h1 align = 'center'> Qgen </h1>
<h2 align='center'>BERT, SpaCY, Wordnet & more ...</h2>

<h2 align='center'> About </h2>
<p align='center'>
Many times, we read our notes again and again, without ever getting any information inside our head. Havent you noticed that whenver there is a quiz, or whenever you take a test, you learn the material better? Hence, we have created an app, which used Machine Learning and Natural Language Processing to generate flashcards, quizzes, and summary from your notes! Moreover, we have three types of questions: MCQ, Fill in the blanks, and True or False questions to test you on your notes.
You can also upload handwritten notes to generate quizzes so that you can directly upload a photo and generate a quiz.
</p>

-----------------------------------

# Concepts

* **Transformer** - A transformer architecture is an encoder-decoder network that uses self-attention on the encoder side and attention on the decoder side.
* **BERT** - Relaeased in 2018 by researchers at Google, BERT stands for Bidirectional Encoder Representations from Transformers. BERT is the encoder part of the transformer architecture. 
* **Extractive Summarization** - In NLP, we usually have two types of summarization- extractive and abstractive. Extractive deals with extracting important sentences from the text corpora and abstractive is the summary of the whole text in one's own words.
* **Embeddings** - Embeddings are just the vector representations of the words which is a way of understanding textual data by computers, since computers only understand the language of binary. 

# Models Used

* **Fillups generations** - Here, using the sentence-transformers, we first find the document embeddings and the word embeddings of all the candidate words. Document embeddings are the representation of the whole document and candiate embeddings are the word embeddings of the candidates. Then, using the cosine similarity we calculate the top_n most similar words to the document embedding and label them as keywords. We find sentences having those keywords and these form the question for fill in the blanks and the corresponding keyword being the answer.
* **MCQs generations** - The same procedure is followed for generating keywords anf the corresponding sentences. Now, for the wrong options for MCQs, we choose random keywords from the list of keywords. 
* **True-False generations**- Fist, we find the root word using the spaCY library. Then we try to find the negation i.e. hypernms and antonyms of the word using wordnet. Now, if the antonyms exist we replace the word with antonym and the statement becomes False. But if the antonym does not exist, we find the numbers, proper-nouns in the whole corpora and replace it in the sentence and change them, else we randomly choose to either take or not take the sentence as a question as a False question.
* **Image-to-text** - We used the pre-trained easyocr which is the optical character recognition library. It gives us the position as well as the string representation of the text in the image.

Backend, Frontend, ML repository are kept private. 

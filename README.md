# **Automated Multiple-Choice Question Generation Using SpaCy**
![Automated MCQ Generator](https://github.com/rdcodings/Automated-MCQ-Generation-Using-SpaCy/blob/99322bebde966f7f0a61f6f4f05577867a59e68e/Work%20Sample.JPG)

### Overview

This project is designed to automate the creation of multiple-choice questions (MCQs) from textual content using natural language processing (NLP). By leveraging the spaCy library, the script processes input text to identify key terms and generate fill-in-the-blank style questions, complete with answer choices. This tool is highly versatile and can be applied in educational content creation, e-learning platforms, corporate training, and more. Additionally, it supports different languages, such as Bengali, when the input text is provided in Unicode.

### Introduction

Creating MCQs manually can be time-consuming and labor-intensive. This project aims to simplify the process by automating the generation of questions directly from text, saving time and ensuring consistency. Whether used by educators, content creators, or developers, this tool offers a streamlined solution for generating quizzes and assessments from any given text.

### Methodology

The project utilizes spaCy, a powerful NLP library, to process input text and extract key terms such as nouns, proper nouns, adjectives, and numbers. These terms are then used to generate fill-in-the-blank questions. The methodology includes:

1. **Text Processing**: The input text is processed using spaCy to break it down into sentences and identify important words.
2. **Key Term Extraction**: Nouns, proper nouns, adjectives, and numbers are extracted as potential candidates for the questions.
3. **Question Generation**: Selected key terms are replaced with blanks, and a set of answer choices is generated, including the correct answer and distractors.
4. **Answer Shuffling**: The answer choices are shuffled to ensure the correct answer is not always in the same position.

### Algorithm

1. **Input**: The text passage and the desired number of questions.
2. **Sentence Selection**: Randomly select sentences from the text.
3. **Key Term Identification**: Extract key terms (nouns, proper nouns, adjectives, numbers) from each selected sentence.
4. **Question Creation**: Replace a key term with a blank and generate answer choices, including distractors.
5. **Answer Shuffling**: Randomly shuffle the answer choices and identify the correct answer.
6. **Output**: Return the generated MCQs, each with a question stem, answer choices, and the correct answer.

### Applications

- **Educational Content Creation**: Automate the creation of quizzes and exams from instructional content.
- **E-Learning Platforms**: Integrate this tool to generate practice questions for students.
- **Corporate Training**: Generate assessments from training manuals and policy documents.
- **Language Learning**: Create exercises for vocabulary and comprehension from reading passages.
- **Test Preparation**: Automatically generate practice questions for standardized tests.
- **Interactive Learning Tools**: Use in educational games and tools for a more engaging learning experience.

```
1. Initialize spaCy model (load NLP pipeline)

2. Define function `generate_mcqs(text, num_questions)`

    a. Process the input `text` using the spaCy model to create a `doc` object.
    
    b. Extract sentences from the `doc` object and store them in a list `sentences`.
    
    c. Randomly select a number of sentences (equal to `num_questions` or fewer) from `sentences` and store them in `selected_sentences`.

    d. Initialize an empty list `mcqs` to store generated MCQs.

    e. For each `sentence` in `selected_sentences`:
    
        i. Process `sentence` using the spaCy model to create a `sent_doc` object.
        
        ii. Extract key terms (nouns, proper nouns, adjectives, and numbers) from `sent_doc` and store them in a list `nouns`.
        
        iii. If `nouns` contains fewer than 2 items, skip to the next sentence.
        
        iv. Randomly select one key term from `nouns` to be the `subject` of the question.
        
        v. Create the question stem by replacing the `subject` in `sentence` with a blank ("__________").
        
        vi. Initialize a list `answer_choices` with the `subject` as the correct answer.
        
        vii. Identify potential distractors by taking other items from `nouns` and store them in `distractors`.
        
        viii. If there are at least 3 distractors, randomly select 3 of them and add them to `answer_choices`.
        
        ix. If there are fewer than 3 distractors, add all available distractors to `answer_choices`.
        
        x. Shuffle the `answer_choices` to randomize their order.
        
        xi. Determine the `correct_answer` by finding the position of the `subject` in `answer_choices`.
        
        xii. Add the tuple `(question_stem, answer_choices, correct_answer)` to the `mcqs` list.

    f. Return the list `mcqs` as the final output.

3. Example usage:

    a. Define a text passage `text`.
    
    b. Specify the desired number of questions `num_questions`.
    
    c. Call the `generate_mcqs` function with `text` and `num_questions` as arguments.
    
    d. Print each generated MCQ, including the question stem, answer choices, and correct answer.
```


### Conclusion

This project demonstrates the effective use of NLP techniques for automating the generation of MCQs from text. By leveraging spaCy, the script efficiently processes and extracts key information, enabling quick and consistent question creation. Its versatility in handling different languages when encoded in Unicode further enhances its applicability across various fields. The project represents a significant advancement in integrating NLP into practical educational and content delivery systems, offering an innovative and scalable solution for generating assessments.

---

Author- *Rajarshi Das*

# CommonLit-Evaluate-Student-Summaries-Kaggle

## Overview 
In this competition, the main objective is to develop a model that can evaluate the quality of summaries created by students in grades 3-12. The model's assessment will focus on how well the students capture the main idea and details of a given source text, as well as the clarity, precision, and fluency of their writing. A dataset of actual student summaries will be provided for training the model.

https://www.kaggle.com/competitions/commonlit-evaluate-student-summaries/overview

The competition is aimed at supporting teachers in efficiently assessing student work quality and aiding learning platforms in offering prompt feedback to students.

Summary writing is a crucial skill for learners of various ages, aiding reading comprehension, especially for second language learners and those with learning difficulties. This skill also promotes critical thinking and is effective in enhancing writing capabilities. However, students often lack opportunities to practice summarization due to the time-consuming nature of evaluation for teachers. Advanced technology like large language models (LLMs) could revolutionize this by enabling quick assessment by teachers.

While automated evaluation methods for student writing have advanced, particularly for argumentative or narrative writing, these techniques don't apply as well to summary writing. Evaluating summaries introduces added complexity, requiring consideration of both the student's writing and a longer source text. Although some techniques exist for evaluating summaries, they often focus on generated summaries rather than actual student writing due to the lack of appropriate datasets.

The competition is hosted by CommonLit, a nonprofit educational technology organization focused on equipping all students, especially those in Title I schools, with essential skills for success in higher education and beyond. Collaborating with CommonLit are The Learning Agency Lab, Vanderbilt University, and Georgia State University.

The successful development of summary scoring algorithms in this competition will provide a valuable tool for both teachers and students. Students will have more chances to practice summary writing, leading to improvements in reading comprehension, critical thinking, and writing skills.

## About Data

The dataset for this competition consists of approximately 24,000 summaries created by students in grades 3-12. These summaries are based on passages covering various topics and genres. Each summary has been assigned scores for both its content and wording. The objective of the competition is to predict content and wording scores for summaries on topics that have not been seen before.

Here is an overview of the files and fields in the dataset:

**summaries_train.csv:** This file contains the summaries in the training set.

  1. **student_id:** The unique ID of the student writer.
  2. **prompt_id:** The ID of the prompt associated with the summary, linking to the prompt file.
  3. **text:** The full text of the student's summary.
  4. **content:** The content score for the summary (the first target).
  5. **wording:** The wording score for the summary (the second target).
  
**summaries_test.csv:** This file contains the summaries in the test set, similar to summaries_train.csv. However, it lacks the content and wording fields.

**prompts_train.csv:** This file provides information about the prompts used for training.

  1. **prompt_id:** The unique ID of the prompt, linking to the associated summaries and prompt text.
  2. **prompt_question:** The specific question posed to students for summarization.
  3. **prompt_title:** A brief title for the prompt.
  4. **prompt_text:** The complete text of the prompt.
  
**prompts_test.csv:** This file is similar to prompts_train.csv but for the test set. It lacks the prompt_id field and contains only an example of the prompts used for testing. The complete test set includes a larger number of prompts, and the train/test splits have     distinct prompts.


## Submission
Submissions in the competition are evaluated using the MCRMSE (mean columnwise root mean squared error) metric, which calculates the average root mean squared error between the actual and predicted values across different target columns in the dataset.
$${MCRMSE} = \frac{1}{N_{t}}\sum_{j=1}^{N_{t}}\left(\frac{1}{n} \sum_{i=1}^{n} (y_{ij} - \hat{y}_{ij})^2\right)^{1/2}$$

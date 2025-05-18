<h2>LoRA-Based Fine Tuning of BART-small for News Article Summarization</h2>
<p>This repository holds the training script for training BART-small for abstractively summarizing news text in partial fulfillment of the requirements in the course Machine Learning 2. A more comprehensive reading on the goals, methods, and conclusions of the project can be found in the project paper.</p>

<h2>📌Directory</h2>
<ul>
  <li>Project Paper</li>
  <li>Training Script</li> 
</ul>

<h2>📃Introduction</h2>
<p>News summarization is an application of automatic summarization in Natural Language Processing that generates a shorter version of a full news article while preserving its most important information. Key challenges in abstractive summarization, a branch of text summarization that generates new sentences to summarize the original text, include inadequate representation of meaning, maintaining factual consistency, and addressing temporal and causal reasoning. Despite progress, models still face difficulties in capturing semantic nuances and striking the right balance between completeness and conciseness.</p>

<h2>🎯Objectives</h2>
<p>The goal is to produce a summary that reads naturally—similar to how a human might summarize the article—while retaining the essential facts and context of the original news story. This task involves understanding the meaning of the text and generating summaries that are both informative and linguistically fluent.</p>

<h2>📚About the Dataset: <i>therapara/summary-of-news-articles</i></h2>
<p>The dataset can be found on <a href = '[therapara/summary-of-news-articles](https://huggingface.co/datasets/therapara/summary-of-news-articles)'>this</a> link. It contains a total of 56 240 rows, which are divided into three subsets: a training set with 45,000 rows, a validation set with 5,620 rows, and a test set also containing 5,620 rows. There are two features: <b>document</b>, which contains the original news content, and <b>summary</b>, which is the summarized version of the document column.</p>

<h2>🧠About the Model: BART-small</h2>
<p>The base model used in this project is BART-small, a smaller version of BART with fewer attention heads for the news summarization task. BART is widely recognized for its effectiveness in natural language generation, particularly in summarizing long-form text, making it a suitable choice for our project. However, due to limited computational resources, a lightweight variant was chosen to balance performance with efficiency. </p>

<h2>⚙️Methodology</h2>
<h4>Data Preprocessing</h4>
  <p>1. Tokenization on input and output fields (max_length = 512 for both fields)</p>
  <p>2. Applying DataCollatorForSeq2Seq to pad sequences</p>
<h4>Fine-tuning with LoRA and Adam Optimizer</h4>
  Initial run through on the model:
  <p>Epochs = 20</p>
  <p>Training Steps = Epoch * tokenized_dataset</p>
  <p>Warmup Steps = 0.1 * Training Steps</p>

<h4>Final Settings</h4>
<p></p>
<h2>📝Evaluation and Results</h2>

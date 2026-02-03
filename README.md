# Data Science Practicum Project Proposal
Project Sponsor: Linda Clark (feat. Eric Kaldor and Michael Littman)
Students: Jimmy Lin, Qinjunjie Pu, Linzhuo Zhang
## Context

The rapid rise of Generative AI (GenAI) tools such as ChatGPT has created both exciting new opportunities and significant challenges for higher education institutions. Universities worldwide are facing the challenge of adapting their academic integrity policies and teaching methodologies. At Brown University, individual instructors have begun to formulate their own course-specific policies regarding the use of AI. However, there is currently no centralized understanding of the prevalence, nature or tone of these policies across different departments and academic levels. This project exists to bridge that information gap. By systematically analyzing the full corpus of course syllabi from the 2023-2024 and 2024-2025 academic years, the project provides a data-driven, evidence-based overview of the current landscape. These findings will help the university develop clear guidelines, highlight effective policies, and support faculty as they adapt to new AI tools.

## Goals and OKRs
Goal 1: Quantify the adoption and demographic distribution of AI policies in Brown University courses for the 2023-24 and 2024-25 academic years. 
We will process all provided course syllabus from the 2023-24 and 2024-25 academic years to:
Identify and count every syllabus that contains a mention of AI, using a predefined list of keywords (e.g., ChatGPT, LLM, Generative AI).
Extract key demographic data for each course: Department, Knowledge Area (Humanities, Social Science, etc.), and Academic Level (under 1,000 level vs. over 1,000 level).
Generate lists of classes that do and do not contain an AI policy.
Our aim is to Successfully extract usable text from over 95% of all provided syllabus and achieve over 90% accuracy in identifying the presence or absence of an AI policy. This will be validated by manually reviewing a random sample of 200 syllabus and comparing the result to our automated script's output.
Output: Producing clear summary statistics and visualizations (e.g., bar charts, tables) that show the percentage of AI policy adoption across different departments, knowledge areas, and academic levels.

Goal 2: Analyze and categorize the content, tone, and nature of all identified AI policies.
For every syllabus identified as containing an AI policy, we will:
Extract the specific text of the policy itself and any mentions of AI outside of an AI policy.
Perform thematic analysis (e.g., using clustering) to discover the main topics discussed (e.g., academic integrity, proper citation, tool for brainstorming).
Conduct sentiment analysis to assign a quantitative score (e.g., negative, neutral, positive) to the tone of each policy.
Classify each policy into a predefined 'level' of use (e.g., 'no use,' 'some use,' 'integrated use').
The goal is satisfied once we have extracted policy text from at least 95 % of all syllabi that mention AI and our models, evaluated on a stratified, manually annotated test set of 200 policies, reach a macro-F1 of 0.85 or better for sentiment classification and ≥ 90 % accuracy when assigning the “no use / some use / integrated use” levels. For the sentiment analysis and level classification part, we apply distillation to set the target variable in the training process. (The thematic analysis will be reported qualitatively and is not tied to a numeric target.)

## Data Science Competency Areas
Data science is essential for this project because it allows us to transform hundreds of unstructured syllabus into clear, quantitative insights. Manual review would be too slow and subjective. Our approach uses three key data science skills:
1. Natural Language Processing (NLP) to Find and Extract Policies
First, we need to turn messy syllabus (from PDFs and Word documents) into clean, workable data. We use NLP to automatically read each document, understand its structure, and precisely pull out the specific sentences that form the AI policy. This is the crucial first step for further demographic analysis and some machine learning analysis.
2. Descriptive Summary Statistics to Analysis Policies
Once we have extracted the AI policy sentences, we use descriptive statistics to summarize how these policies are distributed across the curriculum. This includes calculating the overall percentage of courses that include an AI policy, identifying which departments have higher or lower adoption rates, analyzing how policies are distributed across course levels (under 1,000 level vs. over 1,000 level), and breaking down the proportion of policies classified as “No Use,” “Some Use,” or “Integrated Use.” These statistics provide a clear snapshot of how AI policies are currently implemented before we move on to deeper machine learning analysis.
3. Machine Learning to Understand Policy Content and Tone
Once we have the policy texts, we use machine learning to dig deeper and answer "what do these policies actually say?":
Discovering Themes: We use a technique to automatically group similar policies together. This helps us see the main themes that instructors are focusing on—for example, some policies might be about "preventing cheating" while others are about "using AI as a creative tool."
Analyzing the Tone: We analyze the language to score the overall tone of the policy. This tells us if the message being sent to students is generally warning, neutral, or encouraging.
Categorizing Usage Rules: We train a model to classify each policy into a simple category: “No Use,” “Some Use,” or “Integrated Use.” This gives us a consistent way to count and compare how restrictive or permissive different courses are.
4. Data Visualization 
Our goal is to create a visual story that can be understood at a glance. We will design specific charts and graphs to show:
Policy Adoption: How many AI policies exist and how they are distributed across departments, knowledge areas, and course levels.
Policy Content: The breakdown of different policy types (e.g., 'no use' vs. 'integrated use') and the overall tone of their language.
This approach makes sure that our findings are presented as easy-to-understand and useful information, not just as simple numbers or tables.


## Deliverables
1. A Comprehensive Dataset (Master CSV File)
This will be the foundational data product. It will be a single, clean table where each row represents a course syllabus. The columns will include:
Course demographics (department, knowledge area, academic level).
A flag indicating if an AI policy is present.
The extracted text of the AI policy itself.
The policy's assigned thematic category, sentiment score, and usage level ('no use', 'some use', 'integrated use').
A flag for any AI mentions found outside of the formal policy section.
2. An Analytical Report and Visualizations
This written report will tell the story of the data. It will synthesize our findings and include:
Key summary statistics answering "how many" policies exist, broken down by course demographics.
A detailed analysis of the policy themes, levels, and sentiment, supported by clear charts and graphs (e.g., bar charts, stacked charts, word clouds).
Lists of courses with and without AI policies for internal review.


## Non-Goals
Evaluate the effectiveness of any policy: We are analyzing the text of the policies, not their impact on student learning or academic integrity.
Author or recommend specific policy wording: The project's role is to provide data, not to draft the university's official policy.
Guarantee 100% accuracy in text extraction: OCR and PDF parsing on non-standardized documents may result in minor errors. Our goal is to maximize accuracy and document any limitations.
Analyze information outside the provided syllabus: The analysis is limited to the text within the syllabus documents. We cannot account for verbal instructions given in class or information on course websites.


## Methodology
Data
1. Lance Eaton AI Syllabus Statement archive 
2. Two zip files containing course syllabus from Brown University for the 2023-2024 and 2024-2025 academic years 
3. Brown list of Departments and Centers by Knowledge Area

Tools
Programming Language: Python 3
Data Analysis: We will use foundational libraries such as Pandas to manipulate data, and Scikit-Learn and PyTorch to implement our machine learning models.
Document Processing: The pipeline will incorporate libraries capable of parsing .docx and .pdf files, including those with OCR capabilities.
Visualization: We will use established libraries like Matplotlib and Seaborn to create the charts and graphs for our final report.

Project Management:
Communication: The team will use Zoom for scheduled virtual meetings and email for daily communication.
Coordination: Slack will serve as our central hub for project tracking. Meeting notes and key decisions will also be archived in Slack to ensure transparency and alignment.

## Appendix
Glossary

Syllabus
A document outlining a course’s structure, policies, and expectations
AI Policy
A statement in a syllabus about the permitted or restricted use of AI tools
NLP
Natural Language Processing; computational analysis of human language
Sentiment
The tone or attitude expressed in text (e.g., positive, negative, neutral)
Thematic Analysis
Categorizing text based on recurring themes or topics

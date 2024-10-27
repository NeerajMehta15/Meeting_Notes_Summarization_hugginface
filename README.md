# Meeting_Notes_Summarization_Hugginface

**Project Summary:** Meeting Notes Summarization and Export to Google Sheets
**Project Title**
Automated Meeting Notes Summarization and Google Sheets Integration

**Project Overview**
This project aims to streamline the process of summarizing meeting notes collected from various kitchens within the organization. By utilizing natural language processing (NLP) techniques, particularly the BART summarization model, the project automates the extraction of concise summaries from extensive meeting notes. The summarized notes are then exported to a Google Sheets document for easy access and further analysis.

**Objectives**
Automate Summarization: Develop a systematic approach to summarize lengthy meeting notes into concise summaries.
Facilitate Data Management: Export the summarized notes to a Google Sheets document to enable better tracking and management of kitchen-related information.
Enhance Decision-Making: Provide stakeholders with easily digestible summaries that help in making informed decisions based on past meetings.
Methodology
1. Data Collection
Source: Meeting notes are collected from a Google Sheets worksheet named Meeting_notes.
Data Structure: Each row in the sheet contains details about the kitchen name, house name, and the associated meeting notes.
2. Data Processing
Data Loading: Utilized the gspread library to authenticate and retrieve data from Google Sheets.
Data Preparation: Loaded the meeting notes into a Pandas DataFrame for manipulation. The relevant columns were selected, and meeting notes were grouped by kitchen name.
3. Summarization
NLP Model: Implemented the Hugging Face transformers library to utilize the BART (Bidirectional and Auto-Regressive Transformers) model for summarization. This model is effective for text summarization tasks due to its ability to understand the context and generate coherent summaries.
Chunking: Developed a function to handle long meeting notes by dividing them into manageable chunks. Each chunk is summarized separately to avoid truncation errors due to length limitations of the model.
Final Summary: Combined the summaries from chunks into a final summary, which is then further summarized if it exceeds a defined length.
4. Data Export
Output Destination: Summarized data is prepared for export to a Google Sheets worksheet named Kitchen_summary.
Updating Google Sheets: Utilized the gspread library to append summarized notes into the specified worksheet, ensuring headers are included for clarity.

**Implementation Details**
1. Programming Language: Python
2. Libraries Used:
   i) gspread for Google Sheets interaction.
   ii) pandas for data manipulation.
   iii) transformers from Hugging Face for NLP summarization.



**Key Challenges and Solutions**
Handling Long Texts: The BART model has limitations on input length. Implemented a chunking strategy to break down long meeting notes, ensuring all information is captured in summaries.
Error Handling: Incorporated exception handling to manage potential errors during summarization and Google Sheets updates, ensuring that the process runs smoothly.
Outcomes
Successfully developed an automated system that generates concise summaries of meeting notes for multiple kitchens.
Exported the summarized notes to Google Sheets, providing a valuable resource for stakeholders to review past discussions and decisions easily.
Enhanced the efficiency of information retrieval, contributing to improved decision-making processes within the organization.

**Future Enhancements**
Real-time Summarization: Explore options for real-time summarization during meetings using live transcription services.
User Feedback Mechanism: Implement a feedback mechanism to refine the summarization process based on user inputs and preferences.


**Conclusion**
This project demonstrates the power of automation and NLP in enhancing organizational efficiency. By summarizing meeting notes and exporting them to a centralized location, the initiative contributes significantly to knowledge management and informed decision-making processes.

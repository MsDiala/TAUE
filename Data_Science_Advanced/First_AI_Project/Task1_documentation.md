# Resume Info Extractor

This code is a Python script that extracts information from resumes stored in a CSV file. It utilizes the `pandas` library for data manipulation and the `re` module for regular expression matching. The script contains several functions that extract specific details from the resume text, such as position title, qualifications, education type, school type, education major, experience length, awards, community service involvement, volunteering experience, driver's license availability, skills, and languages.

## Prerequisites

- Python 3.x
- pandas library

## Installation

1. Clone or download the code files to your local machine.
2. Install the required dependencies by running the following command:
   `pip install pandas re`


## Usage

1. Prepare your resumes in a CSV file named "resume_updated.csv". The file should have two columns: "Resume_str" for the resume text and "ID" for the resume identifier.

**Note:** Make sure the CSV file is located in the same directory as the script.

2. Open Jupyter Notebook or any other compatible notebook environment.

3. Open the `Task1_extract.ipynb` notebook file.

4. Run the notebook cells sequentially to execute the code and extract the resume information.

5. The script will process the resumes, extract the necessary information, and save the results to a new CSV file named "extracted_resume_info.csv".

## Functions

The script contains the following functions:

### `extract_position_title(resume_text)`

This function extracts the position title from the given resume text using regular expressions. It searches for a pattern consisting of two consecutive words and returns the matched string. If no match is found, it returns "No info".

### `extract_qualifications(resume_text)`

This function extracts the qualifications or highlights section from the given resume text using regular expressions. It searches for patterns such as "Qualifications:", "Qualification:", "Highlights:", or "Highlight:" followed by any non-digit characters. It returns a list of extracted qualifications or highlights. If no match is found, it returns ["no info"].

### `extract_education_type(resume_text)`

This function determines the highest education type achieved based on the given resume text. It searches for specific patterns associated with different education types such as PhD, Doctor, Master, Bachelor, Diploma, or High School. It returns the identified education type or "No info" if none is found.

### `extract_school_type(resume_text)`

This function extracts the school type (university, college, or high school) from the given resume text. It searches for any of these three keywords and returns the matched string. If no match is found, it returns "No info".

### `extract_education_major(resume_text)`

This function extracts the education major or concentration from the given resume text. It searches for patterns such as "Education Major:", "Education Concentration:", or "Education Degree:" followed by any non-empty characters. It returns a list of extracted education majors. If no match is found, it returns "No info".

### `extract_experience_length(resume_text)`

This function extracts the total years of experience from the given resume text. It searches for patterns matching the format "X years" or "X plus years" where X is a numeric value. It also handles alternative date formats like "MM/YYYY to Current" or "MM/YYYY to MM/YYYY". It returns a list of extracted experience lengths in years.

### `extract_awards(resume_text)`

This function extracts the awards section from the given resume text. It searches for patterns such as "AWARD:", "AWARDS:", "Awarded:", or "Awards:" followed by any non-empty characters. It returns a list of extracted awards. If no match is found, it returns ["no info"].

### `extract_community_service(resume_text)`

This function determines if the given resume text mentions community service or volunteering. It searches for keywords like "community service", "volunteer", or "volunteering" and returns "Yes" if any match is found. Otherwise, it returns "No".

### `extract_volunteering(resume_text)`

This function determines if the given resume text mentions volunteering. It searches for keywords like "volunteer" or "volunteering" and returns "Yes" if any match is found. Otherwise, it returns "No".

### `extract_drivers_license_availability(resume_text)`

This function determines if the given resume text mentions a driver's license or driving license. It searches for keywords like "driver's license" or "driving license" and returns "Yes" if any match is found. Otherwise, it returns "No".

### `extract_skills(resume_text)`

This function extracts the skills section from the given resume text. It searches for the word "Skills" followed by a colon (optional) and any non-digit characters. It returns a list of extracted skills. If no match is found, it returns ["no info"].

### `get_skills_count(skills_text)`

This function calculates the count of skills extracted from the given resume text. It takes the list of skills as input and returns the number of skills. If the skills list is ["no info"], it returns 0.

### `extract_languages(resume_text)`

This function extracts the languages mentioned in the given resume text. It searches for specific languages like English, Spanish, French, German, Mandarin Chinese, Arabic, Russian, Portuguese, Japanese, or Italian. It returns a comma-separated string of languages found. If no match is found, it returns "English".

### `extract_resume_info(resume_text, resume_number)`

This function combines all the extraction functions to extract various resume information. It takes the resume text and resume number as input and returns a dictionary containing the following fields:

- 'POSITION_TITLE': Position title extracted from the resume.
- 'resume number': Resume identifier.
- 'QUALIFICATIONS': Qualifications or highlights extracted from the resume.
- 'EDUCATION_TYPE': Highest education type achieved.
- 'SCHOOL_TYPE': School type (university, college, or high school).
- 'EDUCATION_MAJOR': Education major or concentration.
- 'EXPERIENCE_LENGTH': Total years of experience.
- 'AWARDS': Awards received.
- 'COMMUNITY SERVICE': Community service involvement (Yes/No).
- 'VOLUNTEERING': Volunteering experience (Yes/No).
- 'DRIVERS_LICENSE_AVAILABILITY': Driver's license availability (Yes/No).
- 'SKILLS_COUNT': Count of skills mentioned in the resume.
- 'SKILLS': List of skills extracted from the resume.
- 'Languages': Languages mentioned in the resume.

### `main()`

This function serves as the entry point of the script. It reads the resumes from the CSV file, extracts the resume information using `extract_resume_info()`, creates a DataFrame from the extracted information, and saves it to a new CSV file named "extracted_resume_info.csv".

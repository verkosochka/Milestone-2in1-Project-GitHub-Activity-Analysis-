# Milestone 2in1 Project: GitHub Activity Analysis feat. Python Repositories KPIs Research 
The project consists of two interconnected parts, united by a common structural theme (the analysis of technical and behavioral metrics for measuring the activity of GitHub repositories). However, each sub-project has its own focus, insights, and KPIs, based on which different research methodologies were applied:
1. **GitHub Activity Analysis with Applied Advansed Statistics** (`GitHub-Activity-Analysis-Project.ipynb` + `BigQuery Dataset Implementation.md`).
2. **GitHub Activity Analysis of Python Repositories** ([GitHub Activity of Python Repositories | Tableau Public](https://public.tableau.com/app/profile/veronika.kobets/viz/GitHub_Activity_Python/GitHubActivityofPythonRepositories) + `BigQuery Dataset Implementation.md`).
---
## Table of Contents
1. [Project Overview](#milestone-2in1-project-github-activity-analysis-feat-python-repositories-kpis-research)
2. [Technologies Used](#technologies-used)
3. [Key Features](#key-features)
4. [Data Overview](#data-overview)
5. [Methodology](#methodology)
6. [Key Findings](#key-findings)
---
## Technologies Used 
1. Hard Skillset for **GitHub Activity Analysis with Applied Advansed Statistics**:
	- **`Python` Tools and Packages:**
		- **`Pandas`**: data manipulation, data transformation, data augmentation.
		- **`NumPy`**: numerical operations (using vectors and arrays) and statistical analysis.
		- **`Seaborn & Matplotlib`**: data visualization and creating graphical representations.
		- **`SciPy`**: conducting statistical tests like the Mann-Whitney U tests, Kolmogorov-Smirnov tests, Chi-squared tests, ANOVA, and A/B testing frameworks.
		- **`Statsmodels`**: advanced statistical analysis, including proportions Z-test, power analysis concept.
2. Hard Skillset for **GitHub Activity Analysis of Python Repositories** - Key Insights and KPIs:
	- BI-vizualizations tool - **`Tableau`**:
3. Hard Skillset for Milestone 2in1 Project:
	- Data Implementation and Data Collection:
		- **BigQuery** with Advanced Concepts of SQL-queries:
			- Original DataBase: [BigQuery public dataset  |  Google Cloud](https://cloud.google.com/bigquery/public-data) from Cloud Marketplace: [GitHub Activity Data](https://console.cloud.google.com/marketplace/product/github/github-repos?invt=Abt4TA&authuser=1&project=github-analysis-455609)
			- `BigQuery Dataset Implementation.md` contains queries for both **the full original database** and **the generated dataset (sample)**, which will be used for all subsequent operations such as data cleaning, data aggregation, data augmentation, statistical hypothesis testing, and the development of both static and interactive visualizations. 
			- In the `Python Dataset for BI-systems Visualization` section there is a full guide of dataset construction. 
4. All in all, there is the following project's starterpack: Python (5 libraries), BI-tools for interactive KPIs illustration (Tableau), BigQuery (+ SQL) for data collection and product metrics calculation.
---
## Key Features
The dataset consists of the following columns:

1. **`repo_name`** (STRING, Nullable):
    
    - **Description:** The name of the repository.
        
    - **Example:** `"tensorflow/tensorflow"`, `"microsoft/vscode"`
        
2. **`language`** (STRING, Nullable):
    
    - **Description:** The programming language used in the repository (this can represent the language for a specific file or general project use).
        
    - **Example:** `"Python"`, `"JavaScript"`
        
3. **`language_bytes`** (INTEGER, Nullable):
    
    - **Description:** The total number of bytes of code in the repository that is written in the specified `language`. Represents the size of the code base in terms of bytes.
        
    - **Example:** `250000`, `134500`
        
4. **`license`** (STRING, Nullable):
    
    - **Description:** The license type for the repository, which governs the legal terms for usage and distribution of the code.
        
    - **Example:** `"MIT"`, `"GPL-3.0"`
5. **`total_files`** (INTEGER, Nullable):
    
    - **Description:** The total number of files in the repository.
        
    - **Example:** `150`, `320`
        
6. **`total_commits`** (INTEGER, Nullable):
    
    - **Description:** The total number of commits made to the repository.
        
    - **Example:** `1200`, `8000`    
        
7. **`used_languages`** (INTEGER, Nullable):
    
    - **Description:** The number of distinct programming languages used in the repository.
        
    - **Example:** `2`, `3`
           
8. **`top_language`** (STRING, Nullable):
    
    - **Description:** The primary or most used programming language in the repository.
        
    - **Example:** `"Python"`, `"JavaScript"`
        
9. **`avg_bytes_per_file`** (FLOAT, Nullable):
    
    - **Description:** The average size of files in the repository, calculated as the total size (in bytes) divided by the number of files.
        
    - **Formula:** `avg_bytes_per_file = language_bytes / total_files`
        
    - **Example:** `1700.5`, `420.75`
        
10. **`avg_commits_per_file`** (FLOAT, Nullable):
     
	- **Description:** The average number of commits per file in the repository.
        
	- **Formula:** `avg_commits_per_file = total_commits / total_files`
	     
	- **Example:** `8.5`, `25.3
11. **`commit_intensity_score`** (FLOAT, Nullable):
    
    - **Description:** A measure of commit intensity, calculated as the total number of commits divided by the total bytes of code in the repository. This metric indicates how active a repository is relative to its size.
        
    - **Formula:** `commit_intensity_score = total_commits / language_bytes`
        
    - **Example:** `0.005`, `0.03`
        
12. **`avg_files_per_lang`** (FLOAT, Nullable):
    
    - **Description:** The average number of files per programming language in the repository.
        
    - **Formula:** `avg_files_per_lang = total_files / used_languages`
        
    - **Example:** `75`, `50`
        
13. **`code_density`** (FLOAT, Nullable):
    
    - **Description:** The ratio of the bytes of code written in a specific language to the total bytes of code across all languages in the repository.
        
    - **Formula:** `code_density = language_bytes / SUM(language_bytes) OVER (PARTITION BY repo_name)`
        
    - **Example:** `0.4`, `0.6`
        
14. **`avg_commits_per_lang`** (FLOAT, Nullable):
    
    - **Description:** The average number of commits for each language used in the repository.
        
    - **Formula:** `avg_commits_per_lang = total_commits / used_languages`
        
    - **Example:** `300`, `1000`
---
## Data Overview

All details about dataset implementation are provided in `BigQuery Dataset Implementation.md` with the following **Table of Contents**:

1. GitHub Analysis BigQuery Dataset Implementation.
	-   DataBase `github_repos` dictionary (for used tables only).
		- Fields in the `languages` Table.
		- Fields in the `licenses` Table. 
		- Fields in the `files` Table. 
		- Fields in the `commits` Table.
	- Complete SQL query code for calculating product metrics (performance metrics and user activity analysis on GitHub) based on the original database.
		- Data Structure.
		- Additional Derived Features.
	- Complete SQL query code for filtering each column where the values are not NULL, to create a new consolidated table with 30,000 rows, based on the table generated by SQL query (1).
2. `Python` Dataset for BI-systems Vizualization.
3. Conclusions and Key Points.

GitHub stands as the leading platform for collaborative software development and version control, hosting the largest global community of open-source developers. Since its launch in 2008, over 12 million developers have contributed to more than 31 million projects, positioning GitHub as a key hub for innovation, code sharing, and community-driven software development.

This dataset, which exceeds 3 terabytes in size, represents the most extensive public archive of GitHub activity available today. It captures a comprehensive snapshot of over 2.8 million open-source repositories, including over 145 million unique commits, more than 2 billion file paths, and the full content of the latest revisions for 163 million files. These data points are searchable through regular expressions, allowing for detailed analysis.

You can download the GitHub-Activity-Analysis dataset with the following link:
- .csv: [GitHub Activity Dataset](https://drive.google.com/file/d/17G7a_cQI1d5Yd_PtU0ur56ZUBuAUV9ml/view?usp=drive_link) 
- .xlsx: [GitHub Activity Dataset]( https://docs.google.com/spreadsheets/d/1qB4dKAOOidrfsKoSoPHqWu_CMnF-uT3X/edit?usp=drive_link&ouid=102100486137110097760&rtpof=true&sd=true)

You can download the Python-Activity-Analysis dataset with the following link:
- .csv: [Google Drive - Python Activity Dataset](https://drive.google.com/file/d/1JyxWKULUc44hSTPLwnX5UyrUofxs8QfZ/view?usp=sharing) 
- .xlsx: [Google Drive - Python Activity Dataset](https://drive.google.com/file/d/1J5yCuDyzfTDATZpu8aNNFykBAAhCSfty/view?usp=drive_link)
---
## Methodology 

### GitHub Activity Analysis with Applied Advansed Statistics (`GitHub-Activity-Analysis-Project.ipynb` + `BigQuery Dataset Implementation.md`)

1. **Repository Classification by License Type.**
  Repositories are categorized based on their license type (including both open-source and proprietary) using selected parametric features:
	- 1.1. Average number of commits.
	- 1.2. Average file size.
	- 1.3. Commit intensity.
	- 1.4. Code density (lines of code per file or per repository).
2. **Code Density Analysis Across License Types.**
	A Mann-Whitney U Test is applied to compare the mean code density between open-source and licensed (non-open-source) repositories. This statistical test aims to evaluate whether the observed difference in code density is statistically significant with respect to license classification.
3. **Repository Categorization by Language Usage.**
	  Projects are classified based on the number of programming languages used: (monolingual, bilingual, trilingual, multilingual).
	- 3.1. A detailed analysis of the statistical distribution of multilingual repositories is performed using descriptive statistics, Q-Q plots, and the Kolmogorov-Smirnov test to assess distribution type and normality.
	- 3.2. A brief exploration of whether the distribution follows a power-law behavior is included.
4. **Language Dominance Analysis.**
	- 4.1. Identification of the top 5 dominant programming languages across unique repositories.
	- 4.2. Correlation analysis between dominant language and overall repository activity.
	- 4.3. A/B test experiment design: _"From Python to Java"_ — based on commit intensity score, including an outline of data requirements and implementation considerations.
	- 4.4. Chi-squared test for independence between two categorical variables: license type (open-source vs non-open-source) and language usage category (monolingual, bilingual, trilingual, multilingual).
5. **ANOVA: Language Diversity vs Code Density.**
	Analysis of Variance (ANOVA) is employed to test whether the average code density significantly differs across projects grouped by language usage categories.
6. **Mean Activity Level per Top-10 Programming Languages.**
	Calculation and comparison of the average repository activity levels for the top 10 most commonly used languages, based on the number of repositories in the dataset.
---
### GitHub Activity Analysis of Python Repositories - Key Insights and KPIs ([GitHub Activity of Python Repositories | Tableau Public](https://public.tableau.com/app/profile/veronika.kobets/viz/GitHub_Activity_Python/GitHubActivityofPythonRepositories) + `BigQuery Dataset Implementation.md`)

1. Language Category Distribution, %.
	- Pie Chart.
2. License Type Distribution, %.
	- Pie Chart.
3. KPI: CD and CIS.
	- Activity Metrics: Code Density and Commit Intensity Score.
4. KPI: ATC.
	- Average Total Commits.
5. KPI: ACF - File Touches with Status (Active|Low).
	- Average Commits per File | Status.
6. KPIs for ASM per File and Language, categorized by License Type.
	- Average Software Metrics for Python Repos.

Dashboard with illustrated KPIs and Insights: 
- [GitHub Activity of Python Repositories | Tableau Public](https://public.tableau.com/app/profile/veronika.kobets/viz/GitHub_Activity_Python/GitHubActivityofPythonRepositories)
---
## Key Findings

1.  **Large Variability in Repository Sizes.**
	- Some repositories are very small, with only one file, while others contain millions of bytes of code and thousands of files. This suggests a significant difference in the scope and complexity of projects.
2. **Outliers in Commits.**
	- Some repositories have an extremely high number of commits compared to others, indicating that they might be highly collaborative or continuously developed over long periods. These outliers could be major open-source projects like web frameworks or libraries.
3. **Multi-language Repositories.**
	- The average number of languages per repository is **4.8**, but some repositories use more than 100 languages. This could suggest the presence of non-code files (like documentation or configuration files) in the codebase.
4. **Commit Activity and File Size Correlation.**
	- Larger codebases and more files seem to be correlated with more commits. However, repositories with a large number of commits may also show smaller file sizes on average, indicating that frequent commits could be smaller, incremental updates.
5. **File Size and Commit Intensity.**
	- Repositories with large files tend to have lower commit intensity. This suggests that smaller, more frequent updates are typical for files with a smaller size, while larger files might receive fewer, more substantial changes, but we should take a considiration on used languages and the field of development.
6. **Repository Growth Potential.**
	- Projects with a larger number of commits, larger file sizes, and high code density could indicate well-established repositories with long-term contributions. Conversely, repositories with fewer commits and smaller codebases could be newer or less actively developed.
7. **Language Dominance.**
	- By analyzing the `code_density` and `avg_files_per_lang columns`, it’s clear that some languages dominate specific repositories. This could point to repositories that are focused on a single technology stack, while others might have multiple languages supporting various tasks (e.g., a repository containing both Python code for backend development and JavaScript for frontend development).
8. **Active Open-Source Projects.**
	- Repositories under **MIT** are highly active and have larger file sizes, which could indicate popular open-source projects such as frameworks, tools, and libraries being actively worked on by a wide user base.
9. **Community Engagement.**
	- **MIT**-licensed projects appear to have the most commits, suggesting that permissive licenses are often chosen for community-driven, high-engagement projects. This is particularly important for **Open Source Contributors** and **Start-Up Founders** seeking to create projects that attract broad collaboration.
10. **Repository Growth and Development.**
	- **GPL-3.0** and **Apache-2.0** licenses show a good balance between file size, code density, and commit intensity. Projects under these licenses may have a more controlled growth, focusing on structured development processes, making them suitable for **DevOps Engineers** and **Software Engineers** aiming for reliable, scalable systems.
11. **Complexity of Projects.**
	- **GPL-3.0**-licensed repositories show higher code density, which may suggest they are more focused on core code, as opposed to **MIT** repositories that may contain more diverse file types (documentation, configuration files). This can be useful for **Programming Language Designers** and **Maintainers** who want to understand how to optimize code and related files in their own repositories.
12. **Minimalist Projects.**
	- Repositories with **Unlicense** have low commit intensity and small file sizes, suggesting they may be minimal or experimental repositories. **Tech Policy Makers** may want to observe how such repositories develop in terms of codebase growth and legal ramifications when using public domain licenses like **Unlicense**.
13. The difference in the average code density (`code_density`) between open-source and non-open-source repositories (`license_type`) is statistically significant, indicating that the code density of non-open-source repositories is higher than that of open-source repositories.
14. The largest share among all repositories based on the `lang_category` characteristic is held by multilingual repositories (>4 languages), accounting for 46.44%, which is 2.3 times larger than the second-ranking category (trilingual).
15. Multilingual repositories, according to the `used_languages` metric, follow a power law distribution.
16. **Top 5 of dominant languages of the dataset repositories** are JavaScript, Python, C, PHP and Java.
17. The analysis suggests that **repository activity** is strongly correlated with **commit intensity**, meaning that repositories with more commits generally exhibit higher levels of activity. This is important for understanding how frequently repositories are updated and the overall development momentum.
18. The positive relationship between **file size** and **commits per language** indicates that larger repositories tend to have more languages and more commits per language. This suggests that multi-language repositories are often more complex, requiring updates and maintenance across different parts of the codebase, and typically show higher activity levels.
19. The weak negative correlation between **code density** and **commit intensity** suggests that commit intensity is not always driven by the amount of code. Some repositories might have more frequent, but smaller updates without significantly increasing the overall codebase, which points to incremental changes rather than large code updates.
20. The relationship between **files** and **languages** highlights the significance of multilingual repositories in driving development activity. This suggests that repositories with multiple languages tend to be larger and involve higher development efforts, which is crucial for understanding the dynamics of complex software projects.
21. **The transition (switching) from Python to Java does affect the commit intensity score of repositories**. This may be the result of the development of new libraries, frameworks, or the increased popularity of these languages for specific tasks.
22. **There is a dependency between the license type (open source and non-open source) and the language usage category (monolingual, bilingual, trilingual, multilingual)**.
23. There is a statistically significant difference in code density between language categories.
24. High code density in duolingual repositories.
25. **Trilingual repositories show a similar**, but _slightly lower_, median code density. This could suggest that with three languages, repositories might be slightly more complex but still focused on a core set of functionalities.
26. **Monolingual repositories**, despite being focused on a single language, **tend to have lower code density**. **Multilingual repositories also show a lower median**, suggesting that the inclusion of multiple languages or greater complexity leads to a less dense core codebase.
27. The distribution **Top-10 Programming Languages** (by `total_commits`) of provides a foundation for clustering projects based on their profiles according to the languages used. For example, Python + R = Data Analysis feat. Data Science, JavaScript + CSS + HTML = Frontend, Solidity = Smart Contracts and Blockchain, etc.

Furthermore, for each point in the methodology, a set of recommendations has been developed for the target audience of the analytical project and IT stakeholders. To discover this detailed information, as well as to determine if you are part of the market for which these insights are incredibly useful and valuable in your work to maintain leadership positions in your field, be sure to check out the full project report!

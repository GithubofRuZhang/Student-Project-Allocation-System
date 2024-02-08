# Student Project Allocation System

## Project Overview

This project utilizes an improved Gale-Shapley algorithm to address the matching issue between students and projects, aiming to achieve a fair and stable allocation system. By considering the preferences of both students towards projects and the capacity of each project to accommodate students, the system is able to assign each student to a suitable project, thereby optimizing student satisfaction and project talent allocation.

## Features

- **Fairness**: Ensures that all students are allocated to projects as fairly as possible according to their preferences.
- **Stability**: The final matching results are stable, with no student or project preferring each other over their current allocation.
- **Optimized Gale-Shapley Algorithm**: Through algorithm optimization, the efficiency and satisfaction of matching are improved.

## Requirements

- A Google account to access Google Colab.
- Internet connection.

## How to View and Run in Google Colab

1. **Access the Notebook**: Click on the link provided in the repository to open the Colab notebook. If a direct link is not provided, you can save the `.ipynb` file to your Google Drive and open it with Google Colab.

2. **Run the Notebook**: Once the notebook is open in Colab, you can run the cells sequentially by clicking on the play button next to each cell or by using the shortcut `Ctrl + Enter` (or `Cmd + Enter` on Mac).

3. **View the Results**: The output of each cell will be displayed directly below the cell after execution. This includes the final project allocations and any print statements or visualizations included in the notebook.

## Pseudocode Description

The following pseudocode outlines the process of matching students to projects using an improved Gale-Shapley algorithm:

1. **Set a random seed for reproducibility.**

2. **Initialize parameters:**
   - Number of students: 50
   - Number of projects: 10
   - Students per project: Calculate by dividing the number of students by the number of projects
   - Options per student: 5

3. **Generate students' preference lists:**
   - For each student, randomly generate a list of 5 preferred projects.

4. **Initialize projects' capacity:**
   - Each project has a certain number of slots to accommodate students.

5. **Define the optimized Gale-Shapley algorithm function:**
   - Initialize project allocations and remaining capacities.
   - Attempt to allocate students to their top three choices.
   - Record and print the time taken for allocation.

6. **Define a function to finalize allocations:**
   - For unallocated students, try to assign them to projects based on their preferences until all students are allocated.

7. **Execute the optimized Gale-Shapley function for preliminary student-to-project allocation.**

8. **Execute the function to finalize allocations, ensuring all students are allocated and preferences are considered as much as possible.**

9. **Print the final project allocations:**
   - For each project, list the allocated students and their top three preferences.

## Contribution Guide

We welcome all forms of contributions, including but not limited to suggestions for new features, code optimization, documentation improvements, or issue reporting. Please submit your contributions via GitHub's Issue and Pull Request mechanisms.

## License Information

This project is licensed under the MIT License. For more details, please refer to the `LICENSE` file.

## 📌 Two-Stage Optimization Algorithm (Team Allocation with Top-3 Guarantee)

### 🎯 Objective
To allocate students to projects such that as many students as possible receive one of their **top-3 preferences**, while also maximizing the overall satisfaction score.

---

### 📝 Algorithm Design

#### Stage 1: Maximize Top-3 Coverage
- **Decision variables**
  - \(x_{s,p} \in \{0,1\}\): whether student \(s\) is assigned to project \(p\).  
  - \(y_s \in \{0,1\}\): whether student \(s\) is assigned to one of their top-3 choices.  

- **Constraints**
  1. Each student is assigned to exactly one project:  
     $$
     \sum_{p} x_{s,p} = 1 \quad \forall s
     $$
  2. Each project must satisfy capacity bounds:  
     $$
     L_p \leq \sum_{s} x_{s,p} \leq U_p \quad \forall p
     $$
  3. Linking variable \(y_s\) to top-3 preferences:  
     $$
     y_s \leq \sum_{p \in \text{Top3}(s)} x_{s,p} \quad \forall s
     $$

- **Objective function**  
  Maximize the number of students assigned within their top-3 choices:  
  $$
  \max \sum_s y_s
  $$

---

#### Stage 2: Maximize Satisfaction under Top-3 Guarantee
- **Carry-over constraint from Stage 1**  
  Ensure at least \(\text{max\_top3}\) students are in top-3 choices:  
  $$
  \sum_s y_s \geq \text{max\_top3}
  $$

- **Satisfaction scores**
  - 1st choice: 5 points  
  - 2nd choice: 4 points  
  - 3rd choice: 3 points  
  - 4th choice: 2 points  
  - 5th choice: 1 point  

- **Objective function**  
  Maximize the total satisfaction score:  
  $$
  \max \sum_{s,p} \text{score}(s,p) \cdot x_{s,p}
  $$

---

### 🌟 Advantages
1. **Fairness**: maximizes the number of students receiving top-3 choices.  
2. **Satisfaction**: further improves overall allocation quality after fairness.  
3. **Flexibility**: project capacity bounds can be tuned.  
4. **Transparency**: results include *Preference Rank* and *Top3 (Yes/No)* labels.

---

### 📊 Output
The final results table contains:
- Student ID  
- First Name, Last Name  
- Email  
- Assigned Project  
- Preference Rank (which choice)  
- Top3 (Yes/No)  
- Additional fields: Educational Background, Major, Minor, etc.  


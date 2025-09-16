# Optimal Project Allocation System / 最优项目分配系统

This repository provides algorithms for allocating students to projects under capacity and preference constraints.
It was originally developed for the **MGT-555 course at EPFL** to assign students to industry-sponsored projects in a fair, efficient, and transparent way.

本仓库提供了一套学生–项目分配算法，考虑了项目容量和学生偏好限制。
该系统最初为 **EPFL MGT-555 课程**开发，用于在公平、高效、透明的原则下将学生分配到企业合作项目。

---

## ✨ Features / 功能特点

We provide **two generations** of algorithms:
本项目包含 **两个阶段的算法版本**：

### 📌 Original Algorithms (Report Version, 2024-08-31)

原始算法（报告版，2024-08-31）：

1. **Greedy Allocation / 贪心分配**

   * Fast and simple / 简单快速。
   * Assigns students iteratively based on highest remaining preference / 按剩余最高偏好逐步分配。
   * Does not guarantee stability or global fairness / 不保证稳定性或整体公平性。

2. **Stable Matching (Gale–Shapley) / 稳定匹配算法（GS）**

   * Ensures stability (no blocking pairs) / 保证稳定性（无阻塞对）。
   * Widely used in matching markets (e.g., residency matching) / 常用于匹配市场（如医学生住院分配）。
   * May not maximize the number of students assigned to their top-3 choices / 未必能最大化进入前三志愿的学生比例。

3. **Score-Based Allocation / 基于打分的分配**

   * Assigns numerical scores to preferences / 将志愿转化为数值评分。
   * Maximizes the sum of scores subject to capacity constraints / 在容量约束下最大化总得分。
   * Flexible but computationally heavier / 灵活，但计算量较大。

---

### 📌 Upgraded Algorithm (Two-Stage Optimization, 2025 Version)

升级算法（二阶段优化，2025 版本）：

* **Stage 1 / 阶段一:** Maximize the number of students assigned to one of their **Top-3 preferences**
  最大化进入 **前三志愿** 的学生数量（公平性保证）。

* **Stage 2 / 阶段二:** Within that solution set, maximize the **overall satisfaction score**
  在阶段一的解集上，进一步最大化 **整体满意度得分**（按志愿顺序加权）。

**Advantages / 优势:**

* Balances **fairness** (Top-3 coverage) and **satisfaction** (rank quality)
  同时兼顾 **公平性**（前三覆盖率）与 **满意度**（志愿质量）。
* Transparent optimization process / 优化过程透明。
* Outputs detailed results / 输出包含：

  * Student ID / 学号
  * Assigned Project / 分配项目
  * Preference Rank / 志愿顺序
  * Top-3 (Yes/No) / 是否进入前三志愿

---

## ⚖️ Comparison / 算法比较

| Algorithm / 算法         | Stability / 稳定性 | Fairness (Top-3) / 公平性 (前三) | Satisfaction / 满意度 | Complexity / 复杂度 |
| ---------------------- | --------------- | --------------------------- | ------------------ | ---------------- |
| Greedy Allocation      | ❌               | Medium / 中等                 | Medium / 中等        | Low / 低          |
| Stable Matching (GS)   | ✅               | Medium / 中等                 | Medium–High / 中–高  | Low–Medium / 中低  |
| Score-Based Allocation | ❌               | High / 高                    | High / 高           | Medium–High / 中高 |
| Two-Stage Optimization | ✅ (soft / 弱)    | **High / 高**                | **High / 高**       | High / 高         |

---

## 📊 Outputs / 输出结果

* Excel/CSV file listing assignments with preference ranks.
  输出包含学生分配及志愿顺序的 Excel/CSV 文件。
* Summary statistics on fairness and satisfaction.
  提供公平性和满意度的汇总统计。

---

## 📌 Usage / 使用方法

```bash
# Install dependencies / 安装依赖
pip install pulp pandas numpy

# Run the two-stage optimization / 运行二阶段优化
python two_stage_allocation.py input.xlsx
```

---
## 📝 License / 许可证

This project is licensed under the MIT License 
本项目采用 MIT 许可证

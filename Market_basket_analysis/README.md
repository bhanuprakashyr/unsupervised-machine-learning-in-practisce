# 📊 Association Rules: Support, Confidence, and Lift

## 1. Support
- **Definition**: How frequently an item or itemset appears in the dataset.  
- **Formula**:  
  \[
  \text{Support}(A) = \frac{\text{Number of transactions containing A}}{\text{Total transactions}}
  \]  
- **Example**: If 200 out of 1000 baskets contain milk, support(milk) = 0.2.

---

## 2. Confidence
- **Definition**: Probability of seeing item B in a transaction given that it already contains item A.  
- **Formula**:  
  \[
  \text{Confidence}(A \Rightarrow B) = \frac{\text{Support}(A \cup B)}{\text{Support}(A)}
  \]  
- **Example**: If 50 baskets have {milk,bread} and 200 baskets have milk,  
  confidence(milk ⇒ bread) = 50 / 200 = 0.25.

---

## 3. Lift
- **Definition**: How much more likely two items are to be bought together compared to being independent.  
- **Formula**:  
  \[
  \text{Lift}(A \Rightarrow B) = \frac{\text{Confidence}(A \Rightarrow B)}{\text{Support}(B)}
  \]  
- **Interpretation**:  
  - **Lift > 1** → Positive association (A increases likelihood of B).  
  - **Lift = 1** → Independent (no effect).  
  - **Lift < 1** → Negative association (A reduces likelihood of B).  

- **Use**: Rank/filter top rules by lift. Higher lift = stronger association.  

---

✅ **Summary**:  
- **Support** = frequency.  
- **Confidence** = conditional probability.  
- **Lift** = strength of association compared to independence.  

## 4. Apriori Algorithm Overview

- **Purpose**: The Apriori algorithm is used for mining frequent itemsets and learning association rules. It’s a foundational algorithm in market basket analysis.

- **Key Idea**: An itemset is considered frequent only if all of its subsets are also frequent. In other words, if a combination of items is going to be deemed "popular," then every individual item and every subset of that combination must also meet the minimum support threshold.

- **Steps**:
  1. **Find frequent 1-itemsets**: Identify individual items that meet the minimum support.
  2. **Generate candidate itemsets**: Create combinations of items from the frequent itemsets found in the previous step.
  3. **Prune**: Remove candidate itemsets if any of their subsets are not frequent.
  4. **Repeat**: Continue the process iteratively, increasing the size of itemsets until no more frequent itemsets are found.

- **Output**: A set of frequent itemsets and the association rules (with support, confidence, and lift) that can be derived from them.

---


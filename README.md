<h1>Loan Eligibility Prediction Using Logistic Regression</h1> 
 <p>This project presents a full machine learning pipeline designed to predict <strong>loan eligibility</strong> based on demographic and financial information. Built using Python and Scikit-learn, the model is intended to help banks and financial institutions make faster, fairer, and data-driven loan approval decisions.</p>

  <h2> Business Objective</h2>
  <p>To predict whether a loan application should be approved (<strong>Loan_Status</strong>) based on applicant information — helping lenders reduce manual screening time and increase approval consistency.</p>

  <h2> Machine Learning Workflow</h2>

  <h3>1. Problem Framing</h3>
  <ul>
    <li><strong>Type</strong>: Binary classification</li>
    <li><strong>Target Variable</strong>: <code>Loan_Status</code> (Yes/No)</li>
    <li><strong>Key Challenge</strong>: Balancing model accuracy with interpretability in a financial decision-making setting</li>
  </ul>
  <h3>2. Data Preprocessing</h3>
  <ul>
    <li><strong>Missing Values</strong>: 
      <ul>
        <li>Imputed <code>Gender</code>, <code>Married</code>, <code>Dependents</code>, and <code>Self_Employed</code> using <strong>mode</strong></li>
        <li>Imputed <code>LoanAmount</code> using <strong>median</strong></li>
      </ul>
    </li>
    <li><strong>Encoding</strong>: Used <code>LabelEncoder</code> to convert categorical variables to numeric values</li>
    <li><strong>Feature Engineering</strong>:
      <ul>
        <li><code>Total_Income = ApplicantIncome + CoapplicantIncome</code></li>
        <li><code>Income_per_loan = Total_Income / LoanAmount</code></li>
      </ul>
    </li>
    <li><strong>Scaling</strong>: Applied Min-Max Scaling to normalize income-related features</li>
  </ul>
  <h3>3. Model Used: Logistic Regression</h3>
  <p><strong>Why Logistic Regression?</strong></p>
  <ul>
    <li>Well-suited for binary outcomes</li>
    <li>Fast and efficient on structured/tabular data</li>
    <li>Easy to interpret and explain to business stakeholders</li>
  </ul>

  <h3>4. Training Process</h3>
  <ul>
    <li><strong>Train/Test Split</strong>: 80% training / 20% testing</li>
    <table border="1">
    <tr>
      <th>Metric</th>
      <th>Value</th>
    </tr>
    <tr>
      <td>Accuracy</td>
      <td>81.5%</td>
    </tr>
    <tr>
      <td>Precision</td>
      <td>86%</td>
    </tr>
    <tr>
      <td>Recall</td>
      <td>91%</td>
    </tr>
    <tr>
      <td>F1-Score</td>
      <td>88.4%</td>
    </tr>
  </table>

  <h3> Confusion Matrix:</h3>
  <pre>
  [[21  6]
   [ 3 44]]
  </pre>
  <ul>
    <li><strong>True Positives (44)</strong>: Approved loans correctly predicted</li>
    <li><strong>True Negatives (21)</strong>: Rejected loans correctly predicted</li>
    <li><strong>False Positives (6)</strong>: Predicted as approved, actually rejected</li>
    <li><strong>False Negatives (3)</strong>: Predicted as rejected, actually approved</li>
  </ul>

  <h3>Key Insights:</h3>
  <ul>
    <li><code>Credit_History</code> is the single most predictive feature.</li>
    <li>Applicants with higher <code>Total_Income</code> and a history of timely payments were more likely to be approved.</li>
    <li>The model generalizes well with a low false-negative rate, which is critical in loan risk management.</li>
  </ul>

  <h2>Data & Visual Insights</h2>
  <ul>
    <li><strong>Heatmap</strong>: Showed low multicollinearity between engineered features</li>
    <li><strong>Bar Charts</strong>: Visualized credit history and property area distributions</li>
    <li><strong>Boxplots</strong>: Revealed how income and education level correlate with loan approval</li>
  </ul>

  <h2> Tools & Technologies</h2>
  <ul>
    <li><strong>Language</strong>: Python</li>
    <li><strong>Libraries</strong>:
      <ul>
        <li><code>pandas</code>, <code>numpy</code> for data wrangling</li>
        <li><code>matplotlib</code>, <code>seaborn</code> for EDA</li>
        <li><code>scikit-learn</code> for modeling and evaluation</li>
      </ul>
    </li>
    <li><strong>IDE</strong>: Jupyter Notebook</li>
  </ul>
    <li><strong>Model</strong>: <code>LogisticRegression()</code> from <code>sklearn.linear_model</code></li>
    <li><strong>Fit</strong>: Trained on the full feature set, including engineered features</li>
  </ul>

  

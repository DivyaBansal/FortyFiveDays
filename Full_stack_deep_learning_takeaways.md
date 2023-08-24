> Rule of thumb: Start simple, add complexity later

# Modelling:
1. Make it run: no erros
2. Make it fast: profilling, remove bottlenecks, change precision (16-bit) etc.
3. Make it right: scale model/data sticking with proven architectures

Overfitting? scale data  
Underfitting? scale model  
Distributional Shift? scale data and model

# Model Testing:  

Smoke Testing:
- Expectation tests for checking data quality issues
- Memorization tests for training (overfit batches)
- Regression tests for models, for finding data points with highest loss/gradient changes i.e.e to identify hard test suites etc.

Expectation tests/data quality tests like:
- Accuracy
- Completeness
- Consistency
- Timelines
- Validity/Conformity
- Integrity

# Deployment:
- Prototype: Simple app with gradle/streamlit UI  
- Model-in-server  
- Model-in-DB
- Model-as-a-service
- REST API/flask/separation of concerns (e.g. UI, model, DB etc.)

# Caching and Batching:
- examples:  
  cache model outputs or users to lower latency  
  batch users and make a forward pass in parallel  

> Keep limitations of target device in mind (in case of edge deployment)
> Have fallback mechanisms in place

# Continual Learning:
Adjust to data distribution shift

## Retraining Cycle:
1. Logging - which data to store, where, how to process?
2. Curation - what data to prioritize for labeling & potential retraining?
3. Retraining trigger - when to retrain?
4. Dataset formation - what specific data to train on?
5. Training
6. Offline Testing - what does "good enough" look like for all stakeholders?
7. Deployment/online testing
8. If everything looks good, rollout chenged model fully
9. Repeat from the top

> Overall tune the strategy by monitoring metrics

## Retraining strategies:
1. Ad-hoc
2. Periodic

> This may fail/be insufficient in the following cases:
> 1. high volume and you need to choose a subset to retrain
> 2. there are missing important representative data points that need to be present in every training set 
> 3. in human-in-the-loop settings where labeling is too expensive, you need custom labeling rules
> 4. retraining is costly
> 5. data is rapidly evolving
> 6. high cost of bad predictions

Most valuable signals to monitor (Descending order):
1. Outcomes and feedback from users
2. Model performance metrics
3. Proxy metrics (correlated with bad model performance: repetitive outputs, toxic outputs etc.)
4. Data quality
5. Distribution drift
6. System metrics
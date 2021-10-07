## AI and ML

AI is the set of tools for making computer behave intelligently. ML is most prevelant subset of AI.

## Supervised learning
kNN

```
# Load the 'class' package
library(class)

# Create a vector of labels
sign_types <- signs$sign_type

# Classify the next sign observed
knn(train = signs[-1], test = next_sign, cl = sign_types)
```

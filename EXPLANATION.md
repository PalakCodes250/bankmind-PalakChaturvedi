# EXPLANATION.md — Track B (ML Engineer)

### 1. What percentage of customers in your dataset have `y = yes`? What does this imbalance mean for how you'd evaluate a model?

Only about 11.7% of customers said yes, the rest (88.3%) said no. This means the data is pretty imbalanced. If I just check accuracy, a model that predicts "no" every single time would still get like 88% accuracy, but it would be useless since it never actually finds a real lead. So I can't just trust accuracy here, I need to check precision/recall/F1 for the "yes" class specifically to see if the model is actually doing its job.

### 2. Which job category had the highest subscription rate? Does this make sense to you intuitively?

Students and retired people had the highest subscription rates. Yeah it makes sense to me, they probably have more free time to actually listen to the call and consider it, and might want a safe way to save/grow money since they're not super busy with work stuff like a full time employee would be.

### 3. Which feature had the highest importance in your tree-based model? Why do you think that is?

`duration` (how long the call lasted) was by far the most important feature, way ahead of everything else. Makes sense, if someone stays on the call longer they're probably actually interested, vs someone who just says no and hangs up fast. One issue though, you only know the duration after the call already happened, so it's not really useful for deciding who to call in the first place. Good to know but kind of a flaw if this was used in real life.

### 4. Why is F1 a better metric than accuracy for this particular dataset?

Because the data is imbalanced (88% no, 12% yes), accuracy can look fine even if the model is bad at finding the actual "yes" customers. F1 combines precision and recall so it actually punishes the model if it's missing real subscribers or giving too many wrong "yes" predictions. So F1 tells you the real story better than accuracy does here.

### 5. Pick one of your 5 sample predictions. Do you actually agree with the model's call, given that customer's features?

I picked the 32 year old, works in management, single, tertiary education, balance of €1,619, no housing loan, no personal loan. Model predicted "yes" with 0.856 probability. I agree with it. No loans means more free money, decent balance means they're not broke, and being single with a stable job means less stuff pulling at their finances (no mortgage, no kids etc). So they've got room to actually say yes to something like this. Feels like a solid lead.

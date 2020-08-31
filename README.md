# nocode-ml

Package for `#nocode` machine learning. Supported in all `#nocode` programming languages.

**10 easy steps**:  
1. [Install this package](#1-install-this-package-via-the-command-below-then-click-here)  
2. [Define business problem & objective](#2-define-your-business-problem-and-objective-then-click-here)  
3. [Provide clean data](#3-provide-your-pristine-data-then-click-here)  
4. [Define offline validation approach](#4-set-offline-validation-approach-and-metrics-then-click-here)  
5. [Train the model (one-click)](#5-train-the-machine-learning-model-via-one-click)  
6. [Validate the model offline](#6-validate-the-model-offline-then-click-here)  
7. [Deploy the model (one-click)](#7-deploy-the-ml-model-via-one-click)  
8. [Validate the model online](#8-validate-the-model-online-ie-ab-testing-then-click-here)  
9. [Share the results](#9-share-the-results-then-click-here)  
10. [Maintain the model](#10-maintain-the-model)   

## Quick Start

### 1. Install this package via the command below. Then, click [here](#2-define-your-business-problem-and-objective-then-click-here).
```

```

### 2. Define your business problem and objective. Then, click [here](#3-provide-your-pristine-data-then-click-here).
- Get buy-in from all stakeholders ~~involved~~, including their pet 🐶/🐱/🐔/🌵.   
- (Note: There ~~might~~ will be conflicting objectives. E.g., customer experience wants to remove counterfeit/low-quality products (to protect customers) but commercial refuses as they _think_ it'll reduce revenue.)
- It's okay if you don't have the problem defined. Let's train some ML first and figure it out later. 
- It's okay if you don't have the objective defined. You can decide after viewing the A/B test results.  
- (Optional) Decide how your ML model will benefit customers. Will it (i) be integrated into an existing system, (ii) need a new UI, (iii) augment decision-making, (iv) something else?

### 3. Provide your pristine data. Then, click [here](#4-set-offline-validation-approach-and-metrics-then-click-here).
- Upload your data as a single denormalized `csv`; file size should not exceed 1gb.  
- Data should not have missing values. Decide whether to exclude at row or column level, impute via statistics (e.g., median, mode), machine learning, or a specified null value (e.g., `NA`, `-1`).  
- **For string values**: `ASCII` encoded, lowercased, spellchecked & normalized (see "60 ways to spell Philidelphia" below), [naughty words](https://github.com/LDNOOBW/List-of-Dirty-Naughty-Obscene-and-Otherwise-Bad-Words) removed.  
- **For numerics**: Parsed correctly (e.g., `"$1.00"`, `"USD1.00"`, `"0.85 €"` should all be `1.0`), exclude errors (e.g., age > 200) and possibly outliers.  
- **For date**: Formatted based on [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601). 
- **For human genes**: Formatted based on [industry best practice](https://www.theverge.com/2020/8/6/21355674/human-genes-rename-microsoft-excel-misreading-dates).
- (Optional) Remove redundant columns (e.g., only a single value, >95% missing values, low variance, etc.)
- (Optional) Remove redundant rows (e.g., exact duplicates, >95% missing values, etc.)  

<details><summary>60 ways to spell "Philidelphia"</summary>
<pre><code><span class="n">PHAILLIDELPPHA</span>  
<span class="n">PHIADELPHIA</span>  
<span class="n">PHIALDELPHIA</span>  
<span class="n">PHIDAELPHIA</span>  
<span class="n">PHIELADELPHIA</span>  
<span class="n">PHIILADELPHIA</span>  
<span class="n">PHILA</span>  
<span class="n">PHILA</span><span class="o">.</span>  
<span class="n">PHILAD</span>  
<span class="n">PHILADALPHIA</span>  
<span class="n">PHILADEDLPHIA</span>  
<span class="n">PHILADELAPHIA</span>  
<span class="n">PHILADELELPHIA</span>  
<span class="n">PHILADELHIA</span>  
<span class="n">PHILADELHIPHILADELHPIA</span>  
<span class="n">PHILADELHPIA</span>  
<span class="n">PHILADELOHIA</span>  
<span class="n">PHILADELPH</span>  
<span class="n">PHILADELPHA</span>  
<span class="n">PHILADELPHAI</span>  
<span class="n">PHILADELPHI</span>  
<span class="n">PHILADELPHIA</span>  
<span class="n">PHILADELPHIA</span> <span class="n">PA</span>  
<span class="n">PHILADELPHIA,</span>  
<span class="n">PHILADELPHIA, PA</span>  
<span class="n">PHILADELPHIA</span><span class="o">.</span>  
<span class="n">PHILADELPHIAPHIA</span>  
<span class="n">PHILADELPHIOA</span>  
<span class="n">PHILADELPHIOE</span>  
<span class="n">PHILADELPIA</span>  
<span class="n">PHILADELPOHIA</span>  
<span class="n">PHILADELPPHIA</span>  
<span class="n">PHILADEPHA</span>  
<span class="n">PHILADEPHIA</span>  
<span class="n">PHILADEPHILA</span>  
<span class="n">PHILADEPLHIA</span>  
<span class="n">PHILADLEPHIA</span>  
<span class="n">PHILADPHIA</span>  
<span class="n">PHILAELPHIA</span>  
<span class="n">PHILDADELPHIA</span>  
<span class="n">PHILDADLPHIA</span>  
<span class="n">PHILDEALPHIA</span>  
<span class="n">PHILDEALPHIA</span>  
<span class="n">PHILDELPHIA</span>  
<span class="n">PHILDELPHILA</span>  
<span class="n">PHILDEPPHIA</span>  
<span class="n">PHILDRLPHIA</span>  
<span class="n">PHILEAPHIA</span>  
<span class="n">PHILIAHELPHIA</span>  
<span class="n">PHILIDELPHIA</span>  
<span class="n">PHILLA</span>  
<span class="n">PHILLADELPHIA</span>  
<span class="n">PHILLY</span>  
<span class="n">PHILOADELPHIA</span>  
<span class="n">PHLADELPHIA</span>  
<span class="n">PHOLADELPHIA</span>  
<span class="n">PHPILADELPHIA</span>  
<span class="n">PIHLADELPHIA</span>  
</code></pre>
</details>

**Suggested `#nocode` tools:**   

- To query and join database tables to get the single `csv`, try these `#nocode` tools: [~~SQL~~](https://en.wikipedia.org/wiki/SQL)
- To clean tabular data, try: [~~pandas~~](https://en.wikipedia.org/wiki/Pandas_(software)), [~~Spark~~](https://en.wikipedia.org/wiki/Apache_Spark), [Excel](https://www.microsoft.com/en-us/microsoft-365/excel), [Numbers](https://www.apple.com/numbers/), [Sheets](https://www.google.com/sheets/about/), [OpenOffice Calc](https://www.openoffice.org/product/calc.html)
- To clean and augment images, try: [~~torchvision~~](https://pytorch.org/docs/stable/torchvision/transforms.html), [Paint](https://support.microsoft.com/en-us/help/4027410/windows-10-open-microsoft-paint), [Preview](https://support.apple.com/en-sg/guide/preview/welcome/mac)


### 4. Set (offline) validation approach and metrics. Then, click [here](#5-train-the-machine-learning-model-via-one-click).
- Decide how to split the data into train, validation, and test. (By default, _random-split_ is used, though a [_time-based split_](https://www.fast.ai/2017/11/13/validation-sets/) should be used in most production settings.)
- Decide on metric(s). (By default, [RMSE](https://en.wikipedia.org/wiki/Root-mean-square_deviation) _and_ [accuracy](https://en.wikipedia.org/wiki/Accuracy_and_precision#In_binary_classification) are selected; pick whichever looks best after validation.)
- (Note: Upgrade to PRO edition and get 100+ metrics sorted in order of "What looks best").


### 5. Train the machine learning model via [one-click](#6-validate-the-model-offline-then-click-here). 
- This is the easiest step of all; click on this above ☝️
- The package will run all supervised, unsupervised, semi-supervised, self-supervised, reinforcement, transfer, ensemble, meta, few-shot, one-shot, blockchain learning models, starting with the _most_ compute-intensive.

### 6. Validate the model offline. Then, click [here](#7-deploy-the-ml-model-via-one-click).
- If you have done steps [**2**](#2-define-your-business-problem-and-objective-then-click-here) and [**4**](#4-set-offline-validation-approach-and-metrics-then-click-here) properly, this will be straightforward.
- (Optional) Model analysis via [learning curves](https://en.wikipedia.org/wiki/Learning_curve_(machine_learning)), [precision-recall trade-offs](https://en.wikipedia.org/wiki/Precision_and_recall), [residual analysis](https://en.wikipedia.org/wiki/Regression_analysis#Underlying_assumptions), etc.
- (Optional) Feature importance and [selection](https://en.wikipedia.org/wiki/Feature_selection). (By default, all features are selected even if only 1% are useful.)
- (Optional) [Error analysis](https://www.coursera.org/lecture/machine-learning/error-analysis-x62iE), examine [counterfactuals](https://en.wikipedia.org/wiki/Counterfactual_conditional) and skewed classes (and [adjust distribution](https://en.wikipedia.org/wiki/Oversampling_and_undersampling_in_data_analysis)).  

### 7. Deploy the ML-model via [one-click](#8-validate-the-model-online-ie-ab-testing-then-click-here).
- This is also easy; click on this above ☝️
- By default, the model with the best metric is deployed (even if it requires _10x compute and data_ for training, has _100x inference latency_, and _0.001% improvement_ relative to the 2nd best).
- (Optional) Decide serving approach: Cache, microservice, or embedded in app? (By default, served via `csv`).
- (Optional) Perform QA, integration testing, and stress testing to ensure optimal customer experience.

### 8. Validate the model online (i.e., A/B testing). Then, click [here](#9-share-the-results-then-click-here).
- Estimate effect size and decide on sample size required.
- Decide on random assignment condition: By customer, session, or product?
- Decide on [attribution](https://en.wikipedia.org/wiki/Attribution_(marketing)) model: First touch, last touch, multi-touch, or no-touch?
- Decide on statistical approach: Frequentist, Bayesian, or [Torturean](https://en.wiktionary.org/wiki/if_you_torture_the_data_long_enough,_it_will_confess_to_anything)?

### 9. Share the results. Then, click [here](#10-maintain-the-model).
- Share the best results (even if it's a warehouse optimization model but recommendation CTR goes up).
- Design fancy slides and label everything related to statistics and ML as Artificial Intelligence™.

### 10. Maintain the model.
- You're done! 🎉
- ML models don't need to be refreshed or maintained. (But if you want unnecessary work, read [this](https://eugeneyan.com/writing/practical-guide-to-maintaining-machine-learning/).)


## FAQ

#### How can I contribute to the source code?
There's no need to—there's `#nocode`! But if you want to contribute to the README, raise a [PR](https://github.com/eugeneyan/nocode-ml/pulls).

#### I found a bug! How should I report it?
Impossible! Our package has `#nobugs` as it is `#nocode`.

#### Is this a joke or is this real?
Yes.

#### No seriously, what is this?
It's partly (i) a joke, (ii) a point about the non-ML code related work, and (iii) a basic ML workflow.


## To Do

- [x] Add quick start
- [x] Add no code style guide
- [x] Add license
- [ ] Add unit tests
- [ ] Add code coverage checks
- [ ] Add lint checks
- [ ] Add type checks
- [ ] Add CI/CD pipeline
- [ ] ~~Build CLI for developer experience~~ (out of scope as `#nocode`)

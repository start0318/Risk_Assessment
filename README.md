
# Privacy Risk Assessment
# National Household Travel Survey Data

# Data Practicum II
# Regis University
# Leidy Boyce

## 1.Research Questions

### What is consider sensitive data?
### What is the most suitable method against identity disclosure?
### What is the level of identifiability considering the people and settings of the data environment?
### What threats to the data need to be managed?
### Can we create a “low-risk public dataset” that maintains all the research benefits of the original dataset with minimal privacy risk?


## 2. Why a Risk Assessment is necessary?

    NREL's Transportation Secure Data Center (TSDC) serves as a centralized repository of detailed transportation
    data from travel surveys and studies conducted in the U.S.

    It's purpose is to make this highly valuable data available to researchers in a way that protects the 
    privacy of the study's participants. NREL maintains the TSDC in partnership with the U.S. Department of
    Transportation and the U.S. Department of Energy.

    The risk assessment is done by identifying so-called disclosure or intrusion scenarios. A disclosure scenario
    describes the information potentially available to the intruder (e.g., census data, electoral rolls,
    population registers or data collected by private firms)  to identify respondents and the ways such
    information can be combined with the Survey datasets  to be released and used for re-identification of
    records in the dataset.

## 3. Data Source and Content: 

    State departments of transportation (DOTs), metropolitan planning organizations (MPOs), and  research
    organizations regularly collect travel survey data. Detail demographic and socioeconomic data is collected
    for household members, as well as travel and vehicle data.  Collection period varies between 24-hrs to 48
    hrs.

## 4.Definitions

    The following definitions and concept were used in the risk assessment

### 4.1 Attribute Classification


### 4.2 Identifiers:
    The identifier attributes can be used to identify the individual unambiguously. A typical example of
    identifier is the passport number. 

### 4.3 Quasi-identifiers:
    A quasi-identifier attribute is an attribute that is not able to identify a single individual when it is used
    alone. However, when it is combined with other quasi-identifier attributes, they can univocally identify an
    individual. Among the quasi-identifier attributes, we distinguish between confidential and non-confidential,
    depending on the kind of information that they contain. An example of non-confidential quasi-identifier
    attribute would be the zip code, while a confidential quasi-identifier might be the salary. 

### 4.5 Gini Index: 
    Gini Index can be used to quantify the unevenness in variable distributions. The degree of Gini index varies
    between 0 and 1, where 0 denotes that all elements belong to a certain class or if there exists only one
    class, and 1 denotes that the elements are randomly distributed across various classes.


### 4.6 Disclosure Risk Measures

    The possibility that private or confidential information can be revealed is technically known as disclosure
    risk. For each user, the risk of re-identification can be computed, by measuring the probability of his re
    identification in a released data.

    Disclosure risk is the possibility of correctly re-identifying an individual in the released data file by
    matchingtheir data to an external file based on a set of quasi-identifiers.

    1. Probability that a sample unique is a population unique.
    2. Probability of a correct match between a record in the microdata to an external file.


### 4.7 Type of Disclosure:

    • Identity: Re-identification occurs when an individual’s identity can be attached to some data, either alone
    or in combination with other information.

    • Attribute disclosure: occurs when sensitive information is associated with an individual or group in the
    data. This can occur with or without identity disclosure.

    • Inferential disclosure: occurs when it’s possible to learn something new about an individual or group in
    the data more accurately than would have otherwise been possible.


### 4.8 Quantifying identifiability:

    • Prosecutor attack: prosecutor has background info and its used to match a record in the shared data. A
    scenario in which the entire dataset is used is known as the prosecutor risk.

    • Journalist attack: the journalist doesn't know the particular individual is in the shared data, which is a
    subset of a larger public dataset, but it does know that all the people in the data exist in a larger public
    dataset. Journalist method, while more permissive, requires specifying the reference population 


### 4.9 Equivalence class: 
   Records that share the same values on a set of quasi-identifiers are an “equivalence
    class.” When considering re-identification risk, we are only interested in a subset of variables in a data
    set that can make individuals unique in the population and are possibly publicly known. These quasi
    identifiers are sex, age, etc...


   𝑓𝑘 (sample frequency of key 𝑘): the number of individuals in the sample with the same combination of quasi-identifiers. 
   Therefore, Individuals with the same values of quasi-identifiers have the same sample frequency. 

    A value of 2 for an observation means that in the sample, there is one more individual with exactly the same combination 
    of values for the selected variables.

    It is important to note that missing values are treated as if they were any other value. 
    If 𝑓𝑘=1, this individual has a unique combination of values of quasi-identifiers and is called “sample unique”.

    The fewer the individuals with whom an individual shares his or her combination of quasi-identifiers, the more likely the 
    individual is to be correctly matched in another dataset that contains these quasi-identifiers. 

    The individual risk is the same for all individuals sharing the same pattern of values of quasi-identifiers.
    This individual risk can also be interpreted as the probability of disclosure for the individuals.

    This risk is the worst-case scenario risk and does not imply that the person will be re-identified with certainty 
    with this probability.
    For instance, if an individual included in the data is not included in the external data file, the probability for 
    a correct match is zero. Even thought the risk measure computed based on the frequencies was positive.


### 4.10 Global risk:
    Global risk is the mean of all individuals risk in the sample. One caveat of this global risk is that it can
    be relatively low, but a few individuals could have a very high probability of re-identification. The problem
    with average risk is that it allows records that are unique to be released. 

###   4.11 Strict average risk is a combination of the average risk and k threshold.
    For example, 2-anonymity, means that there are at least two records that share any combination of values of
    quasi-identifiers. Meeting this threshold means getting rid of the unique records in the data set. Adhering
    to strict average risk ensure that there are no unique Individuals in data set.

### 4.12 Entropy: Shannon’s entropy quantifies the amount of information in a variable. The idea with entropy
    is that the more heterogenous and impure a feature is, the higher the entropy. Conversely, the more
    homogenous and pure a feature is, the lower the entropy.


    The expected amount of self-information contained in a random event is called entropy. The lower the entropy,
    the lower the expected amount of self-information that is associated with the system.

    A database system with a low entropy score leads to a low risk of disclosure in database entries (Trabelsi et
    al., 2019). The intuition for that argument is that, for a given amount of information that is required to
    re- identify data entries in a database system, if the expected amount of self-information contained in the
    system is low, the likelihood of disclosure is low. 

### 4.13 Inadvertent Risk: 
    Captures the probability that data recipient can potentially recognize someone in the data set.


## 5. Project Methodology

    1.	Identify the privacy metric for the project
    2.	Evaluate the risk of re-identification using the value quasi-identifiers
    3.	Evaluate the risk of re-identification using an external source (population data)
    4.	Identify Risk Thresholds
    5.	Evaluate the loss of information after 

    NOTE: I cannot share my code of data due to work restriction.

## 6. Conclusions

    •A risk-based approach to data protection promotes a better understanding of difficult privacy concepts.
    •Conducting A Risk Assessment enables TSDC to understand the overall sensitivity of the data. 
    •It can be impossible to assess re-identification risk with absolute certainty.
    •Gini Index provides a mean to identify and properly categorize the information in a survey using the amount
    of information hold in each feature, helping us to prioritize each individual feature by its risk level.
    •Estimating the rareness in the sample or population has some limitations: 
        •it does not consider intruder knowledge explicitly, and, 
        •in case of continuous variables, number of population uniques maybe extremely large.


## 7. Further work
    Built a Risk-Utility Map for the dataset hosted by the TSCD will be beneficial to show data providers the TSCD 
    accountability and data protection safeguards in place.

    Example of Risk-Utility Map:

## 8. References: Please refer to the bibliography.doc file attached in this repository. 

## 9. Lessons Learned:

    Coming into this project with little to zero experience or knowledge in the privacy landscape was bit intimidated and 
    challenging for sure. An intensive literature review was a great place to start and shape the work needed to be done. 
    I’ve to remind myself to be comfortable with the unknown and strive to do the best while I was learning in the process.  

    I struggled to find a direct process workflow to answer the research questions. My first approach to this project was 
    apply some familiar concepts and techniques to evaluate privacy, like machine learning models, but the results did not 
    make much sense, making me doubt on the validity of my approach.  I quickly realize that ML models, although highly 
    predictive due to their data mining, flexible and non-linear nature, are not usually calibrated to model geographical
    relationships, essentially being ‘aspatial’ algorithms. 

    I learned that Spatial is Special!!!  Dealing with geo spatial data, I needed a methodology that account not only 
    for spatial structure of data but the meaning of that data. I found specific libraries in python to evaluate
    privacy using locations data(scikit-mobility) and do spatial geo-statistics (pysal); even though I did not use 
    them directly on my project, exploring them planted ideas on a better approach to solve my project.

    At the end of these two months, I appreciate the unfamiliar waters I was in and I feel great that I did not drown. 



```python

```


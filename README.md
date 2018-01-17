# 5Ps Project (NLP)
Social Media Text Analysis and Profiling based on the 5Ps concept

This is a vast text analysis and advanced profiling project following the 5 Ps system. 

ABOUT THE 5 Ps SYSTEM: 
- we consider a social media mention as base unit or "atom" in our system (this can be text, picture, video, or soundbyte)
- at subatomic level, we'll have words, pixels, ... 
- at molecular level, we have the atom (the social media mention), linked to other mentions: replies, comments on a blog post, retweets, ...
- to each of these base units that are social media mentions, we attach 5 properties: 
- PRODUCT: this is the object of the sentence, what product, brand, politician, topic, ... are the other elements of the mention centered around
- PEOPLE: the subject, meaning the author of the post
- PLACES: on which medium / online platform is the mention found 
- PERCEPTION: how does the subject perceive the product, this involves sentiment among other things
- POTENCY: measurement of the reach of the mention

- Metadata: there are also some additional data like geographical element, time element, ... 

The above is just a top level description of the 5 Ps system. 

I developed the 5 Ps system over the years to replace the usual questions: who, how, where, why, ...
What I find unproductive with the usual W questions is that they are too broad, unfocused, and don't follow a safe enough rationale. 

Let's take one example found on tripadvisor for the Hard Rock Cafe in Los Angeles, the contributor is from the UK: 
"We decided to eat at the Hard Rock, it is one of our favourite chains, even though it is a glorified burger bar really. Anyhow, we had some lovely food and a great server ..."
If you compare analytics reports from different providers, you'll see under the question "Where" different things: is it the location of the Hard Rock Cafe? The main residence of the author? The location of the author when she/he wrote the post? The platform that hosts the comment (tripadvisor)?  ...

With the 5 Ps system, we'll be able to classify things in a much rational manner: 
- Hard Rock Cafe Los Angeles will be PRODUCT
- Tripadvisor = PLACES
- The UK = auth_resid_cntry field in the metadata
- And also the location of the author when writing the post = auth_location field in the metadata of the mention

ABOUT THE PROJECT 

The purpose is to get a better understanding of trends and human behaviors, and supply a methodology and an ever-growing dataset for research purposes in multiple disciplines: sociology, politics, marketing, psychology, medical, ...

- The project will consist of 2 main datasets: 
- 1. MENTIONS DATASET: mentions are stored, text is tokenized, metadata and all 5 P's elements are extracted and/or infered from the textual data, each mention will link to one author in the second dataset: 
- 2. AUTHOR DATASET: we store all the data we have about the author, some are just metadata like residence, name (is available), and shouldn't change much over time. 
Some other data are infered from an ongoing mentions analysis, testing different algorithms: level of language, typos ratio, brands mentioned, sentiment analysis on TOPICS mentioned, ... 

The first milestones are: 
1. Project preparation
- obtaining the data from different sources
- naming conventions for all variables, ensuring it is comprehensive enough without constantly referring to a codebook and scalable, as we will add large amounts of new variables as the project develops
- data flow between the different sources and the target databases
- data preprocessing: both for metadata and text processing 

2. Make the data 5P compliant: 
- infer from text elements each of the 5 Ps, 
- PRODUCT: work on datasets of brands, products, 
- measuring accuracy

3. Sentiment analysis part 1:
The approach is to drop the usual positive, neutral, negative paradigm. This can be infered at a later time from the mention analysis but the focus is on a more granular level. 
- mention analysis based on the 5 Ps
- each unique sentiment occurence (there can be several ones per mention) will take several of the 5 Ps into account: 
- product: what or who is the object of the statement, 
- people: from whom originates the emotional statement, author or someone else, 
- perception: among others, what element of language (verbs, adjectives, ...) is used, what does it concern (for instance the customer service of the brand (PRODUCT), or the specific feature of a product), ...
- create system that links the result of the analysis of each unique sentiment occurence to the mention itself
- create system that links the result of the analysis of each unique sentiment occurence to the author database: this will help with measuring affinity with brands, ideologies, psychological dispositions, ... 

SPECIFICATIONS OF THE PILOT PROJECT

- Project primarily developed with R and SQL
- Updates posted in this repository: https://github.com/xvalda/5Ps-Project-NLP-



... last updated 17 January 2018


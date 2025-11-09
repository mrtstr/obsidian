### text training data and preprocessing
#### sources
- **Wikipedia**
- **CommonCrawl**: collection of web pages (no filtering or quality control)
- **FineWeb**: larger open source dataset for [[LLM]] training with quality control
- crawlers like GPTBot or ClaudeBot

#### pre-processing
1) **Text Extraction**: remove for example HTML code
2) **URL Filtering**: remove blacklisted [[uniform resource locator (URL)]]
3) **Language Filtering**: remove languages that should not be trained (like FineWeb only english)
4) **Deduplication**: remove duplicated text
5) **Additional Quality Filtering**: remove unwanted patterns like high fraction of short lines (e.g. I; ML; Deep Learning; NLP; Robotics) lines


#### quality instead of quantity approach
- a [[LLM]] trained on a small but relevant and high quality dataset can outperform a [[LLM]] trained on a larger dataset
- for example **FineWeb Edu** a filtered version of the **FineWeb** dataset that only contains text with a high **educational quality score**

1) annoted **educational quality score** with the use of an [[LLM]]
2) train a classifier to rate the **educational quality score** of texts
3) filter the **FineWeb** by keeping only texts with a score >= 3 of 5

→ [[LLM]] demonstrated comparable or superior performance than a model trained on a 10 times larger dataset

**general problem**: [[LLM]] don't lean the truth but only what thy see and thus take over biases and might even generalize them
# anki


START
Basic
[[nn text training data and preprocessing]]
- sources (4)
- preprocessing steps (5)

Back: 
### text training data and preprocessing
#### sources
- **Wikipedia**
- **CommonCrawl**: collection of web pages (no filtering or quality control)
- **FineWeb**: larger open source dataset for LLM training with quality control
- crawlers like GPTBot or ClaudeBot

#### pre-processing
1) **Text Extraction**: remove for example HTML code
2) **URL Filtering**: remove blacklisted [[uniform resource locator (URL)]]
3) **Language Filtering**: remove languages that should not be trained (like FineWeb only english)
4) **Deduplication**: remove duplicated text
5) **Additional Quality Filtering**: remove unwanted patterns like high fraction of short lines (e.g. I; ML; Deep Learning; NLP; Robotics) lines
Tags: ml WS2526
<!--ID: 1761579643557-->
END


START
Basic
[[nn text training data and preprocessing]]
- example and result
- general problems with the training data of [[LLM]]

Back: 


#### quality instead of quantity approach
- a [[LLM]] trained on a small but relevant and high quality dataset can outperform a [[LLM]] trained on a larger dataset
- for example **FineWeb Edu** a filtered version of the **FineWeb** dataset that only contains text with a high **educational quality score**

1) annoted **educational quality score** with the use of an [[LLM]]
2) train a classifier to rate the **educational quality score** of texts
3) filter the **FineWeb** by keeping only texts with a score >= 3 of 5

→ [[LLM]] demonstrated comparable or superior performance than a model trained on a 10 times larger dataset

**general problem**: [[LLM]] don't lean the truth but only what thy see and thus take over biases and might even generalize them

________________
### text training data and preprocessing
#### sources
- **Wikipedia**
- **CommonCrawl**: collection of web pages (no filtering or quality control)
- **FineWeb**: larger open source dataset for LLM training with quality control
- crawlers like GPTBot or ClaudeBot

#### pre-processing
1) **Text Extraction**: remove for example HTML code
2) **URL Filtering**: remove blacklisted [[uniform resource locator (URL)]]
3) **Language Filtering**: remove languages that should not be trained (like FineWeb only english)
4) **Deduplication**: remove duplicated text
5) **Additional Quality Filtering**: remove unwanted patterns like high fraction of short lines (e.g. I; ML; Deep Learning; NLP; Robotics) lines
Tags: ml WS2526
<!--ID: 1761579643560-->
END

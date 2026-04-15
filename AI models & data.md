#  AI models & data
## Training data
The data used for training of any ai model is from 
- Web scraping : Automated crawls of public internet content
                Low: no curator, no version control, content changes after collection
- Licensed data : Data purchased or agreed with platforms (e.g., OpenAI + Reddit, Meta's own social posts)
                  Medium: terms often unclear; original users rarely consented to AI training use
- Synthetic data : AI-generated content used to train further AI systems
                    Variable: growing fast; ~12% of fine-tuning datasets now contain LLM-generated content
- Internal corpora : Company knowledge bases, support transcripts, clinical notes used for fine-tuning
                    Higher: organisation has direct control, but also direct liability if mishandled


  The most widely used training dataset is **Common Crawl**(opens in new tab), a free, publicly available archive of web crawl data that has underpinned essentially every major model family.
  Visit : https://commoncrawl.org/
  Modern AI models such as DeepSeek-V2, DeepSeek-V3, LLaMA 4, and GPT-3 are trained on massive datasets containing trillions of tokens. A major portion of this data comes from Common Crawl.
For example:
- GPT-3 used ~60% of its data from a filtered version of Common Crawl
- Newer models rely even more heavily on similar large-scale web data

The key issue is **data filtering**:
- Data is "filtered" before training
- The filtering process is not always transparent
- It is unclear who controls the filtering and what data is removed

This creates potential **security risks**:
- Harmful or biased data may remain in the dataset
- Malicious content can influence model behavior
- Lack of transparency raises trust and safety concerns

## ML-BOM & AI Supply Chain Security

- In traditional software security, incidents like the SolarWinds attack showed that software cannot be trusted without knowing its internal components.
- This led to the concept of **SBOM (Software Bill of Materials)**, which lists all components used in software.

### AI Equivalent: ML-BOM
- In AI systems, a similar approach is called **ML-BOM (Machine Learning Bill of Materials)**.
- It is used to document everything involved in training a model.

### What ML-BOM Includes
- Sources of training data
- Data usage licenses
- Personally identifiable information (PII)
- Data cleaning and filtering steps

## PII in AI Training Data

- Large training datasets may contain sensitive data like API keys and passwords.
- Truffle Security scanned the December 2024 Common Crawl dataset (~400TB, 2.67B web pages) and found ~12,000 valid API keys and passwords.
- AI models can sometimes reproduce this data when prompted.
- This is not an external attack, but a result of insecure training data.

### Risk
- Exposure of credentials
- Data leakage from models

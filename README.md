\# MotiveVerse AI Hackathon - Video Query System



\*\*2nd Place | Score: 83.2/90\*\*



\## Problem Statement

Parse natural language queries to retrieve dashcam videos from a 500-video dataset with pre-extracted features.



\### Example Queries

\- "Show t-bone collisions but exclude silver vehicles"

\- "Vehicle loses traction in desert with clear weather"  

\- "Red light violations in heavy rain"



\## Solution Overview



\*\*Architecture:\*\* Claude LLM (AWS Bedrock) + Domain-Specific Post-Processing



\### 1. Query Parsing (Claude)

\- Convert natural language to structured metadata filters

\- System prompt with traffic/collision domain rules

\- Handles negation, vehicle descriptions, weather conditions



\### 2. Error Correction (Post-Processing)

\- Vehicle model aliasing: "Kenworth T680" matching

\- Traffic signal reclassification

\- Negation handling for exclusion filters

\- Vehicle control disambiguation



\### 3. Semantic Filtering

\- Substring + semantic matching on dataset

\- Support for color + vehicle type matching

\- Abbreviation handling (Ave to Avenue)



\## Performance

\- \*\*Score:\*\* 83.2/90 on hidden test set

\- \*\*Dataset:\*\* 500 dashcam videos with metadata

\- \*\*Accuracy:\*\* 92.6% on test queries



\## Tech Stack

\- Claude 3.5 Sonnet (AWS Bedrock API)

\- Python 3.9+

\- Pandas, NumPy

\- Boto3 (AWS SDK)



\## Files

\- `problem2 (1).ipynb` - Complete working solution



\## How to Run
pip install pandas numpy boto3 python-dotenv
Set environment variables
export AWS_ACCESS_KEY_ID=your_key
export AWS_SECRET_ACCESS_KEY=your_secret
export AWS_REGION=us-east-1
Run notebook
jupyter notebook "problem2 (1).ipynb"

## Key Insights
1. Prompt engineering > embeddings for this task
2. Post-processing critical — Claude alone scored ~75%, corrections brought it to 83.2%
3. Domain knowledge matters — traffic/collision terminology was crucial

## What's Next
- Add vector embeddings for semantic search
- Quantify correction logic effectiveness
- Test on larger query sets

---

Built for MotiveVerse AI Hackathon 2025

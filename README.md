# Sentiment-Driven Community Detection in a Network of Perfume Preferences

## Project Overview
This repository contains datasets used in our paper, **"Sentiment-Driven Community Detection in a Network of Perfume Preferences."** The research focuses on applying community detection techniques to analyze a network of perfume preferences based on positive user reviews from a Persian retail platform, Atrafshan. The study leverages sentiment analysis to group perfumes into clusters, revealing shared consumer preferences in the fragrance domain.

### Key Contributions:
- The first exploration of community detection in a network of perfumes, driven by positive user feedback.
- Sentiment analysis enhanced by emojis and user ratings, offering better accuracy in comment classification.
- A unique **Perfume Co-Preference Network**, linking perfumes based on shared positive reviews.

### Keywords:
Community Detection, Data Mining, Perfume Networks, Sentiment Analysis, User Preferences, Co-Preference Network, Persian Retail Platform.

## Datasets
This repository includes multiple datasets used for the study, providing a comprehensive view of perfume reviews, sentiment analysis, and emoji mappings.

### 1. **User Reviews and Perfume Attributes Dataset**
- **Comments:** 36,434 comments from 7,387 unique users.
- **Ratings:** User ratings on perfume attributes such as Scent, Longevity, Sillage, and Bottle Design.
- **Metadata:** Includes usernames, user IDs, and comment types (e.g., standalone or replies).

#### Fields:
- **user_id:** Unique identifier for the user.
- **user_name:** Name of the user who left the comment.
- **comment_text:** The text of the user's review, providing insights into their sentiment towards the perfume.
- **perfume_id:** Unique identifier for the perfume.
- **perfume_name:** Name of the perfume.
- **perfume_brand:** Brand of the perfume.
- **perfume_url:** URL to the perfume's page on the Atrafshan website.
- **scent_specifications:** Fragrance group, perfumer, and nature of the perfume (e.g., warm, fresh).
- **production_specifications:** Brand name (in Farsi), country of origin, and release year of the perfume.
- **users_vote:** Community-wide ratings on various perfume attributes (scent, longevity, diffusion, and design).
- **user_vote_on_perfume:** Specific user ratings on perfume aspects.

#### Example JSON Structure:
```json
{
    "user_id": "93040",
    "user_name": "علی",
    "comment_text": "در برنامه خریدم هست ولی نمیدونم چرا نمیتونم باهاش کنار بیام حس میکنم بوی رژ لب میده",
    "perfume_id": "1030",
    "perfume_name": "Dior Homme Intense",
    "perfume_brand": "Dior",
    "perfume_url": "https://www.atrafshan.ir//perfume/1030-480/dior-homme-intense",
    "scent_specifications": {
        "fragrance_group": "چوبی گلی مُشکی",
        "perfumer": "فرانسوا دماشی",
        "nature": "گرم"
    },
    "production_specifications": {
        "brand_name_farsi": "دیور",
        "origin_country": "فرانسه",
        "release_year": "2007"
    },
    "users_vote": {
        "smell": "8.2",
        "durability": "7.8",
        "diffusion": "7.6",
        "design": "8.2"
    },
    "user_vote_on_perfume": {
        "votes": {
            "رایحه": "8",
            "ماندگاری": "7",
            "پخش بو": "7",
            "طراحی شیشه": "8"
        },
        "comment_id": "128773",
        "is_comment_answer": "NO"
    }
}
```
## 2. Emoji Mapping Dataset
A dictionary of **392 common emojis** mapped to their Persian equivalents.

#### Example:

```
- "😍" → "چشم های عاشق" ("Loving Eyes").
```

This dataset allows for a more accurate sentiment analysis by incorporating emoji usage in user comments.

## 3. Sentiment Classification Results
We provide **three CSV files** containing the sentiment classification results, with each file biased towards a specific perfume attribute: **Scent**, **Longevity**, or **Sillage**.

### Methodology:
First, we used the [**ParsBert** model](https://github.com/hooshvare/parsbert) to classify comments based on sentiment. The sentiment classification was conducted on the user comments, where only positive comments were considered for constructing the perfume-perfume network.

To further enhance the accuracy of sentiment classification, we integrated **user votes** on three essential perfume categories—**Scent**, **Longevity**, and **Sillage**—into the sentiment analysis process. This integration provided a more refined sentiment classification for each aspect of the perfume experience.

### Sentiment Classification Integration:
To enhance the accuracy of sentiment labels, user votes regarding three essential perfume attributes—**Scent**, **Longevity**, and **Sillage**—were integrated into the classification process. Each user's rating (R) for these categories was used to bias the sentiment analysis, as detailed below:

- **R ≥ 7:** Positive sentiment.
- **R ≤ 3:** Negative sentiment.
- **4 < R < 7:** Ambiguous, no sentiment change.

This systematic integration allows for a more nuanced understanding of consumer preferences across different dimensions of the perfume experience.

### CSV Files:
1. **Scent-biased sentiment classification**
2. **Longevity-biased sentiment classification**
3. **Sillage-biased sentiment classification**

## Usage
The datasets provided in this repository are available for use in further research and analysis. They can be leveraged to study user preferences, conduct community detection, or enhance recommendation systems in the fragrance industry.

## Terms of Use
The datasets are shared for academic and non-commercial purposes only. Please ensure proper citation if you use the data in your work.

## Citation

## Authors
- Kamand Kalashi - [GoogleScholar](https://scholar.google.com/citations?user=Rjiq7qUAAAAJ&hl=en), [GitHub](https://github.com/Kamii114), [LinkedIn](https://www.linkedin.com/in/kamand-kalashi-0696b1199/), [ResearchGate](https://www.researchgate.net/profile/Kamand-Kalashi)
- Sajjad Saed -    [GoogleScholar](https://scholar.google.com/citations?user=4xT5JlQAAAAJ&hl=en), [LinkedIn](https://www.linkedin.com/in/sajjad-saed-845908125/), [ResearchGate](https://www.researchgate.net/profile/Sajjad-Saed)
- Babak Teimourpour - [GoogleScholar](https://scholar.google.com/citations?user=Hb0DMrUAAAAJ&hl=en), [LinkedIn](https://www.linkedin.com/in/babak-teimourpour-7877482b/), [ResearchGate](https://www.researchgate.net/profile/Babak-Teimourpour)


# Video Summarizer

## Introduction

Video Summarizer App uses Generative AI to give you the key points of long videos so you can save time for the things that matter most.

## Setup

1. Clone the repositor

```bash
git clone https://vivek-chaprana/video-summarizer.git
```

1. Install the required packages

```bash
pip install -r requirements.txt
```

2. Copy the `.env.example` file to `.env` and update the values

```bash
cp .env.example .env
```

3. Run the application

- UNIX/Linux

```bash
streamlit run app.py
```

- Windows

```bash
python -m streamlit run app.py
```

4. Open the browser and go to `http://localhost:8501` to view the application.

## How to use ?

1. Input a video youtube video url.
1. Click on the `Summarize` button.
1. The video will be summarized.

## How it works ?

1. **Get Video URL**: The user enters the YouTube video URL in the text input field provided by Streamlit.
1. **Extract Video ID**: From the entered URL, the application extracts the video ID using string manipulation (splitting the string at the "=" symbol).
1. **Attempt Transcript Retrieval**: The application uses the YouTubeTranscriptApi library to try and retrieve a transcript for the video based on the extracted ID.
   Transcript Found:

- If a transcript is successfully retrieved, the application proceeds to step 4 (summary generation).
  Transcript Not Found:
- If no transcript is available, the application can handle the situation in a few ways:
  - Inform the user: A message can be displayed indicating that the application couldn't find a transcript and therefore cannot generate a summary.
  - Offer Alternative (Optional): You could explore offering an alternative summarization method that doesn't rely on transcripts, like automatic speech recognition (ASR) for a less accurate but still informative summary.

1. **Generate Summary**:
   It then uses Google's Generative AI model (specifically the Gemini-Pro model) to analyze the combined text.
   The model generates a summary highlighting the key points of the video.
1. **Display Results**:
   The application displays the video thumbnail image using the extracted video ID.
   If a summary was generated (transcript found), it displays the summary under the heading "## Summary:".

## Future Work

1. Add more paltforms to fetch the video.
1. Add more summarization techniques.
1. Add more customizations to the summarizations.
1. Add features to share the summary of video on social media.

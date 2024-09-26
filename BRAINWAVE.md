# Welcome to TwelveLabs Jockey!
The world's coolest agentic video framework, based on TwelveLabs video models.

## Links
**Video, Audio, Imagery & On-Screen Text Understanding**  
Search  
Text, context, dialogue, etc. within video  
  
Generate  
Titles, topics, hashtags (/gist)  
Summaries, chapters, and highlights (/summarize)  
Create open ended text about your content (/generate)  
  
Classify  
Organize your content  

**Embeddings**
[Video](https://docs.twelvelabs.io/reference/video-embeddings) & [Text](https://docs.twelvelabs.io/reference/text-embeddings) 

**Note:** the embeddings API is not generally available. The other endpoints are powerful enough that most people won’t need embeddings, but Twelve Labs is providing accelerated access for hackathon participants. Fill out [this form](https://twelvelabs.typeform.com/to/q0VyBAd4?typeform-source=tl-docs) to request access


**API Docs**
[Quickstart](https://docs.twelvelabs.io/v1.1.1/docs/quickstart)

**SDK**
https://pypi.org/project/twelvelabs/
https://github.com/twelvelabs-io/twelvelabs-js

**Playground**
https://playground.twelvelabs.io/

**Pricing** 
https://www.twelvelabs.io/pricing

**Jockey**
https://www.twelvelabs.io/blog/introducing-jockey
https://github.com/twelvelabs-io/tl-jockey

# Environment 

## GPU/Server configuration 
Local is possible, this uses a VM

## YT DLP
```sudo curl -L https://github.com/yt-dlp/yt-dlp/releases/latest/download/yt-dlp -o /usr/local/bin/yt-dlp
sudo chmod a+rx /usr/local/bin/yt-dlp 
yt-dlp <YouTube_video_url>
```

## Colorado Hikes 
https://www.youtube.com/watch?v=KKeZPA-Gvs4

# Twelve Labs Setup 

## Create an Account 
https://playground.twelvelabs.io/  
10 hours free video uploaded  
50 API calls/day <<<< be judicious!  

## Create an Index 
https://playground.twelvelabs.io/indexes  

## Upload video(s)
https://playground.twelvelabs.io/  

# Accessing API 
`export TL_API_KEY=<your key from: https://playground.twelvelabs.io/dashboard/api-key>`
`export VIDEO_INDEX = <your index>`  

[Search](https://docs.twelvelabs.io/reference/make-search-request)  
```
curl -X POST https://api.twelvelabs.io/v1.2/search \
     -H "Accept: application/json" \
     -H "X-Api-Key: ${TL_API_KEY}" \
     -H "Content-Type: application/json" \
     -d "{\"search_options\":[\"visual\",\"conversation\",\"text_in_video\"],\"adjust_confidence_level\":0.5,\"group_by\":\"clip\",\"threshold\":\"low\",\"sort_option\":\"score\",\"operator\":\"or\",\"conversation_option\":\"semantic\",\"page_limit\":10,\"query\":\"waterfall in fall\",\"index_id\":\"${VIDEO_INDEX}\"}"
```

[Classify](https://docs.twelvelabs.io/reference/classify-bulk)  
 
[Generate](https://docs.twelvelabs.io/reference/generate-text-from-video-1)  
[Generate: gist](https://docs.twelvelabs.io/reference/generate-gist)  
[Generate: Summary](https://docs.twelvelabs.io/reference/summarize)  
[Generate: Text](https://docs.twelvelabs.io/reference/generate-text-representation)  


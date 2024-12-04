# Text to AI Presenter Video 🎥

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1ctABZFrmlKKf0LP1852PRUoX3uLswbtB)

An automated system that converts text into educational videos featuring AI presenters. The system generates professional presentations with synchronized avatar animations, creating engaging educational content.

## 🎯 Features

- Text preprocessing and URL cleaning
- Automatic slide generation with Gemini Pro AI
- Dynamic image fetching from Unsplash
- Text-to-speech conversion with natural voices
- Avatar lip-sync animation
- Automatic video composition and rendering

## 🔄 Process Flow

```mermaid
flowchart TB
    subgraph Input
        A[Input Text] --> B[Text Preprocessing]
        B --> C[Remove URLs & Clean Text]
    end

    subgraph PPT_Generation
        C --> D[Generate Slide Content]
        D --> E[Generate Images]
        D --> F[Generate Audio]
        E & F --> G[Create Slides]
        G --> H[Combine Slides]
        H --> I[Final PPT Video]
    end

    subgraph Avatar_Generation
        I --> J[Extract Audio]
        J --> K[Select Avatar]
        K --> L[Process Avatar]
        L --> M[Generate Lip-Sync Video]
    end

    subgraph Final_Combination
        I --> N[Main Video]
        M --> O[Avatar Video]
        N & O --> P[Combine Videos]
        P --> Q[Final Output]
    end
```

## 🔍 Detailed Process Flow

```mermaid
sequenceDiagram
    participant User
    participant Text Processor
    participant Content Generator
    participant Media Services
    participant Avatar System
    participant Video Combiner

    User->>Text Processor: Input Text
    Text Processor->>Text Processor: Remove URLs
    Text Processor->>Text Processor: Clean Text
    Text Processor->>Content Generator: Processed Text

    Content Generator->>Media Services: Generate Slide Content
    activate Media Services
    par Media Generation
        Media Services->>Media Services: Fetch Images from Unsplash
        and
        Media Services->>Media Services: Generate Audio from Text
    end
    Media Services->>Media Services: Create Slides
    Media Services->>Media Services: Combine Slides
    Media Services-->>User: PPT Video Generated
    deactivate Media Services

    User->>Avatar System: Select Avatar
    Avatar System->>Media Services: Extract Audio from PPT
    Media Services-->>Avatar System: Extracted Audio
    Avatar System->>Avatar System: Process Avatar with Audio
    Avatar System-->>User: Avatar Video Generated

    User->>Video Combiner: Request Final Video
    Video Combiner->>Video Combiner: Combine PPT & Avatar
    Video Combiner-->>User: Final Combined Video
```

## 🚀 Quick Start

1. Open the project in Google Colab using the badge above
2. Run all cells in the installation section
3. Enter your presentation text
4. Select your preferred voice
5. Choose an avatar
6. Wait for the final video generation

## 📋 Requirements

- Python 3.8
- CUDA-enabled GPU (for avatar generation)
- Required Python packages:
  - edge-tts
  - moviepy
  - google-generativeai
  - pillow
  - python-pptx
  - torch
  - and others as listed in requirements.txt

## 🎥 Demo Video

<div align="center">
  <img src="examples/Demo.gif" alt="Demo Video" width="800"/>
</div>


## 🔧 Technical Components

1. **Text Processing**
   - URL removal
   - Text cleaning
   - Content structuring

2. **Presentation Generation**
   - Slide content generation using Gemini Pro
   - Image fetching from Unsplash
   - Audio generation using Edge TTS

3. **Avatar System**
   - Audio extraction
   - Lip-sync processing
   - Video rendering

4. **Video Composition**
   - Video synchronization
   - Final rendering
   - Quality optimization

## 🎨 Available Voices

- en-US-AvaNeural (Female)
- en-US-ChristopherNeural (Male)
- en-US-EricNeural (Male)
- en-US-JennyNeural (Female)

## 🤖 Available Avatars

- anne
- Narendra Modi
- Sky_2
- Rayan
- Rohit
- Diva
- Elon Musk
- Ava
- Mathew
- HC Verma
- Alicia

## 🙏 Acknowledgments

- Google Generative AI for content generation
- Unsplash for image resources
- Edge TTS for voice synthesis
- SadTalker for avatar animation

## 💡 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📧 Contact

Aakashdeep Srivastava
---

Made with ❤️ for educational content creation

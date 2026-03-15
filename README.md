# Daily APAC Business Podcast Generator

Automatically generates daily business news podcasts for the Asia-Pacific region using AI.

## Features

- 🎙️ **Automated Daily Podcasts** - Runs automatically every morning at 5:55 AM Singapore time
- 🌏 **APAC Focus** - Covers news from Singapore, Southeast Asia (Indonesia, Thailand, Vietnam, Philippines, Malaysia), and India
- 🤖 **AI-Powered** - Uses Claude AI for script generation and OpenAI TTS for natural-sounding voice
- 📰 **Real News Sources** - Aggregates from 20+ verified APAC news feeds
- ⚡ **Optimized** - 90% token reduction while maintaining quality
- ✅ **Anti-Hallucination** - Strict source grounding for factual accuracy

## Output

Each episode generates:
- 🎧 **MP3 Audio** - High-quality podcast (12-15 minutes)
- 📄 **Text Script** - Complete transcript
- 📝 **Word Document** - Formatted script with metadata
- 🔗 **Sources File** - All article references with URLs

## How It Works

1. **News Collection** - Fetches latest articles from APAC news sources
2. **Script Generation** - Claude AI creates a professional podcast script
3. **Audio Generation** - OpenAI TTS converts script to natural speech
4. **Quality Control** - Anti-hallucination checks ensure accuracy

## Setup

### Prerequisites

- Python 3.11+
- API Keys:
  - [Anthropic API Key](https://console.anthropic.com/)
  - [OpenAI API Key](https://platform.openai.com/api-keys)

### Local Installation

1. Clone the repository:
```bash
git clone https://github.com/ddadas/daily-APAC-podcast.git
cd daily-APAC-podcast
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Create `.env` file with your API keys:
```
ANTHROPIC_API_KEY=your_anthropic_key_here
OPENAI_API_KEY=your_openai_key_here
```

4. Run the generator:
```bash
python podcast_generator.py
```

### GitHub Actions Setup (Automated Daily Runs)

1. Go to your repository **Settings** → **Secrets and variables** → **Actions**

2. Add the following secrets:
   - `ANTHROPIC_API_KEY` - Your Anthropic API key
   - `OPENAI_API_KEY` - Your OpenAI API key

3. The workflow will automatically run daily at **5:55 AM Singapore time**

4. To run manually: Go to **Actions** → **Daily APAC Podcast Generator** → **Run workflow**

## Configuration

### Change Voice

Edit `podcast_generator.py` line 482 to change the voice:

```python
voice = "nova"  # Options: nova, onyx, shimmer, alloy, echo, fable
```

### Change Schedule

Edit `.github/workflows/daily-podcast.yml` line 7:

```yaml
- cron: '55 21 * * *'  # 5:55 AM SGT (21:55 UTC)
```

### News Sources

The script aggregates from these sources:
- Singapore: The Straits Times, Channel NewsAsia, Business Times
- India: Economic Times, Business Standard, Mint, The Hindu Business Line
- Southeast Asia: Jakarta Post, Bangkok Post, Vietnam News, Philippine Star
- International: Reuters Asia, Bloomberg Asia, CNBC Asia, Nikkei Asia

## Cost Estimation

Per episode:
- **Claude AI**: ~$0.05-0.10 (script generation)
- **OpenAI TTS**: ~$0.30-0.50 (audio generation)
- **Total**: ~$0.35-0.60 per episode

Monthly cost (30 episodes): **~$10.50-18.00**

## Voice Quality

The podcast uses **OpenAI TTS HD** for natural-sounding voices. The quality is significantly better than free alternatives like Google TTS or Edge TTS.

**Available voices:**
- `nova` - Warm, engaging (recommended for news)
- `onyx` - Deep, authoritative male voice
- `shimmer` - Clear, professional female voice
- `alloy` - Neutral, balanced
- `echo` - Male, clear
- `fable` - British accent, expressive

## Accessing Generated Podcasts

Episodes are saved as **GitHub Actions artifacts**:
1. Go to **Actions** tab
2. Click on the latest workflow run
3. Download the **podcast-episodes-XXX** artifact
4. Episodes are kept for 30 days

## Troubleshooting

### OpenAI TTS fails with "string too long" error
The script automatically splits long scripts into chunks. If this still occurs, check that the chunking logic is working properly.

### No articles found
Check if the news RSS feeds are accessible. Some feeds may require VPN or have rate limits.

### GitHub Actions fails
1. Verify API keys are correctly set in repository secrets
2. Check the Actions logs for specific error messages
3. Ensure you have Actions enabled in repository settings

## License

MIT License - feel free to use and modify!

## Credits

Powered by:
- [Claude AI](https://www.anthropic.com/) - Script generation
- [OpenAI TTS](https://platform.openai.com/docs/guides/text-to-speech) - Voice synthesis
- Various APAC news sources - Content

---

**Generated with AI 🤖 | Updated daily at 5:55 AM SGT**

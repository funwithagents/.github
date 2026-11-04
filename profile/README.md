# funwithagents 🤖

**Open-source building blocks for agents and robots that interact with people.**

At the core, [**wica-framework**](https://github.com/funwithagents/wica-framework) is a generic agent brain with multimodal inputs and outputs: any perception can flow in, and any capability can be exposed as an action. Around it, modular components handle the rest of the interaction: senses (speech recognition, vision), a voice (streaming TTS) and robot bodies (NAO, Reachy Mini).

<!-- TODO: replace with a 10–20 s GIF of an agent talking through a NAO or Reachy Mini -->
<!-- ![demo](https://raw.githubusercontent.com/funwithagents/.github/main/profile/demo.gif) -->

## How the pieces fit

```text
            ┌──────────────────────────────────────────┐
  Senses    │  asr-engine   vision-modules             │   speech, faces, gestures
            └───────────────┬──────────────────────────┘
                            ▼
  Brain     ┌──────────────────────────────────────────┐
            │  wica-framework  (World · Inputs ·       │   any LLM: Anthropic, OpenAI,
            │                   Commands · Agent)      │   Gemini, Mistral, HF Hub
            └───────────────┬──────────────────────────┘
                            ▼
  Voice     ┌──────────────────────────────────────────┐
            │  tts-engine                              │   streaming TTS, 12+ providers
            └───────────────┬──────────────────────────┘
                            ▼
  Bodies    ┌────────────────────┐  ┌──────────────────┐
            │ naoqi-bridge       │  │ reachy-mini-     │   real robot, simulator,
            │ (NAO / Pepper)     │  │ bridge           │   or offline fake
            └────────────────────┘  └──────────────────┘
```

Every block works on its own, and most ship an **MCP server** so you can plug them straight into an agent.

## Projects

### 🧠 Agent
| Repo | What it does |
|---|---|
| [**wica-framework**](https://github.com/funwithagents/wica-framework) | Agent framework for multimodal, embodied interaction: a state-first World, reactive Inputs, cancellable Commands, provider-agnostic LLM loop. |

### 🎙️ Senses & voice
| Repo | What it does |
|---|---|
| [**asr-engine**](https://github.com/funwithagents/asr-engine) | Async, real-time speech recognition with pluggable providers, segmentation and an optional MCP server. |
| [**tts-engine**](https://github.com/funwithagents/tts-engine) | Streaming text-to-speech: speak an LLM's answer while it's still being generated. Cloud (ElevenLabs, OpenAI, Gemini, Cartesia…) and local (Kokoro, Piper, Qwen3-TTS…) providers. |
| [**vision-modules**](https://github.com/funwithagents/vision-modules) | Composable perception over a live video stream: hand detection, gesture recognition, faces. |

### 🤖 Reachy Mini
| Repo | What it does |
|---|---|
| [**reachy-mini-bridge**](https://github.com/funwithagents/reachy-mini-bridge) | One async API for Reachy Mini: emotions, speech, face tracking, camera, mic. Same code on the robot, MuJoCo or an offline fake. |
| [**reachy-mini-lite-to-wireless-pi-setup**](https://github.com/funwithagents/reachy-mini-lite-to-wireless-pi-setup) | Turn a Reachy Mini Lite into a wireless robot with a Raspberry Pi — one-shot SD card setup. |

### 🤖 NAO toolkit
| Repo | What it does |
|---|---|
| [**naoqi-bridge**](https://github.com/funwithagents/naoqi-bridge) | Intent-level async API for NAO/Pepper, with MCP and WebSocket servers for agents and apps. |
| [**naoqi-sim**](https://github.com/funwithagents/naoqi-sim) | A NAO in a box: NAOqi 2.1 / 2.8 running in Docker, so you can develop without a robot. |
| [**naoqi-viewer**](https://github.com/funwithagents/naoqi-viewer) | Live 3D MuJoCo mirror of any NAOqi robot, and naoqi-sim's simulated world. |
| [**nao-unity**](https://github.com/funwithagents/nao-unity) | Unity scripts and a 3D NAO model to drive and visualize a NAO in real time. |
| [**naoqi-meshes**](https://github.com/funwithagents/naoqi-meshes) | NAO meshes converted for MuJoCo, license-gated for naoqi-viewer. |

### 🔧 Maintained forks
| Repo | What it does |
|---|---|
| [**libqi**](https://github.com/funwithagents/libqi) | NAOqi core framework (C++), the foundation the NAO toolkit talks to. |
| [**libqi-python**](https://github.com/funwithagents/libqi-python) | qi SDK Python bindings, with prebuilt wheels for macOS arm64, Linux x86_64 and Windows. |
| [**cozmo-python-sdk**](https://github.com/funwithagents/cozmo-python-sdk) | Anki Cozmo Python SDK, kept usable for Cozmo projects. |

## Get involved

⭐ Star what's useful to you
🐛 Open an issue if you try it on a robot we haven't tested (wireless Reachy Mini, NAO v6, Pepper…)
💬 Ideas and PRs welcome.

<sub>Unofficial projects, not affiliated with Aldebaran or Pollen Robotics.</sub>

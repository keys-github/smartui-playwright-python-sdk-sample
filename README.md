# SmartUI SDK Sample for Playwright Python — TestMu AI (Formerly LambdaTest)

Welcome to the SmartUI SDK sample for Playwright Python. This repository demonstrates how to integrate SmartUI visual regression testing with Playwright Python.

## Repository Structure

```
smartui-playwright-python-sdk-sample/
├── SmartUI_SDK_LT_hub.py      # Cloud test
├── SmartUI_SDK_local.py        # Local test
├── SmartUI_SDK_Ignore.py       # Example with ignore options
├── requirements.txt             # Python dependencies
└── smartui-web.json             # SmartUI config (create with npx smartui config:create)
```

## 1. Prerequisites and Environment Setup

### Prerequisites

- Python 3.7 or higher
- Node.js (for SmartUI CLI)
- TestMu AI account credentials (for Cloud tests)
- Chrome browser (for Local tests)

### Environment Setup

**For Cloud:**
```bash
export LT_USERNAME='your_username'
export LT_ACCESS_KEY='your_access_key'
export PROJECT_TOKEN='your_project_token'
```

**For Local:**
```bash
export PROJECT_TOKEN='your_project_token'
```

## 2. Initial Setup and Dependencies

### Clone the Repository

```bash
git clone https://github.com/LambdaTest/smartui-playwright-python-sdk-sample
cd smartui-playwright-python-sdk-sample
```

### Install Dependencies

**Recommended: Use a virtual environment** (recommended to avoid dependency conflicts):

**For Python 3.13+** (if you encounter greenlet errors):
```bash
python3 -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
npm install @lambdatest/smartui-cli
pip install playwright lambdatest-playwright-driver lambdatest-sdk-utils
python -m playwright install chromium  # Local only
```

**For Python 3.7-3.12**:
```bash
python3 -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
npm install @lambdatest/smartui-cli
pip install -r requirements.txt
python -m playwright install chromium  # Local only
```

**Dependencies included:**
- `playwright` - Playwright Python library
- `lambdatest-playwright-driver` - SmartUI SDK for Playwright Python
- `lambdatest-sdk-utils` - TestMu AI SDK utilities

### Create SmartUI Configuration

```bash
npx smartui config:create smartui-web.json
```

## 3. Steps to Integrate Screenshot Commands into Codebase

The SmartUI screenshot function is already implemented in the repository.

**Cloud Test** (`SmartUI_SDK_LT_hub.py`):
```python
from lambdatest_playwright_driver import smartui_snapshot

page.goto("https://www.lambdatest.com")
smartui_snapshot(page, "screenshot")
```

**Local Test** (`SmartUI_SDK_local.py`):
```python
from lambdatest_playwright_driver import smartui_snapshot

page.goto("https://www.lambdatest.com")
smartui_snapshot(page, "screenshot")
```

**Note**: The code is already configured and ready to use. You can modify the URL and screenshot name if needed.

## 4. Execution and Commands

**If using a virtual environment**, activate it first:
```bash
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### Local Execution

```bash
npx smartui exec python SmartUI_SDK_local.py
```

### Cloud Execution

```bash
npx smartui exec python SmartUI_SDK_LT_hub.py
```

## Test Files

### Cloud Test (`SmartUI_SDK_LT_hub.py`)

- Connects to TestMu AI Cloud using CDP (Chrome DevTools Protocol)
- Reads credentials from environment variables (`LT_USERNAME`, `LT_ACCESS_KEY`)
- Takes screenshot with name: `screenshot`

### Local Test (`SmartUI_SDK_local.py`)

- Runs Playwright locally using Chromium
- Requires Chrome browser installed
- Takes screenshot with name: `screenshot`

### Ignore Example (`SmartUI_SDK_Ignore.py`)

- Demonstrates how to use ignore options in SmartUI snapshots
- Shows how to exclude specific DOM elements from visual comparison

## View Results

After running the tests, visit your SmartUI project dashboard to view the captured screenshots and compare them with baseline builds.

## More Information

For detailed onboarding instructions, see the [SmartUI Playwright Python Onboarding Guide](https://www.testmuai.com/support/docs/smartui-onboarding-playwright-python/).

## 🚀 LambdaTest is Now TestMu AI

👋 Welcome to TestMu AI, the next evolution of LambdaTest. As of January 2026, [LambdaTest is Now TestMu AI](https://www.testmuai.com/lambdatest-is-now-testmuai/) - we have evolved from a cross-browser testing cloud into a unified, AI-native quality engineering platform designed for the modern DevOps era.

Whether you have been part of the LambdaTest community for years or are just discovering TestMu AI, our mission remains the same: to help you ship faster with high-scale test execution, autonomous testing, and deep quality analytics.

### 🔄 Our Rebrand Journey

In 2017, we introduced LambdaTest with a clear mission: to become the world's most trusted cloud testing platform. We built a scalable, high-performance test cloud that eliminated flakiness, improved developer feedback cycles, and accelerated release velocity for teams worldwide.

As LambdaTest grew, we expanded the platform into Test Intelligence, Visual Regression Testing, Accessibility Testing, API Testing, and Performance Testing, covering the entire testing lifecycle. These capabilities enabled teams to test any stack, on any technology, at enterprise scale.

Over time, we rebuilt the architecture to be AI-native from the ground up. What began as LambdaTest's high-performance testing cloud has now evolved into TestMu AI, an AI-native, multi-agent platform redefining modern quality engineering.

We chose the name TestMu AI to reflect our shift towards intelligent, autonomous testing. While our identity has changed, our core technology and commitment to the testing community stay the same.

👉 Find [LambdaTest's New Home](https://www.testmuai.com/).

### 🔭 Explore TestMu AI

The same infrastructure LambdaTest customers relied on, now delivered through autonomous AI agents.

- [KaneAI](https://www.testmuai.com/kane-ai/)
- [Agent-to-Agent Testing](https://www.testmuai.com/agent-to-agent-testing/)
- [HyperExecute](https://www.testmuai.com/hyperexecute/)
- [Real Device Cloud](https://www.testmuai.com/real-device-cloud/)
- [Pricing](https://www.testmuai.com/pricing/)
- [Documentation](https://www.testmuai.com/support/docs/)
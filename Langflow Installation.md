# 🚀 Langflow Installation Guide (Windows and macOS)
- 🪟 **Windows** (CMD)
- 🍎 **macOS** (Terminal)

We will be using **UV** to install **Langflow**. First, we will install UV, and then proceed with setting up Langflow inside a virtual environment.

---

## 🔧 UV Installation

For detailed instructions, visit the official  <a href="https://docs.astral.sh/uv/getting-started/installation/#installation-methods" target="_blank" rel="noopener noreferrer">UV Installation Guide</a>.



## 📦 Langflow Installation

For installation instructions, visit the <a href="https://docs.langflow.org/get-started-installation" target="_blank" rel="noopener noreferrer">Langflow Installation Guide</a>.

## 🧰 Step-by-Step Setup
### ✅ Step 1: Install UV

Open **CMD** and run the following command:
#### 🪟 Windows (CMD)
```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

#### 🍎 macOS (Terminal)
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

### 🔄 Step 2: Restart Your Terminal or CMD

After installing UV, restart your terminal or CMD to ensure the changes take effect.

### 📁 Step 3: Create a New Directory

Create a new directory called `Langflow` and navigate into it.

#### 🪟 Windows
```cmd
mkdir Langflow
cd Langflow
```

#### 🍎 macOS
```bash
mkdir Langflow
cd Langflow
```
---

### 🧪 Step 4: Create a Virtual Environment Using UV

In the CMD window, run:

```bash
uv venv
```

### ⚙️ Step 5: Activate the Virtual Environment
Activate the environment:
#### 🪟 Windows
```cmd
.venv\Scripts\activate
```

#### 🍎 macOS
```bash
source .venv/bin/activate
```

### 📥 Step 6: Install Langflow in the Virtual Environment
Once activated, install Langflow:
```bash
uv pip install langflow
```

> **Note:** If you encounter any issues during installation, refer to the <a href="https://github.com/AI-CCORE-BOOTCAMP/Week-3/blob/df0a61e4170128844525493dbe638b5ee1fe1a6a/Troubleshooting%20Guide%20.md" target="_blank" rel="noopener noreferrer">Troubleshooting Guide</a>.

### ▶️ Step 7: Run Langflow
To start Langflow, run:
```bash
uv run langflow run
```

### 🧠 Example Output:
📌 Click on the URL shown in the terminal (e.g., http://127.0.0.1:7860) to open Langflow in your default browser.
![Alt Text](https://github.com/AI-CCORE-BOOTCAMP/Week-3/blob/6a38663e689e68c4db3b553fd57f2dbf7dd726d1/Langflow%20Running%20screen%20shot.png)

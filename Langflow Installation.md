# 🚀 Langflow Installation Guide (Windows and macOS)
- 🪟 **Windows** (CMD)
- 🍎 **macOS** (Terminal)


We will be using **UV** to install **Langflow**. First, we will install UV, and then proceed with setting up Langflow inside a virtual environment.

---

## 🔧 UV Installation

For detailed instructions, visit the official [UV Installation Guide](https://astral.sh/uv/install.ps1).

## 📦 Langflow Installation

For installation instructions, visit the [Langflow Installation Guide](https://example.com/langflow-installation-guide).


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

### 📁 Step 2: Create a New Directory

Create a new directory called `Langflow` and navigate into it.

#### 🪟 Windows

You can create and open the folder using **CMD**:

```cmd
mkdir Langflow
cd Langflow
```

#### 🍎 macOS

Use the Terminal to create and enter the folder:

```bash
mkdir Langflow
cd Langflow
```
---


### 🧪 Step 3: Create a Virtual Environment Using UV

In the CMD window, run:

```bash
uv venv
```

### ⚙️ Step 4: Activate the Virtual Environment
Activate the environment:
#### 🪟 Windows
```cmd
.venv\Scripts\activate

```

#### 🍎 macOS

Use the Terminal to create and enter the folder:

```bash
source .venv/bin/activate
```


### 📥 Step 5: Install Langflow in the Virtual Environment
Once activated, install Langflow:
```bash
uv pip install langflow
```


### ▶️ Step 6: Run Langflow
To start Langflow, run:
```bash
uv run langflow run
```

### 🧠 Example Output:
📌 Click on the URL shown in the terminal (e.g., http://127.0.0.1:7860) to open Langflow in your default browser.
![Alt Text](https://github.com/AI-CCORE-BOOTCAMP/Week-3/blob/6a38663e689e68c4db3b553fd57f2dbf7dd726d1/Langflow%20Running%20screen%20shot.png)


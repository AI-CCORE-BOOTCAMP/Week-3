# 🧠 CandidateNameTagger - Custom Langflow Component

The **CandidateNameTagger** is a custom component for [Langflow](https://docs.langflow.org/) designed to enhance data ingestion by attaching the candidate's name as metadata to text chunks extracted from resume files. This is especially useful when storing data in a vector database for semantic search, allowing you to trace chunks back to individual candidates.

---

## 📌 Description

This component extracts the **candidate's name** from the **first line of the first chunk** of each file and applies it as metadata (`candidate_name`) to all subsequent chunks from the same file.

---

## 📁 Use Case

**Recommended Flow:**



```
[File Input] → [Text Splitter] → [CandidateNameTagger] → [Vector DB]
```
---

## 🛠️ How to Create a Custom Component

To create and use the `CandidateNameTagger` component in Langflow:

1. Click on **➕ New Custom Component**, located at the bottom-left of the Langflow screen.
2. Replace the existing code with the following:

    ```python
    from pathlib import Path
    from langflow.custom import Component
    from langflow.io import DataInput, Output
    from langflow.schema import Data

    class CustomComponent(Component):
        display_name = "CandidateNameTagger"
        description = "Extracts candidate name from first chunk per file and applies to all others."
        documentation = "https://docs.langflow.org/components-custom-components"
        icon = "code"
        name = "CustomComponent"

        inputs = [
            DataInput(
                name="input_data",
                display_name="Input Data",
                info="List of Data objects with file_path and resume text",
                is_list=True,
                required=True,
            ),
        ]

        outputs = [
            Output(display_name="Output", name="output", method="build_output"),
        ]

        def build_output(self) -> list[Data]:
            data_objects = self.input_data if isinstance(self.input_data, list) else [self.input_data]
            file_to_candidate = {}

            for data in data_objects:
                file_path = data.data.get("file_path", None)
                file_name = Path(file_path).name if file_path else None

                if file_path:
                    if file_path not in file_to_candidate:
                        # First time this file_path appears: extract candidate name
                        if data.text:
                            candidate_name = data.text.strip().split("\n")[0]
                            file_to_candidate[file_path] = candidate_name
                    # Set candidate_name from lookup (either just stored or from earlier chunk)
                    data.data["candidate_name"] = file_to_candidate.get(file_path, "UNKNOWN")

            self.status = data_objects
            return data_objects
    ```

3. Click **💾 Save** to save the custom component.

---

## 🚀 Using the Component

Once the custom component is created in Langflow:

1. Use this component **after** a **Text Splitter**.
2. Connect its output to a **Vector Store** (e.g., FAISS, Chroma, Pinecone).
3. Each chunk will now include the `candidate_name` in the metadata for improved downstream querying and analysis.

---

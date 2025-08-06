# ⚡ LLM Project Generator
````markdown


Automatically generate project folder structure and code using LLMs via OpenRouter API (supports DeepSeek, Mixtral, Gemma, etc.).

---

## 🚀 Features

- 📁 Auto-creates project folder & files from LLM prompt
- 🧠 Generates full valid code per file (Java, Python, etc.)
- 🤖 Supports multiple OpenRouter LLMs
- 📦 Outputs entire project as a ZIP archive

---

## 🔧 Setup API Key

1. Go to [https://openrouter.ai](https://openrouter.ai)
2. Sign in → Click your avatar → **API Keys**
3. Copy your key (starts with `sk-or-...`)

Then, in your notebook or script:
```python
openrouter_api_key = "sk-or-xxxxxxxxxxxxxxxxxxxx"
````

---

## 🧠 Supported Models

You can use any OpenRouter model. Popular ones:

| Model Name                             | Use Case           |
| -------------------------------------- | ------------------ |
| `deepseek/deepseek-coder:free`         | Full-stack code    |
| `mistralai/mixtral-8x7b-instruct:free` | Reasoning + coding |
| `google/gemma-7b-it:free`              | Lightweight code   |

🔗 Full model list: [https://openrouter.ai/docs#models](https://openrouter.ai/docs#models)

---

## ⚙️ Usage

1. **Define your prompt**

```python
structure_prompt = "Generate file/folder structure for a Spring Boot Book Rental App"
```

2. **Call structure generation**

```python
structure_output = generate_structure_from_prompt(structure_prompt, openrouter_api_key, model="deepseek/deepseek-coder:free")
```

3. **Parse & create empty files**

```python
file_paths = parse_structure_to_list(structure_output)
create_files_from_paths(file_paths)
```

4. **Generate code per file**

```python
generate_code_for_files(file_paths, api_key=openrouter_api_key, model="deepseek/deepseek-coder:free")
```

5. **Save project as ZIP**

```python
save_project_as_zip(base_dir="BookRentalApp")
```

---

## 📁 Output Example

```
BookRentalApp/
├── src/
│   ├── main/
│   │   ├── java/com/example/bookrental/
│   │   │   ├── controller/
│   │   │   ├── service/
│   │   │   └── model/
│   │   └── resources/application.yml
├── pom.xml
```

---

## 📄 License
MIT License © 2025


Let me know if you want this auto-generated during ZIP creation as a file inside the project too (`README.md`).
```

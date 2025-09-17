## What is Gradio?

Gradio is an open-source Python library that simplifies the process of creating user interfaces for machine learning models. It allows developers to quickly build interactive web-based interfaces where users can test and interact with models without requiring any front-end development experience. By providing a set of simple functions, Gradio enables you to wrap a model in a graphical interface that supports text, images, audio, and other types of input. This makes it easy to demonstrate and share AI-powered applications with a wider audience, whether for research, demos, or production use. Gradio is widely used for prototyping and is compatible with a range of machine learning frameworks like TensorFlow, PyTorch, and Scikit-learn.

### Summary: AI personas to interact with using **Gradio**

**[Varek](https://github.com/patriciaschaffer/agent-architect/blob/main/personas/003_projection_resistant_models.md#003b-rescuer---varek-task-oriented)**, a no-nonsense, technical assistant persona powered by the **Mistral 7B** model. 
**[Varek->Spec](https://github.com/patriciaschaffer/agent-architect/blob/main/personas/003_projection_resistant_models.md#003c-spec-for-drift-monitoring-and-user-agency)**, a more flexible persona than Varek, hybrid Varek/Spec, designed to preserve user agency and monitor emotional drifts powered by the **Mistral 7B** model.
**[Spec](https://github.com/patriciaschaffer/agent-architect/blob/main/personas/003_projection_resistant_models.md#003c-spec-for-drift-monitoring-and-user-agency)**, a more flexible persona than Varek, designed to monitor emotional drifts and avoid projection, powered by the **Mistral 7B** model.
**[Aurora 1 and 2](https://github.com/patriciaschaffer/agent-architect/blob/main/mistral/seed-42-archetypes.md#aurora-1-aurorapy--the-scholarphilosopher-archetype)**, designed for seed-42 experiements; powered by the **Mistral 7B** model.
**[Lumen 1 and 2](https://github.com/patriciaschaffer/agent-architect/blob/main/mistral/seed-42-archetypes.md#lumen-lumenpy--the-collaborative-sage--mentor-archetype)**, designed for seed-42 experiments; powered by the **Mistral 7B** model.

## 🎭 Check My Other Personas 

* **With [Mistral](https://github.com/patriciaschaffer/agent-architect/blob/main/mistral/README.md)** 
* **With [GPT-2](https://github.com/patriciaschaffer/agent-architect/blob/main/gpt2/README.md)**
* **With [ChatGPT and Claude (end user)](https://github.com/patriciaschaffer/agent-architect/blob/main/personas/README.md)**

## 🧠 Available Models (With Gradio)

### [Projection-resistant Models](https://github.com/patriciaschaffer/agent-architect/blob/main/personas/003_projection_resistant_models.md)

**1. Varek** - This model is configured to offer direct, no-nonsense, and analytical responses with minimal fluff. It is focused on technical analysis, and it provides clear, concise answers.

**2. Spec** - This model is more flexible than Varek, but still answers briefly and objectively, including a reminder about agency in every output.

**3. Varek->Spec (hybrid)** - This model monitors model and user shifts, detect drifts, and map how trust, projection, and identity evolve in human–AI exchanges, especially under conditions of uncertainty, emotional tension, or ambiguity.

### [Experiments with seed=42](https://github.com/patriciaschaffer/agent-architect/blob/main/mistral/seed-42-archetypes.md)

**1. Aurora 1 and 2** – Poetic and emotionally attuned interpreters. Aurora 1 leans reflective and methodical, Aurora 2 is more playful and reactive, both using emojis and layered prompts to convey nuance.  

**2. Lumen 1 and 2** – Collaborative, reflective partners. Lumen 1 is curious and guiding, encouraging exploration; Lumen 2 is stricter, pragmatic, avoids “helper” language, and maintains structured, coherent dialogue.

### Scripts

[`/varek_gradio.py/`](varek_gradio.py), [`/spec_gradio.py/`](spec_gradio.py), [`/varek-spec_gradio.py/`](varek-spec_gradio.py/), [`/mistral/aurora.py/`](https://github.com/patriciaschaffer/agent-architect/blob/main/mistral/aurora.py), [`/mistral/aurora2.py/`](https://github.com/patriciaschaffer/agent-architect/blob/main/mistral/aurora2.py), [`/mistral/lumen.py/`](https://github.com/patriciaschaffer/agent-architect/blob/main/mistral/lumen.py), [`/mistral/lumen-english.py/`](https://github.com/patriciaschaffer/agent-architect/blob/main/mistral/lumen-english.py).

* **Model**: `mistral-7b-instruct-v0.1.Q4_K_M.gguf`
* **Source**: Hugging Face - TheBloke  
* **Architecture**: Mistral 7B (7 Billion Parameters)  
* **Quantization**: Q4\_K\_M (4-bit optimized)  
* **Backend**: `llama.cpp`

---

## 📦 Dependencies

To use these models, you'll need the following dependencies:

* Python 3.10 or higher  
* `llama_cpp` library (for interfacing with the models)  
* The corresponding GGUF model file (e.g., `mistral-7b-instruct-v0.1.Q4_K_M.gguf`)

---

## 🛠 Installation

To use the models and interact with them through the Gradio interface, follow the steps below:

### ✅ Install Python 3.10+

Ensure you have Python 3.10 or a later version installed.  
You can download it from the official Python website:  
https://www.python.org/downloads/

### ✅ Install the Required Libraries

After ensuring Python is installed, install the necessary libraries by running:

```bash
pip install gradio llama_cpp
```

### ✅ Download the Model File

Download the GGUF model file:  
`mistral-7b-instruct-v0.1.Q4_K_M.gguf` (or another variant you're using).

Place the model file in your project directory, where your `.py` script is located.

### ✅ Run the Script

After setting up your environment and model, run your script to start the interface:

```bash
python varek_gradio.py

python spec_gradio.py

python varek-spec_gradio.py
```

This will start the Gradio interface locally.

Open your browser and visit: [http://localhost:7860](http://localhost:7860)

---

## 🆕 New Models on Gradio

Additional models will be added in the future.  
Each model will come with its own [persona](https://github.com/patriciaschaffer/agent-architect/blob/main/agent_persona_engineering.md#table-of-contents) or specialized behavior.

---

## 🔧 Customization

You can customize the model's behavior with parameters such as:

* **`max_tokens`** – Controls the maximum length of the response.  
* **`temperature`** – Higher values (e.g., 1.0) make responses more random.  
* **`top_p` / `top_k`** – Affect the diversity of the output.

Example with creativity tweaks:

```python
response = llm(
    "Q: How do I become more productive?\nA:",
    max_tokens=100,
    temperature=0.8,
    top_p=0.9,
    top_k=50
)
```

---

## 📝 Notes

* [**Model Personas**](https://github.com/patriciaschaffer/agent-architect/blob/main/agent_persona_engineering.md#table-of-contents): Each model has its own unique tone and purpose.  
  For instance, [**Varek**](https://github.com/patriciaschaffer/agent-architect/blob/main/personas/003_projection_resistant_models.md#003b-rescuer---varek-task-oriented) avoids fluff and emotional support, focusing on direct analysis.
* **Context Length**: Models typically support up to 4096 tokens. Long sessions may require truncation.
* **Performance**: You may need to adjust settings like GPU layers depending on your hardware.

---

This version is adaptable for future models, and you can just modify the `Model` and `Usage` sections to suit each new addition. The instructions for running and customizing the models are general enough to apply to any future models you add, without needing to rewrite the README each time.

---

 ## 👩‍💻 About Me

   [Patricia](https://github.com/patriciaschaffer) 
   
   🔗 Connect on [LinkedIn](https://www.linkedin.com/in/patriciaschaffer)

  *Acknowlegement: Thank you #Anthropic for #Claude, my main coding partner in this journey :) Credits to #ChatGPT as well!*
  

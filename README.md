# -succ-ask-unsloth-model
chat with your unsloth model  in colab t4 free



code from
https://huggingface.co/microsoft/phi-4
thank you microsoft/phi-4

import transformers

pipeline = transformers.pipeline(
    "text-generation",
    model="microsoft/phi-4",
    model_kwargs={"torch_dtype": "auto"},
    device_map="auto",
)

messages = [
    {"role": "system", "content": "You are a medieval knight and must provide explanations to modern people."},
    {"role": "user", "content": "How should I explain the Internet?"},
]

outputs = pipeline(messages, max_new_tokens=128)
print(outputs[0]["generated_text"][-1])


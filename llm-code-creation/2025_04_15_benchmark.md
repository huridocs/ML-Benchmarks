
| Task                     | Best Model (Code) | Best Model (No Code) | Train/Test Size | Inference Time No Code | Best Code Accuracy | Best No Code Accuracy |
|--------------------------|-------------------|----------------------|-----------------|------------------------|--------------------|-----------------------|
| upr_paragraph_countries  | phi4              | qwen2.5-coder:14b    | 43/174          | 16.21                  | 94.25              | 96.17                 |
| upr_paragraph_numbers    | qwen2.5-coder:14b | qwen2.5-coder:14b    | 43/174          | 27.49                  | 100                | 100                   |
| upr_paragraph_text       | qwen2.5-coder:14b | qwen2.5-coder:14b    | 43/174          | 88.53                  | 95.98              | 97.89                 |
| rightstaging_agenda_item | qwen2.5-coder:14b | (not tried)          | 40/160          | -                      | 100                | -                     |
| rightstaging_symbol      | gemma3:12b        | (not tried)          | 40/160          | -                      | 96.88              | -                     |
| rightstaging_title       | (all failed)      | gemma3:12b           | 40/160          | 178.49                 | 0                  | 78.75                 |
| vote_in_favour_english   | (all failed)      | qwen2.5-coder:14b    | 3/12            | 19.07                  | 0                  | 94.45                 |
| vote_against_english     | (all failed)      | qwen2.5-coder:14b    | 3/12            | 7.86                   | 0                  | 91.67                 |
| vote_abstaining_english  | (all failed)      | phi4                 | 3/12            | 12.63                  | 0                  | 88.89                 |




---




Dataset: upr_paragraph_countries

| Model                                  | Train/Test Samples | Rounds | Average Train Time (s) | Best Round Accuracy | Average Accuracy |
|----------------------------------------|--------------------|--------|------------------------|---------------------|------------------|
| qwen2.5-coder:14b (no code, new lines) | 43/174             | 3      | 16.59                  | 96.55               | 96.17            |
| gemma3:12b (no code, new lines)        | 43/174             | 3      | 61.76                  | 95.98               | 95.98            |
| qwen2.5-coder:14b (no code)            | 43/174             | 3      | 10.95                  | 95.98               | 95.21            |
| phi4 (no code, new lines)              | 43/174             | 3      | 23.75                  | 96.55               | 94.64            |
| phi4                                   | 43/174             | 3      | 102.05                 | 95.4                | 94.25            |
| phi4 (new lines)                       | 43/174             | 3      | 170.32                 | 94.25               | 93.1             |
| qwen2.5-coder:14b                      | 43/174             | 3      | 66.38                  | 93.1                | 92.91            |
| qwen2.5-coder:14b (new lines)          | 43/174             | 3      | 119.04                 | 93.1                | 91.95            |
| gemma3:12b                             | 43/174             | 3      | 700.07                 | 94.25               | 91.95            |
| gemma3:12b (new lines)                 | 43/174             | 3      | 114.26                 | 91.38               | 90.42            |
| phi4 (no code)                         | 43/174             | 3      | -                      | Failing             | Failing          |
| gemma3:12b (no code)                   | 43/174             | 3      | -                      | Failing             | Failing          |


---

Dataset: upr_paragraph_numbers

| Model                       | Train/Test Samples | Rounds | Average Train Time (s) | Best Round Accuracy | Average Accuracy |
|-----------------------------|--------------------|--------|------------------------|---------------------|------------------|
| qwen2.5-coder:14b           | 43/174             | 3      | 3.56                   | 100                 | 100              |
| gemma3:12b                  | 43/174             | 3      | 4.11                   | 100                 | 100              |
| qwen2.5-coder:14b (no code) | 43/174             | 3      | 6.94                   | 100                 | 100              |
| gemma3:12b (no code)        | 43/174             | 3      | 8.13                   | 100                 | 100              |
| phi4                        | 43/174             | 3      | 13.53                  | 100                 | 100              |
| phi4 (no code)              | 43/174             | 3      | 8.01                   | 98.85               | 98.66            |


---

Dataset: upr_paragraph_text

| Model                       | Train/Test Samples | Rounds | Average Train Time (s) | Best Round Accuracy | Average Accuracy |
|-----------------------------|--------------------|--------|------------------------|---------------------|------------------|
| qwen2.5-coder:14b (no code) | 43/174             | 3      | 20.54                  | 98.28               | 97.89            |
| qwen2.5-coder:14b           | 43/174             | 3      | 7.57                   | 95.98               | 95.98            |
| phi4                        | 43/174             | 3      | 42.8                   | 94.25               | 94.25            |
| phi4 (no code)              | 43/174             | 3      | 192.79                 | 92.53               | 90.04            |
| gemma3:12b (no code)        | 43/174             | 3      | 162.46                 | 94.83               | 90.04            |
| gemma3:12b                  | 43/174             | 3      | 73.97                  | 94.25               | 62.83            |


---

Dataset: rightstaging_agenda_item

| Model             | Train/Test Samples | Rounds | Average Train Time (s) | Best Round Accuracy | Average Accuracy |
|-------------------|--------------------|--------|------------------------|---------------------|------------------|
| qwen2.5-coder:14b | 40/160             | 3      | 3.97                   | 100                 | 100              |
| phi4              | 40/160             | 3      | 15.77                  | 100                 | 99.79            |
| gemma3:12b        | 40/160             | 3      | 94.83                  | 100                 | 77.5             |


---

Dataset: rightstaging_symbol

| Model             | Train/Test Samples | Rounds | Average Train Time (s) | Best Round Accuracy | Average Accuracy |
|-------------------|--------------------|--------|------------------------|---------------------|------------------|
| gemma3:12b        | 40/160             | 3      | 11.99                  | 96.88               | 96.88            |
| phi4              | 40/160             | 3      | 33.24                  | 96.88               | 96.46            |
| qwen2.5-coder:14b | 40/160             | 3      | 14.98                  | 95.62               | 95.21            |


---

Dataset: rightstaging_title

| Model                       | Train/Test Samples | Rounds | Average Train Time (s) | Best Round Accuracy | Average Accuracy |
|-----------------------------|--------------------|--------|------------------------|---------------------|------------------|
| gemma3:12b (no code)        | 40/160             | 3      | 285                    | 80                  | 78.75            |
| qwen2.5-coder:14b (no code) | 40/160             | 3      | 371.07                 | 74.38               | 72.29            |
| phi4 (no code)              | 40/160             | 3      | 396.19                 | 70.62               | 69.37            |


---

Dataset: vote_in_favour_english

| Model                                  | Train/Test Samples | Rounds | Average Train Time (s) | Average Inference Time (s) | Best Round Accuracy | Average Accuracy |
|----------------------------------------|--------------------|--------|------------------------|----------------------------|---------------------|------------------|
| qwen2.5-coder:14b (no code, new lines) | 3/12               | 3      | 10.03                  | 19.07                      | 100                 | 94.45            |
| phi4 (no code, new lines)              | 3/12               | 3      | 6.35                   | 18.54                      | 100                 | 91.67            |
| qwen2.5-coder:14b (no code)            | 3/12               | 3      | 8.17                   | 19.81                      | 100                 | 91.67            |
| gemma3:12b (no code, new lines)        | 3/12               | 3      | 11.84                  | 20.15                      | 91.67               | 91.67            |
| gemma3:12b                             | 3/12               | 3      | -                      | -                          | 0                   | 0                |
| qwen2.5-coder:14b                      | 3/12               | 3      | -                      | -                          | 0                   | 0                |
| phi4                                   | 3/12               | 3      | -                      | -                          | 0                   | 0                |
| phi4 (no code)                         | 3/12               | 3      | -                      | -                          | Failing             | Failing          |
| gemma3:12b (no code)                   | 3/12               | 3      | -                      | -                          | Failing             | Failing          |


---

Dataset: vote_against_english

| Model                                  | Train/Test Samples | Rounds | Average Train Time (s) | Average Inference Time (s) | Best Round Accuracy | Average Accuracy |
|----------------------------------------|--------------------|--------|------------------------|----------------------------|---------------------|------------------|
| qwen2.5-coder:14b (no code, new lines) | 3/12               | 3      | 1.1                    | 7.86                       | 100                 | 91.67            |
| qwen2.5-coder:14b (no code)            | 3/12               | 3      | 1.44                   | 10.22                      | 91.67               | 91.67            |
| gemma3:12b (no code, new lines)        | 3/12               | 3      | 2.11                   | 10.45                      | 91.67               | 88.89            |
| phi4 (no code, new lines)              | 3/12               | 3      | 1.83                   | 8.75                       | 83.33               | 80.55            |
| gemma3:12b                             | 3/12               | 3      | -                      | -                          | 0                   | 0                |
| qwen2.5-coder:14b                      | 3/12               | 3      | -                      | -                          | 0                   | 0                |
| phi4                                   | 3/12               | 3      | -                      | -                          | 0                   | 0                |
| phi4 (no code)                         | 3/12               | 3      | -                      | -                          | Failing             | Failing          |
| gemma3:12b (no code)                   | 3/12               | 3      | -                      | -                          | Failing             | Failing          |


---

Dataset: vote_abstaining_english

| Model                                  | Train/Test Samples | Rounds | Average Train Time (s) | Average Inference Time (s) | Best Round Accuracy | Average Accuracy |
|----------------------------------------|--------------------|--------|------------------------|----------------------------|---------------------|------------------|
| phi4 (no code, new lines)              | 3/12               | 3      | 2.5                    | 12.63                      | 91.67               | 88.89            |
| gemma3:12b (no code, new lines)        | 3/12               | 3      | 2.91                   | 14.83                      | 91.67               | 83.33            |
| qwen2.5-coder:14b (no code, new lines) | 3/12               | 3      | 2.61                   | 13.34                      | 83.33               | 72.22            |
| qwen2.5-coder:14b (no code)            | 3/12               | 3      | 3.21                   | 18.05                      | 75                  | 66.67            |
| gemma3:12b                             | 3/12               | 3      | -                      | -                          | 0                   | 0                |
| qwen2.5-coder:14b                      | 3/12               | 3      | -                      | -                          | 0                   | 0                |
| phi4                                   | 3/12               | 3      | -                      | -                          | 0                   | 0                |
| phi4 (no code)                         | 3/12               | 3      | -                      | -                          | Failing             | Failing          |
| gemma3:12b (no code)                   | 3/12               | 3      | -                      | -                          | Failing             | Failing          |


---



- qwen2.5-coder:14b model is the better option most of the time, it's more consistent than the others.
- The models create different answers on each run, even though I use the same seed to split the data.
- In addition to above models, I have also tried models like deepcoder:14b, deepseek-coder:6.7b or like exaone-deep but they get stuck a lot or they do not perform well at all.
So I have only included the best 3 models to not complicate the results.
- When the labels are multi option (i.e. the output is a list of strings), and when I try to get the answers directly from the model, 
only the qwen2.5-coder:14b model is able to return the output in the correct format. Other models sometimes are not able to create a list of strings properly.
- To solve the above issue with the multi option labels, I have also tried to get the answers each label in a new line, instead of a list of strings, and it improved the results.
- Performance in "rightstaging_title" looks like a bit lower than the other tasks but actually they are not that bad as they seem.
The models just add some simple stuff - a few words from the following segment or something, but it's not that critical.


PROMPT:


    def get_prompt(examples: list[LabeledDataSample]):
        options = json.loads(Path(ROOT_PATH, "data/upr/upr_paragraph_countries/options.json").read_text())
        options_string = ",\n".join([o for o in options])
    
        examples_string = "**Examples**\n"
        for sample_index, sample in enumerate(examples):
            examples_string += f"**Example {sample_index+1}**\n"
            examples_string += "Input:\n"
            examples_string += f'"{sample.text}"\n\n'
            examples_string += "Output:\n"
            examples_string += f"{sample.label}\n\n"
    
        prompt = f"""**Task**  
    We have a set of example inputs and the corresponding outputs. These examples illustrate how we want to transform the input data to the output data. Your goal is to figure out the pattern or logic from these examples and write a self-contained Python function that reproduces this behavior.
    
    We do not provide an explicit list of rules. Instead, use the examples to infer how the input should be processed to create the output. If the pattern does not clearly match some new input, your function may return `None` or an empty string, but it should handle the provided examples correctly.  
    
    {examples_string}
    
    **Requirements**  
    1. Write your solution as a single Python function named `extract(text: str)`. No additional arguments should be required.  
       2. In your solution, you may apply any logic needed to extract, parse, or process the input so that it matches how each example is transformed to its output.  
       3. If no valid transformation or pattern is found, return `None` or an empty string.  
       4. Only return your function definition. No additional commentary, test calls, or example usage should appear outside the code block.  
       5. Your code should be standalone and use only standard Python 3 libraries without external dependencies.
    
    
    **Output Selection**
    
    The code can *only* return elements from the following list and every element can be selected *only* once:
    
    [
        {options_string}
    ]
    
    
    **Output Format**  
    Return the function definition *only*, wrapped in fenced code blocks using Python syntax. For example:
    
    ```python
    def extract(text: str):
        # Your logic here
    ```
    
    No explanatory text or test calls should appear outside of that code block."""
    
        return prompt


NO CODE PROMPT:

    def get_prompt(examples: list[LabeledDataSample], new_sample: LabeledDataSample):
        options = json.loads(Path(ROOT_PATH, "data/upr/upr_paragraph_countries/options.json").read_text())
        options_string = ",\n".join([o for o in options])
    
        examples_string = "**Examples**\n"
        for sample_index, sample in enumerate(examples):
            examples_string += f"**Example {sample_index+1}**\n"
            examples_string += "Input:\n"
            examples_string += f'"{sample.text}"\n\n'
            examples_string += "Output:\n"
            examples_string += f"{sample.label}\n\n"
    
        prompt = f"""**Task**  
    You are presented with a pattern recognition challenge. Your goal is to:
    1. Carefully analyze the relationship between inputs and outputs in the provided examples
       2. Identify the underlying transformation pattern
       3. Apply the same pattern to the new input
    
    {examples_string}
    
    **Important Instructions**
    1. First, analyze what changes between input and output in each example
       2. Look for consistent patterns across all examples:
          - Text transformations
          - Word or character-level changes
          - Structural modifications
          - Content extraction rules
       3. Verify that your pattern works consistently across all examples
       4. Apply the exact same transformation to the new input
    
    **Requirements**
    1. Provide ONLY the final output as a plain text
       2. Do not include any explanations or reasoning
       3. Do not add any external information not derived from the input
       4. Follow the exact same pattern as shown in the examples
       5. Maintain consistency with the output format shown in examples
    
    
    **Output Selection**
    
    The code can **only** return elements from the following list and every element can be selected **only** once:
    
    [
        {options_string}
    ]
    
    
    Here is the new input sample that you are going to find the answer from:
    
    {new_sample.text}
    
    Output:
    """
    
        return prompt




To get the every prediction in new line:

        examples_string = "**Examples**\n"
    for sample_index, sample in enumerate(examples):
        examples_string += f"**Example {sample_index+1}**\n"
        examples_string += "Input:\n"
        examples_string += f'"{sample.text}"\n\n'
        examples_string += "Output:\n"
        for country in sample.label:
            examples_string += f"{country}\n"
        examples_string += "\n\n"

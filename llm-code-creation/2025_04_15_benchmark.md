
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

| Model                                  | Train/Test Samples | Rounds | Average Train Time (s) | Average Inference Time (s) | Best Round Accuracy | Average Accuracy |
|----------------------------------------|--------------------|--------|------------------------|----------------------------|---------------------|------------------|
| llama3.3 (70b) (no code, new lines)    | 43/174             | 3      | 674.43                 |                            | 97.13               | 97.13            |
| cogito:70b (no code, new lines)        | 43/174             | 3      | 516.54                 |                            | 96.55               | 96.36            |
| qwen2.5-coder:14b (no code, new lines) | 43/174             | 3      | 16.59                  |                            | 96.55               | 96.17            |
| gemma3:12b (no code, new lines)        | 43/174             | 3      | 61.76                  |                            | 95.98               | 95.98            |
| qwen2.5-coder:14b (no code)            | 43/174             | 3      | 10.95                  |                            | 95.98               | 95.21            |
| phi4 (no code, new lines)              | 43/174             | 3      | 23.75                  |                            | 96.55               | 94.64            |
| phi4                                   | 43/174             | 3      | 102.05                 |                            | 95.4                | 94.25            |
| phi4 (new lines)                       | 43/174             | 3      | 170.32                 |                            | 94.25               | 93.1             |
| qwen2.5-coder:14b                      | 43/174             | 3      | 66.38                  |                            | 93.1                | 92.91            |
| qwen2.5-coder:14b (new lines)          | 43/174             | 3      | 119.04                 |                            | 93.1                | 91.95            |
| gemma3:12b                             | 43/174             | 3      | 700.07                 |                            | 94.25               | 91.95            |
| gemma3:12b (new lines)                 | 43/174             | 3      | 114.26                 |                            | 91.38               | 90.42            |
| phi4 (no code)                         | 43/174             | 3      | -                      |                            | Failing             | Failing          |
| gemma3:12b (no code)                   | 43/174             | 3      | -                      |                            | Failing             | Failing          |

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
| llama3.3 (70b) (no code)    | 43/174             | 3      | 925.76                 | 98.28               | 98.09            |
| qwen2.5-coder:14b (no code) | 43/174             | 3      | 20.54                  | 98.28               | 97.89            |
| qwen2.5-coder:14b           | 43/174             | 3      | 7.57                   | 95.98               | 95.98            |
| phi4                        | 43/174             | 3      | 42.8                   | 94.25               | 94.25            |
| phi4 (no code)              | 43/174             | 3      | 192.79                 | 92.53               | 90.04            |
| gemma3:12b (no code)        | 43/174             | 3      | 162.46                 | 94.83               | 90.04            |
| gemma3:12b                  | 43/174             | 3      | 73.97                  | 94.25               | 62.83            |


---

Dataset: rightstaging_agenda_item

| Model                                  | Train/Test Samples | Rounds | Average Train Time (s) | Average Inference Time (s) | Best Round Accuracy | Average Accuracy |
|----------------------------------------|--------------------|--------|------------------------|----------------------------|---------------------|------------------|
| qwen2.5-coder:14b                      | 40/160             | 3      | 3.97                   |                            | 100                 | 100              |
| llama3.3 (70b)                         | 40/160             | 1      | 221.26                 |                            | 100                 | 100              |
| phi4                                   | 40/160             | 3      | 15.77                  |                            | 100                 | 99.79            |
| gemma3:4b (no code, new lines)         | 40/160             | 3      | 31.62                  | 33.35                      | 98.12               | 98.12            |
| llama3.2 (3b) (no code, new lines)     | 40/160             | 3      | 3.03                   | 10.95                      | 97.5                | 97.29            |
| cogito:3b (no code, new lines)         | 40/160             | 3      | 35.5                   | 16.13                      | 95                  | 90.62            |
| granite3.3 (8b) (no code, new lines)   | 40/160             | 3      | 165.25                 | 158.07                     | 91.25               | 89.17            |
| gemma3:12b                             | 40/160             | 3      | 94.83                  |                            | 100                 | 77.5             |
| gemma3:1b (no code, new lines)         | 40/160             | 3      | 45.39                  | 21.41                      | 66.26               | 63.96            |
| granite3.3:2b (no code, new lines)     | 40/160             | 3      | 77.47                  | 16.82                      | 70                  | 60.42            |



---

Dataset: rightstaging_symbol

| Model                                  | Train/Test Samples | Rounds | Average Train Time (s) | Average Inference Time (s) | Best Round Accuracy | Average Accuracy |
|----------------------------------------|--------------------|--------|------------------------|----------------------------|---------------------|------------------|
| granite3.3 (8b) (no code, new lines)   | 40/160             | 3      | 24.33                  | 30.01                      | 100                 | 98.75            |
| gemma3:4b (no code, new lines)         | 40/160             | 3      | 13.92                  | 33.51                      | 99.38               | 98.13            |
| gemma3:12b                             | 40/160             | 3      | 11.99                  |                            | 96.88               | 96.88            |
| llama3.3 (70b)                         | 40/160             | 3      | 144.36                 |                            | 96.88               | 96.88            |
| phi4                                   | 40/160             | 3      | 33.24                  |                            | 96.88               | 96.46            |
| llama3.2 (3b) (no code, new lines)     | 40/160             | 3      | 12.64                  | 11.82                      | 97.5                | 95.42            |
| qwen2.5-coder:14b                      | 40/160             | 3      | 14.98                  |                            | 95.62               | 95.21            |
| cogito:3b (no code, new lines)         | 40/160             | 3      | 32.66                  | 17.88                      | 91.88               | 90.42            |
| granite3.3:2b (no code, new lines)     | 40/160             | 3      | 54.24                  | 24.28                      | 95                  | 87.71            |
| gemma3:1b (no code, new lines)         | 40/160             | 3      | 44.21                  | 27.07                      | 63.75               | 58.54            |


---

Dataset: rightstaging_title

| Model                       | Train/Test Samples | Rounds | Average Train Time (s) | Best Round Accuracy | Average Accuracy |
|-----------------------------|--------------------|--------|------------------------|---------------------|------------------|
| llama3.3 (no code)          | 40/160             | 1      | 4318.36                | 87.5                | 87.5             |
| gemma3:12b (no code)        | 40/160             | 3      | 285                    | 80                  | 78.75            |
| qwen2.5-coder:14b (no code) | 40/160             | 3      | 371.07                 | 74.38               | 72.29            |
| phi4 (no code)              | 40/160             | 3      | 396.19                 | 70.62               | 69.37            |


---

Dataset: vote_in_favour_english

| Model                                  | Train/Test Samples | Rounds | Average Train Time (s) | Average Inference Time (s) | Best Round Accuracy | Average Accuracy |
|----------------------------------------|--------------------|--------|------------------------|----------------------------|---------------------|------------------|
| llama3.3 (70b) (no code)               | 3/12               | 3      | 182.8                  | 577.09                     | 100                 | 100              |
| qwen2.5-coder:14b (no code, new lines) | 3/12               | 3      | 10.03                  | 19.07                      | 100                 | 94.45            |
| phi4 (no code, new lines)              | 3/12               | 3      | 6.35                   | 18.54                      | 100                 | 91.67            |
| qwen2.5-coder:14b (no code)            | 3/12               | 3      | 8.17                   | 19.81                      | 100                 | 91.67            |
| gemma3:12b (no code, new lines)        | 3/12               | 3      | 11.84                  | 20.15                      | 91.67               | 91.67            |
| cogito:70b (no code, new lines)        | 3/12               | 3      | 145.77                 | 466.54                     | 100                 | 91.67            |
| gemma3:4b (no code, new lines)         | 3/12               | 3      | 4.11                   | 8.36                       | 91.67               | 88.89            |
| llama3.2 (3b) (no code, new lines)     | 3/12               | 3      | 1.86                   | 6.66                       | 58.33               | 47.22            |
| granite3.3 (8b) (no code, new lines)   | 3/12               | 3      | 8.17                   | 17.13                      | 50                  | 47.22            |
| gemma3:1b (no code, new lines)         | 3/12               | 3      | 1.26                   | 4.44                       | 33.33               | 25               |
| granite3.3:2b (no code, new lines)     | 3/12               | 3      | 4.07                   | 8.74                       | 41.67               | 25               |
| cogito:3b (no code, new lines)         | 3/12               | 3      | 6.21                   | 193.96                     | 0                   | 0                |
| gemma3:12b                             | 3/12               | 3      | -                      | -                          | 0                   | 0                |
| qwen2.5-coder:14b                      | 3/12               | 3      | -                      | -                          | 0                   | 0                |
| phi4                                   | 3/12               | 3      | -                      | -                          | 0                   | 0                |
| phi4 (no code)                         | 3/12               | 3      | -                      | -                          | Failing             | Failing          |
| gemma3:12b (no code)                   | 3/12               | 3      | -                      | -                          | Failing             | Failing          |


---

Dataset: vote_against_english

| Model                                  | Train/Test Samples | Rounds | Average Train Time (s) | Average Inference Time (s) | Best Round Accuracy | Average Accuracy |
|----------------------------------------|--------------------|--------|------------------------|----------------------------|---------------------|------------------|
| llama3.3 (70b) (no code)               | 3/12               | 3      | 22.96                  | 131.6                      | 100                 | 100              |
| cogito:70b (no code, new lines)        | 3/12               | 3      | 25.47                  | 169.87                     | 100                 | 100              |
| qwen2.5-coder:14b (no code, new lines) | 3/12               | 3      | 1.1                    | 7.86                       | 100                 | 91.67            |
| qwen2.5-coder:14b (no code)            | 3/12               | 3      | 1.44                   | 10.22                      | 91.67               | 91.67            |
| gemma3:12b (no code, new lines)        | 3/12               | 3      | 2.11                   | 10.45                      | 91.67               | 88.89            |
| phi4 (no code, new lines)              | 3/12               | 3      | 1.83                   | 8.75                       | 83.33               | 80.55            |
| granite3.3:2b (no code, new lines)     | 3/12               | 3      | 3.18                   | 7.8                        | 41.67               | 38.89            |
| llama3.2 (3b) (no code, new lines)     | 3/12               | 3      | 0.63                   | 2.25                       | 41.67               | 33.33            |
| gemma3:4b (no code, new lines)         | 3/12               | 3      | 1.17                   | 4.67                       | 33.33               | 33.33            |
| granite3.3 (8b) (no code, new lines)   | 3/12               | 3      | 2.81                   | 10.16                      | 25                  | 16.67            |
| cogito:3b (no code, new lines)         | 3/12               | 3      | 0.87                   | 3.78                       | 66.67               | 44.44            |
| gemma3:1b (no code, new lines)         | 3/12               | 3      | 1.98                   | 4.2                        | 0                   | 0                |
| gemma3:12b                             | 3/12               | 3      | -                      | -                          | 0                   | 0                |
| qwen2.5-coder:14b                      | 3/12               | 3      | -                      | -                          | 0                   | 0                |
| phi4                                   | 3/12               | 3      | -                      | -                          | 0                   | 0                |
| cogito:70b (no code)                   | 3/12               | 3      | -                      | -                          | Failing             | Failing          |
| phi4 (no code)                         | 3/12               | 3      | -                      | -                          | Failing             | Failing          |
| gemma3:12b (no code)                   | 3/12               | 3      | -                      | -                          | Failing             | Failing          |


---

Dataset: vote_abstaining_english

| Model                                  | Train/Test Samples | Rounds | Average Train Time (s) | Average Inference Time (s) | Best Round Accuracy | Average Accuracy |
|----------------------------------------|--------------------|--------|------------------------|----------------------------|---------------------|------------------|
| cogito:70b (no code, new lines)        | 3/12               | 3      | 61.54                  | 270.43                     | 100                 | 100              |
| llama3.3 (70b) (no code, new lines)    | 3/12               | 3      | 68.76                  | 270.94                     | 100                 | 100              |
| phi4 (no code, new lines)              | 3/12               | 3      | 2.5                    | 12.63                      | 91.67               | 88.89            |
| gemma3:12b (no code, new lines)        | 3/12               | 3      | 2.91                   | 14.83                      | 91.67               | 83.33            |
| qwen2.5-coder:14b (no code, new lines) | 3/12               | 3      | 2.61                   | 13.34                      | 83.33               | 72.22            |
| qwen2.5-coder:14b (no code)            | 3/12               | 3      | 3.21                   | 18.05                      | 75                  | 66.67            |
| granite3.3 (8b) (no code, new lines)   | 3/12               | 3      | 6.13                   | 11.66                      | 58.33               | 50               |
| cogito:3b (no code, new lines)         | 3/12               | 3      | 2.98                   | 5.1                        | 16.67               | 11.11            |
| llama3.2 (3b) (no code, new lines)     | 3/12               | 3      | 2.18                   | 3.12                       | 16.67               | 5.56             |
| gemma3:4b (no code, new lines)         | 3/12               | 3      | 5.69                   | 7.09                       | 0                   | 0                |
| gemma3:1b (no code, new lines)         | 3/12               | 3      | 2.23                   | 8.23                       | 0                   | 0                |
| granite3.3:2b (no code, new lines)     | 3/12               | 3      | 12.65                  | 32.88                      | 0                   | 0                |
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


CODE PROMPT:


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



Get mistake indexes:

    def get_mistake_indexes(expected_output: list[str], actual_output: list[str], visualize: bool = True):
        mistake_indexes = []
        result_string = ""

        for i in range(len(expected_output)):
            if expected_output[i] == actual_output[i]:
                result_string += '\033[94m"' + str(expected_output[i]) + '", \033[0m'
            else:
                mistake_indexes.append(i)
                result_string += (
                    "\033[91m" + str(actual_output[i]) + "\033[0m" + f"\033[93m{str(expected_output[i])}, \033[0m" + "\033[0m"
                )

        if visualize:
            print(f"Result:\n{result_string}\n")

        return mistake_indexes


Execute code on the fly:

    def execute_function(code: str, function_name: str = None, *args, **kwargs):
        namespace = {}
        try:
            exec(code, namespace)

            if function_name is None:
                import re

                match = re.search(r"def\s+(\w+)\s*\(", code)
                if match:
                    function_name = match.group(1)
                else:
                    return {"success": False, "result": None, "error": "Could not find function name in code"}

            func = namespace[function_name]
            result = func(*args, **kwargs)
            if not result:
                result = None
            return {"success": True, "result": result, "error": None}

        except Exception as e:
            return {"success": False, "result": None, "error": str(e)}



    def get_model_answer(examples: list[LabeledDataSample], model: str) -> str:
        client = Client()
        prompt = get_prompt(examples)
        response = client.chat(model=model, messages=[{"role": "user", "content": prompt}])
        answer: str = response["message"]["content"]
        code_start = "```python\n"
        code_end = "```"
        code_part = answer[answer.find(code_start) + len(code_start) : answer.rfind(code_end)]
        return code_part


    def get_actual_output(code_to_execute: str, data: LabeledData) -> list[str]:
        actual_output = []
        for sample in data.samples:
            function_return = execute_function(code_to_execute, "extract", sample.text)
            if not function_return["success"]:
                actual_output.append("FAIL")
                continue
            actual_output.append(function_return["result"])
        return actual_output


    def update_examples(example_indexes, examples, mistake_indexes, train_data) -> bool:
        new_example_added = False
        for i in mistake_indexes:
            if i not in example_indexes:
                examples.append(train_data.samples[i])
                example_indexes.append(i)
                new_example_added = True
                break
        return new_example_added
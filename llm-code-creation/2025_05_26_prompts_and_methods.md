Example Prompt:

    '**Task**  \nWe have a set of example inputs and the corresponding outputs. These examples illustrate how we want to transform the input data to the output data. Your goal is to figure out the pattern or logic from these examples and write a self-contained Python function that reproduces this behavior.\n\nWe do not provide an explicit list of rules. Instead, use the examples to infer how the input should be processed to create the output. If the pattern does not clearly match some new input, your function may return `None` or an empty string, but it should handle the provided examples correctly.  \n\n**Examples**\n**Example 1**\nInput:\n"118.169 Continue efforts to end all forms of discrimination and violence against women and girls (Tunisia);"\n\nOutput:\n[\'Tunisia\']\n\n**Example 2**\nInput:\n"118.31 Ratify and fully align its national legislation with all the obligations under the Rome Statute of the International Criminal Court, as previously recommended (Latvia);"\n\nOutput:\n[\'Latvia\']\n\n**Example 3**\nInput:\n"118.7 Ratify the Second Optional Protocol to the International Covenant on Civil and Political Rights, aiming at the abolition of the death penalty (Argentina) (Cote d\'Ivoire) (Namibia) (Togo);"\n\nOutput:\n[\'Argentina\', "Cote d\'Ivoire", \'Namibia\', \'Togo\']\n\n\n\n**Requirements**  \n1. Write your solution as a single Python function named `extract(text: str)`. No additional arguments should be required.  \n2. In your solution, you may apply any logic needed to extract, parse, or process the input so that it matches how each example is transformed to its output.  \n3. If no valid transformation or pattern is found, return `None` or an empty string.  \n4. Only return your function definition. No additional commentary, test calls, or example usage should appear outside the code block.  \n5. Your code should be standalone and use only standard Python 3 libraries without external dependencies.\n\n\n**Output Selection**\n\nThe code can *only* return elements from the following list and every element can be selected *only* once:\n\n[\n    Afghanistan,\nAlbania,\nAlgeria,\nAndorra,\nAngola,\nAntigua and Barbuda,\nArgentina,\nArmenia,\nAustralia,\nAustria,\nAzerbaijan,\nBahamas,\nBahrain,\nBangladesh,\nBarbados,\nBelarus,\nBelgium,\nBelize,\nBenin,\nBhutan,\nBolivia,\nBosnia and Herzegovina,\nBotswana,\nBrazil,\nBrunei Darussalam,\nBulgaria,\nBurkina Faso,\nBurundi,\nCambodia,\nCameroon,\nCanada,\nCape Verde,\nCentral African Republic,\nChad,\nChile,\nChina,\nColombia,\nComoros,\nCosta Rica,\nCote d\'Ivoire,\nCroatia,\nCuba,\nCyprus,\nCzechia,\nDemocratic Republic of the Congo,\nDenmark,\nDjibouti,\nDominica,\nDominican Republic,\nDPR Korea,\nEcuador,\nEgypt,\nEl Salvador,\nEquatorial Guinea,\nEritrea,\nEstonia,\nEthiopia,\nFiji,\nFinland,\nFrance,\nGabon,\nGambia,\nGeorgia,\nGermany,\nGhana,\nGreece,\nGrenada,\nGuatemala,\nGuinea,\nGuinea Bissau,\nGuyana,\nHaiti,\nHoly See,\nHonduras,\nHungary,\nIceland,\nIndia,\nIndonesia,\nIran,\nIraq,\nIreland,\nIsrael,\nItaly,\nJamaica,\nJapan,\nJordan,\nKazakhstan,\nKenya,\nKiribati,\nKuwait,\nKyrgyzstan,\nLaos,\nLatvia,\nLebanon,\nLesotho,\nLiberia,\nLibya,\nLiechtenstein,\nLithuania,\nLuxembourg,\nMacedonia FYR,\nMadagascar,\nMalawi,\nMalaysia,\nMaldives,\nMali,\nMalta,\nMarshall Islands,\nMauritania,\nMauritius,\nMexico,\nMicronesia,\nMoldova,\nMonaco,\nMongolia,\nMontenegro,\nMorocco,\nMozambique,\nMyanmar,\nNamibia,\nNauru,\nNepal,\nNetherlands,\nNew Zealand,\nNicaragua,\nNiger,\nNigeria,\nNorway,\nOman,\nPakistan,\nPalau,\nPalestine,\nPanama,\nPapua New Guinea,\nParaguay,\nPeru,\nPhilippines,\nPoland,\nPortugal,\nQatar,\nRepublic of the Congo,\nRepublic of Korea,\nRomania,\nRussian Federation,\nRwanda,\nSamoa,\nSan Marino,\nSao Tome & Principe,\nSaudi Arabia,\nSenegal,\nSerbia,\nSeychelles,\nSierra Leone,\nSingapore,\nSlovakia,\nSlovenia,\nSolomon Islands,\nSomalia,\nSouth Africa,\nSouth Sudan,\nSpain,\nSri Lanka,\nSt Kitts & Nevis,\nSt Lucia,\nSt Vincent & the Grenadines,\nSudan,\nSuriname,\nEswatini,\nSweden,\nSwitzerland,\nSyria,\nTajikistan,\nTanzania,\nThailand,\nTimor-Leste,\nTogo,\nTonga,\nTrinidad and Tobago,\nTunisia,\nTurkey,\nTurkmenistan,\nTuvalu,\nUganda,\nUkraine,\nUnited Arab Emirates,\nUnited Kingdom,\nUnited States,\nUruguay,\nUzbekistan,\nVanuatu,\nVenezuela,\nViet Nam,\nYemen,\nZambia,\nZimbabwe,\n&#40;Unknown&#41;\n]\n\n\n**Output Format**  \nReturn the function definition *only*, wrapped in fenced code blocks using Python syntax. For example:\n\n```python\ndef extract(text: str):\n    # Your logic here\n```\n\nNo explanatory text or test calls should appear outside of that code block.'


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
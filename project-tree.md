- src

    - experiments finetuning LLM models
        - Juptyer notebook that runs the finetuning and saves the model and metrics. it should utilize https://github.com/hiyouga/LlamaFactory so make sure to follow instructions there for setup and usage. it should first run data_train_formatting to make sure that we have the data formatted and ready for training.
        - llm_inference
            * class for loading existing ocr models and using them directly without finetuning 
                * using the following repo https://github.com/hiyouga/LlamaFactory
                * should be able to select model type 
            * input: model name, expected API in .env file
            * methods: generate response

    - Juptyer notebook that runs the inference on one sample. and runs inference on all test samples and saves results in one json file

    - Evaluation docker image
        * Build a docker image for this project https://github.com/openai/human-eval/tree/master
        * I should be able to run and test this docker image manually and using also gVisor
        * It should utilize the output json file by the inference jupyter notebook for the LLM output functions
        * It should output the evaluation results in a json file

    - Juptyer notebook that takes the output of my previous docker image and shows the results in a readable format


- data_utils
        
    - llm_data_train_formatting
        * class for formatting data for training using LlamaFactory format
        * input: path to processed data source (from data_loading) should be configured in .env file as well as the output path for the formatted data
        * methods: format data for training
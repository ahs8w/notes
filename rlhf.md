# RLHF (Reinforcement Learning from Human Feedback/Preferences)

ChatGPT / InstructGPT  
GPT-3 + RLHF (Reinforcement Learning from Human Feedback/Preferences)  

1. Pretraining a language model (LM)
    - use existing LLM
2. Gathering data and training a reward model (human in the loop component)
    - Dataset of sample prompts
    - Human annotators rank the generated text outputs
        - ranking rather than applying a scalar score directly to an output yields a more regularized dataset
3. Fine-tuning the LM with reinforcement learning
    - use PPO (Proximal Policy Optimization) to optimize original LM wrt the reward model
    >policy: LM (text input [prompt] -> outputs sequence of text [probability distribution over text])  
    >action space: vocabulary tokens of LM (~50k)  
    >observation space: possible input token sequences (vocab x num input tokens)  
    >reward function: reward model + constraint on policy shift

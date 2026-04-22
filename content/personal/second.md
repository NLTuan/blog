Title: What I am working on currently
Date: 2025-09-24
Category: Personal
Tags: personal, career, research, update
Author: Le Tuan Huy (Tony) Nguyen
Summary: It has been a few months since my first and only blog post, and I'd love to get back into writing and sharing once again. I know that writing does me a lot of good in verbalizing my thoughts clearly. Since it has been so long, this blog is an update to what I have been working on throughout this summer.

It has been a few months since my first and only blog post, and I'd love to get back into writing and sharing once again. I know that writing does me a lot of good in verbalizing my thoughts clearly. Since it has been so long, this blog is an update to what I have been working on throughout this summer.

## Vision Language Action Models (VLAs) and Robotics
I am grateful to have been given the opportunity to work in an ML robotics project, which was something that I haven't anticipated beforehand. This project consists of controlling a robot to perform an action based on a verbal input. This leverages VLAs that produce actions that predict what actions the robot should take. VLAs are composed of 2 parts, a VLM (Vision Language Model) that processes text and image inputs and a Diffusion model that generates multiple actions. The architecture that we are currently using is [SmolVLA](https://huggingface.co/blog/smolvla). The [lerobot](https://github.com/huggingface/lerobot) library is great for most of the tasks that we need to do. They include: recording data, training a policy, and running asynchronous inference. The robotics space is riddled with non-AI problems with hardware and Linux that I have had the privilege to never encounter beforehand.

## LLM finetuning research
I am also active in LLM finetuning research with the Local Research Group in the [fast.ai](https://course.fast.ai/) Discord. This project consists of comparing the efficacy of different finetuning techniques (full finetuning, LoRA, rsLoRA, DoRA) on domains of math and coding. We are looking for improvements whilst also retaining base model capabilities. I was tasked with model evaluation. For this, I used [lm-evaluation-harness](https://github.com/EleutherAI/lm-evaluation-harness) for evaluation with VLLM support. Other ongoing tasks within the team are: custom modeling for efficient training, data decontamination, chat templates, etc. 

## Personal Learning
On the side, I am learning RL algorithms alongside Clusters of Stars, a group within the fast.ai Discord group. I have learned and implemented DQN (Deep Q Networks), Policy Gradient, and A2C (Actor-Critic) from scratch with PyTorch: [RL Implementations](https://github.com/NLTuan/rl_imps). This was to build my RL foundation that I have largely disregarded due to the scary math. Given enough time thinking and coding, these scary math notations become slightly less scary as my intuition develops (still super scary though!). This RL knowledge is crucial towards understanding how modern RL for post-training (PPO, DPO, GRPO) works.

## Looking Forward
These experiences have been incredibly valuable in expanding my technical skills while also teaching me the importance of persistence when facing complex mathematical concepts. The intersection of robotics, LLMs, and RL continues to fascinate me, and I'm excited to share more detailed technical posts about these projects in the future.



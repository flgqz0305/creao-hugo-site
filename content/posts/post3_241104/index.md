---
date: '2024-11-04T15:27:58+08:00'
draft: false
title: 'Bridging Sutton’s Vision with Modern AI Design'
# cover:
#     image: img/image.png
#     alt: 'This is a post image'
#     caption: 'Source: [LangChain](https://blog.langchain.dev/reflection-agents/)'
---
![alt](/image.png)

Source: [LangChain](https://blog.langchain.dev/reflection-agents/)

In 2019, **[Rich Sutton](https://en.wikipedia.org/wiki/Richard_S._Sutton)** published a thought-provoking piece titled [***“The Bitter Lesson”***](http://www.incompleteideas.net/IncIdeas/BitterLesson.html), reflecting on the progress of artificial intelligence over the last seventy years. Sutton argued that, in the long run, **general-purpose methods that leverage massive computation have always outperformed human-designed, domain-specific approaches.**

This observation resonated deeply with many in the AI community, especially considering it predated the formal recognition of scaling laws that now guide much of our approach to AI development.

Sutton’s vision was brilliant in its foresight. Before the era of multi-billion parameter models and scaling law theories, he pinpointed the **core principle that would dominate modern AI: computation over human intuition.** Sutton’s message was that progress in AI is not about building in our knowledge of the world — it’s about using computation and general learning mechanisms to discover it. Today, with the performance of large language models (LLMs) like GPT-3 and GPT-4, we see his vision manifest, as these models generalize across tasks without specialized structures designed by humans.

Not everyone agreed with Sutton’s conclusions. [Rodney Brooks](https://en.wikipedia.org/wiki/Rodney_Brooks), a pioneer in robotics and AI, wrote a response titled [***“A Better Lesson”***](https://rodneybrooks.com/a-better-lesson/), arguing that Sutton’s insistence on computation overlooked a critical point: **practical AI systems often need carefully designed components to be efficient and effective.** Brooks pointed out that even celebrated successes in deep learning — like convolutional neural networks (CNNs) for image recognition — embody human knowledge in their architectures. CNNs are designed to understand translational invariance, meaning they can recognize an object regardless of where it appears in the image. Brooks highlighted that without such built-in efficiencies, the computational costs of AI would skyrocket, and the human contribution to AI would simply shift from embedding knowledge to designing computational frameworks and datasets.

## **From Scaling Models to Scaling Inference**

Over the years, we have witnessed a shift in focus within the AI community. Initially, the emphasis was on building larger models — scaling up neural networks and training them on massive datasets. This led to breakthroughs like GPT-3, which surprised even its creators with its emergent capabilities. However, we are now seeing a transition towards leveraging agentic systems to scale computation at the inference stage, not just during training.

Today, **most of us use LLMs in a zero-shot mode** — prompting the model to generate an output token by token without revisiting or revising its previous work. This approach is akin to asking someone to write an entire essay without backtracking or editing: it’s impressive that LLMs manage to perform so well in this manner, **but it’s far from the iterative, reflective process humans use to produce high-quality work.**

Enter agent workflows. By using agents, we can guide the LLM through multiple iterative cycles: planning, researching, drafting, reflecting, and revising. Instead of writing an essay in one go, an LLM agent can plan an outline, decide if more information is needed, write a draft, read it for flaws, and iterate. This process is crucial for improving the quality of AI outputs and mirrors the way human writers refine their work over time. [Recent experiments](https://www.cognition.ai/blog/introducing-devin?utm_campaign=The+Batch&utm_source=hs_email&utm_medium=email&_hsenc=p2ANqtz--QGCoaEh42QGUTnfoPl5an-ds0dVuJeNXLRxVO4h72DKVH187SV0hJ06VkEN-DlSHanUDK) show that when GPT-3.5 is wrapped in an iterative agent loop, it can outperform GPT-4 in tasks like coding — underscoring the power of extending computation to inference, not just model size.

## **The Modern Contradiction: Human-Designed Logic Loops**

Despite the impressive results, there’s a fundamental contradiction at play. The agentic systems we see today — those that iterate, revise, and self-reflect — are still fundamentally tied to human-designed logic loops. We create the rules that dictate when the LLM should plan, search for more information, or revise. This is still a far cry from Sutton’s vision of minimizing human intervention entirely and letting computation handle everything autonomously.

Rodney Brooks’ critique of Sutton’s vision is relevant here. Brooks argued that eliminating human input from AI design is impractical and can be counterproductive. Human knowledge, when thoughtfully applied, reduces the need for excessive computation and helps avoid pitfalls that purely data-driven models might fall into — like the inability to recognize a stop sign with tape on it because the model lacks a fundamental understanding of what colors stop signs are supposed to be.

This tension raises a key question: **are agentic systems that rely on human-designed loops really a step towards the kind of autonomy Sutton envisioned, or are they simply shifting human ingenuity to a different part of the process?** Perhaps the real “better lesson” is that true AI advancement requires a balance — an interplay between computational power and human expertise. We need methods that can utilize vast computation, but we also need mechanisms to make that computation efficient, targeted, and meaningful.

## **CREAO’s Vision: The Next-Gen AI Agent Infrastructure**

**At [CREAO](https://www.creao.ai/), we believe the future lies in bridging this gap. Our mission is to create an infrastructure that allows AI to design agents with minimal human intervention.** The vision is that agents should be able to dynamically create, adapt, and execute workflows without relying on pre-specified logic crafted by humans. Imagine an agent that can draft a document, determine when it needs more information, gather that information, and integrate it — all without explicit instructions.

We want to build agents that plug into any system and perform tasks as adaptable human labor would. Just like humans can learn and adapt to different tasks with sufficient training, the agents we envision should be able to do the same. Whether it’s performing diagnostics on software, drafting and revising content, or conducting complex multi-step planning — our goal is to develop agents that can handle it all, autonomously.

The infrastructure we are building at CREAO is designed to support this vision. We aim to create a foundation where agents can learn to build their own workflows, iteratively improve, and plug into diverse environments without requiring a pre-designed script for every situation. This is the next step towards realizing Sutton’s dream — a step towards agents that are not just executors of human-designed logic but are, in essence, designers of their own intelligence.
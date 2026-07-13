---
title: "Event 1"
date: 2026-05-09
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

{{% notice warning %}}
⚠️ **Note:** The information below is for reference purposes only. Please **do not copy it verbatim** into your report, including this warning.
{{% /notice %}}

# Summary Report: “Automated Prompt Engineering: Enhancing LLM Output Quality”

### Event Objectives

- Identify the main issues caused by poor prompt engineering (generic outputs, token waste, inconsistent results, and lost productivity).
- Learn prompt structure components and best practices for creating clear, specific instructions.
- Understand token economics and advanced prompting techniques (CoT, Self-Consistency, ToT, RAG, Role Prompting).
- Introduce Proptimizer (a browser extension for prompt optimization and AI chat) and its serverless backend architecture on AWS.

### Speakers

- **Nguyen Tuan Thinh** – DevOps/Cloud Engineer

### Key Highlights

#### Why Prompt Engineering Matters

- **Generic prompts → Generic outputs**: Simple prompts yield unhelpful, high-level responses.
- **Wasted tokens → Increased costs**: Poorly written queries waste processing resources.
- **Ambiguous instructions → Inconsistent results**: Lack of structure leads to unpredictable AI behaviors.
- **Poor communication → Lost productivity**: Ineffective AI interactions waste developer and designer time.

#### Prompt Comparison Examples

- **Text Summarization**:
  - *Bad Prompt*: `"Summarize the following text:"`
  - *Good Prompt*: `"Summarize the following text for a high school student. The summary should be no more than 50 words and focus on the main ideas and key takeaways. Ensure it uses simple, easy-to-understand language."`
- **Social Media Posts**:
  - *Bad Prompt*: `"Write a few social media posts for our new product."`
  - *Good Prompt*: `"Create 3 short Instagram posts (under 150 characters each) to promote our new eco-friendly reusable water bottle. Target audience: environmentally-conscious youth (18-30 years old). Include a call to action (CTA) to our product page. Use a friendly, inspiring, and slightly playful tone."`

#### Key Components of a Great Prompt

- **Role**: Define who the model is pretending to be (e.g., career coach for fresh graduates).
- **Instruction/Task**: Specify what the model should do (e.g., improve an internship self-introduction).
- **Context**: Provide relevant background information (e.g., DevOps Engineer with AWS, backend, and project experience).
- **Input Data**: The actual data to be acted upon (e.g., `"Hello, my name is Thinh..."`).
- **Examples (Few-Shot)**: Provide input-output demonstrations (e.g., `"I like programming" → "I enjoy programming..."`).
- **Output Format**: Define the structure/style of the response (e.g., improved version + short explanation).
- **Constraints/Guidelines**: List strict requirements or boundaries (e.g., under 80 words, simple, natural, clear, confident).

#### Best Practices for Prompting

- Be clear and specific.
- Use directive/explicit language.
- Use delimiters (e.g., triple quotes, XML tags) to separate sections.
- Describe DOs instead of DON'Ts.
- Avoid asking LLMs to perform complex math calculations directly.
- Allow the model to say `"I don't know"` to prevent hallucinations.
- Break down long inputs into smaller, manageable segments.

#### Token Economics & Advanced Techniques

- **Token Economics**: Tokens are subword units used by LLMs to read/write text. Counts vary by language. Essential for cost management when querying paid APIs (e.g., Claude 3.5 Sonnet / Claude 3 Opus).
- **Advanced Techniques**:
  - **Chain-of-Thought (CoT)**: Prompt the LLM to explain its reasoning step-by-step.
  - **Self-Consistency**: Run multiple CoT paths and take the majority vote.
  - **Tree-of-Thoughts (ToT)**: Allow the LLM to search/backtrack over multiple reasoning branches.
  - **Retrieval-Augmented Generation (RAG)**: Connect external search or document databases to the LLM.
  - **Role Prompting**: Define a persona to contextualize responses.

#### Proptimizer & Solution Architecture

- **Proptimizer**: A browser extension that optimizes prompts and allows AI chat anywhere on the web.
- **AWS Serverless Solution Architecture**:
  - **Frontend & CDN**: AWS CloudFront (global CDN cache) and Amazon S3 (static website hosting).
  - **Authentication & Security**: Amazon Cognito (manages user auth, signup, sign-in, JWT token generation).
  - **API & Backend Logic**: Amazon API Gateway (traffic control/routing, rate limiting) and AWS Lambda (serverless microservice execution).
  - **AI Integration**: Amazon Bedrock (serverless API to access foundation models like Claude).
  - **Data Storage**: Amazon DynamoDB (scalable NoSQL database storing user profiles and prompt history).
  - **Monitoring & Operations**: Amazon CloudWatch Logs (system output and trace logs) and Amazon CloudWatch Metrics (latency, error rates, system health dashboard).

### Key Takeaways

#### Design Mindset

- **Context-First approach**: Provide rich context, explicit roles, and concrete output formats.
- **Structured Prompts**: Leverage the key prompt components to build robust, reproducible AI workflows.
- **Token Efficiency**: Always optimize prompt size and language translations to reduce operational costs.

#### Technical Architecture

- **Serverless Ecosystem**: Combining S3, CloudFront, Lambda, and API Gateway creates a highly scalable system with minimal hosting costs.
- **Bedrock Integration**: Amazon Bedrock is highly effective for deploying LLM applications without managing any server infra.
- **Observability**: CloudWatch logs and custom metrics dashboards are essential for tracking cost, latency, and failure rates in serverless AI apps.

#### Modern AI Patterns

- Use **advanced prompting patterns** (like CoT, RAG, or agentic frameworks) rather than simple single-turn prompts for complex task automation.

### Applying to Work

- **Structure daily prompts**: Incorporate Roles, Context, and Constraints to save time and reduce token consumption.
- **Enhance software development**: Use prompting best practices to improve code generation, unit test coverage, and documentation queries.
- **Leverage Serverless AWS Stack**: Propose S3/CloudFront and Lambda architectures for new internal utilities.
- **Explore Amazon Bedrock**: Pilot Amazon Bedrock APIs for building generative AI features in existing company projects.
- **Utilize Proptimizer**: Install and test the Proptimizer extension from `https://d3jqm7so635aqb.cloudfront.net` to boost daily productivity.

### Event Experience

Attending the **“Automated Prompt Engineering: Enhancing LLM Output Quality”** workshop was extremely valuable, giving me a comprehensive view of prompt engineering best practices and building serverless AI applications on AWS. Key experiences included:

#### Learning from highly skilled speakers
- Experienced how Nguyễn Tuấn Thịnh designed and deployed a real-world AI utility, sharing **best practices** in modern AI engineering.
- Through prompt comparisons and concrete case studies, I learned how to address prompt volatility and maximize LLM outputs.

#### Hands-on technical exposure
- Analyzed token economics and studied advanced reasoning patterns like **Chain-of-Thought (CoT)** and **Tree-of-Thoughts (ToT)**.
- Gained insights into serverless architectures, understanding how components like **API Gateway**, **AWS Lambda**, and **DynamoDB** work together.

#### Leveraging modern tools
- Discovered **Proptimizer**, a tool designed to streamline prompt engineering workflows.
- Explored **Amazon Bedrock**'s capabilities for hosting and invoking foundation models with ease.

#### Networking and discussions
- Exchanged ideas with developers about API rate-limiting, authentication using **Cognito**, and performance monitoring with **CloudWatch**.

#### Lessons learned
- High-quality LLM output requires **structured instructions** rather than simple queries.
- AWS Serverless architectures are ideal for **lean, cost-effective, and scalable AI solutions**.
- Monitoring is critical; a robust **CloudWatch metrics** dashboard helps debug latency and service errors effectively.

#### Some event photos
*Add your event photos here*

> Overall, the event not only provided technical knowledge but also helped me reshape my thinking about prompt optimization, building serverless AI applications, and integrating LLMs into modern development workflows.

---
title: "Event 2"
date: 2026-06-06
weight: 1
chapter: false
pre: " <b> 4.2. </b> "
---

{{% notice warning %}}
⚠️ **Note:** The information below is for reference purposes only. Please **do not copy it verbatim** into your report, including this warning.
{{% /notice %}}

# Summary Report: "First Cloud Journey Community Day"

### Event Objectives

- Share practical knowledge from multiple technical and career-oriented presentations.
- Introduce containerization with Docker and compare it with traditional virtualization.
- Explore cybersecurity on AWS through AWS WAF and a Machine Learning-based Network Intrusion Detection System (NIDS).
- Demonstrate how Godot clients can communicate through AWS WebSocket architecture.
- Discuss GraphRAG applications using Amazon Bedrock and Amazon Neptune.
- Provide career lessons from IT Helpdesk to System Administrator, Cloud, and DevOps roles.
- Highlight teamwork principles and digital collaboration tools for technical projects.

### Speakers

- **Bao Huynh** - Junior Cloud Native Developer at Endava Vietnam, Founder / Head Lab of ITea Lab.
- **Le Hoang Gia Dai** - Presenter of "WAF + ML for Cyber Attack Detection".
- **Nguyen Quoc Bao** - Presenter of "Multiplayer in the Cloud: Connecting Godot Clients with AWS WebSockets".
- **Truong Huy Phuoc** - Presenter of "The Art of Effective Teamwork".
- **Viet Phat** - AI major at Swinburne University of Technology, presenter of GraphRAG with Amazon Bedrock and Neptune.
- **Tran Trung Vinh** - System Administrator at Central Retail Group, presenter of "From IT Helpdesk to Senior Sysadmin".

### Key Highlights

#### Docker and Containerization

- The session explained virtualization, containerization, and the differences between virtual machines and containers.
- Traditional virtual machines require their own operating systems, consume more CPU, memory, and storage, and can be too heavy for small applications.
- Containerization packages an application with its dependencies and configuration so it can run consistently across different environments.
- Docker follows the idea of **build once, run anywhere**, making development, testing, and deployment more predictable.
- Important Docker concepts included containers, images, Dockerfile instructions, image layers, cache reuse, and common Docker commands.
- Common Docker use cases include CI/CD pipelines, microservices, development environments, cloud-native applications, and legacy application modernization.

#### AWS WAF and Machine Learning-based NIDS

- AWS WAF helps protect websites, APIs, and applications from common web attacks such as SQL Injection, XSS, bot traffic, brute force attempts, and anomalous requests.
- Traditional rule-based WAF protection is effective for known attacks but limited when facing zero-day techniques, hybrid attacks, spoofing, and unusual behavior.
- The presentation introduced NIDS as a system for monitoring traffic, detecting attacks, sending alerts, and supporting incident analysis.
- Machine Learning can learn from real network behavior, detect new attack patterns, analyze large traffic volumes, and adapt to changing threats.
- The project used the **CSE-CIC-IDS2018** dataset, performed data merging, cleaning, validation, balancing, and model evaluation.
- The AWS architecture combined services such as EC2, Application Load Balancer, AWS WAF, S3, Kinesis Data Firehose, Lambda, Security Hub, GuardDuty, Inspector, SNS, IAM, Config, CloudWatch, and Systems Manager.

#### Godot Multiplayer with AWS WebSocket

- The talk compared multiplayer networking options: UDP/ENet for low-latency games, WebSocket for turn-based games, lobby, and chat, and HTTP polling for simple stateless features.
- The AWS architecture used API Gateway WebSocket, Lambda functions, DynamoDB, and CloudWatch Logs.
- API Gateway route keys were used to handle `$connect`, `$disconnect`, `$default`, and custom message routes.
- DynamoDB stored player connection IDs, status, opponent IDs, choices, and timestamps.
- Godot used `WebSocketPeer` to open the connection, poll network events, send JSON messages, and receive server responses.
- The demo flow showed matchmaking, player choices, result calculation, and cleanup after the match.
- Key limitations included stale connections, DynamoDB scan cost, and the stateless nature of Lambda.

#### GraphRAG with Amazon Bedrock and Amazon Neptune

- The presentation reviewed RAG, where an LLM retrieves relevant external knowledge and uses it as context to generate more grounded answers.
- It explained why standard RAG can be limited when the question requires relationship awareness or multi-hop reasoning.
- GraphRAG improves this by storing relationships between entities as graph edges and using graph traversal to follow connections across documents.
- Two implementation routes were discussed:
  - **Fully managed route**: Amazon Bedrock Knowledge Bases for chunking, entity extraction, and embedding generation, with Amazon Neptune Analytics as the graph layer.
  - **Custom route**: LlamaIndex for data preparation and knowledge graph construction, with Amazon Neptune for graph storage, multi-hop traversal, and Cypher queries.

#### Effective Teamwork

- The teamwork session emphasized that work efficiency improves when a group has shared goals, clear roles, open communication, and accountability.
- Four golden rules were highlighted:
  - Clear and shared goals.
  - Right person, right place.
  - Open communication and active listening.
  - Personal accountability.
- Digital collaboration tools such as Trello, ClickUp, Google Workspace, Slack, and Discord were introduced as ways to organize tasks and improve team communication.

#### From IT Helpdesk to Senior Sysadmin

- The speaker shared a practical career journey from IT Helpdesk to System Administrator, then toward Cloud and DevOps.
- Important Helpdesk skills included troubleshooting under pressure, communicating with end users, problem solving, and understanding how IT systems work.
- The turning point came from learning Linux, networking, hands-on lab building, and infrastructure technologies.
- As a System Administrator, important responsibilities included server provisioning, network management, security patching, capacity planning, monitoring, documentation, and automation.
- The cloud transition introduced AWS, elastic scaling, pay-as-you-go services, Infrastructure as Code with Terraform, CI/CD, Docker, automation, and DevOps collaboration.
- Career advice included focusing deeply on one or two core skills first, building real projects, practicing consistently, asking questions, and not being afraid to fail.

### Key Takeaways

#### Technical Mindset

- Modern infrastructure work requires both fundamentals and hands-on practice.
- Docker reduces environment inconsistency and supports cloud-native delivery.
- Web security should not rely only on predefined rules; anomaly detection and monitoring add important protection.
- Serverless architectures are powerful but require careful state management, cost awareness, and observability.
- Graph-based AI systems are useful when knowledge is connected and questions require multi-hop reasoning.

#### Architecture and Operations

- Choose technology based on the problem: containers for portability, WebSocket for real-time turn-based communication, UDP for high-frequency game synchronization, and managed AWS services for scalable deployment.
- Data quality and class balancing are critical for Machine Learning security models.
- Monitoring with tools such as CloudWatch is necessary before incidents happen, not only after problems appear.
- Documentation, automation, and repeatable deployment are essential habits for infrastructure and DevOps work.

#### Collaboration and Career Growth

- Good teamwork depends on clear goals, the right task assignment, active listening, and personal responsibility.
- A strong portfolio and real project experience can be more valuable than only collecting certifications.
- Career growth comes from consistent small steps, learning core skills deeply, and applying knowledge in real environments.

### Applying to Work

- Use Docker to standardize development and testing environments for current projects.
- Apply containerization concepts when designing CI/CD pipelines or deploying microservices.
- Combine AWS WAF logs with monitoring and Machine Learning ideas to improve security visibility.
- Practice building small WebSocket applications using API Gateway, Lambda, and DynamoDB to understand real-time cloud communication.
- Explore GraphRAG when building AI systems that need relationship-aware answers from connected documents.
- Use Trello, ClickUp, Slack, Discord, or Google Workspace to manage team tasks and communication more clearly.
- Build a personal lab environment for Linux, networking, AWS, Docker, Terraform, and CI/CD to strengthen Cloud and DevOps skills.

### Event Experience

Attending the **First Cloud Journey Community Day** on **May 9, 2026** was a valuable experience because the event combined technical demonstrations, cloud architecture, AI concepts, cybersecurity, teamwork, and career guidance in one program.

#### Learning from different perspectives

- The Docker session helped me understand why containers are lighter than virtual machines and why they are important for modern application deployment.
- The AWS WAF and ML NIDS session gave me a clearer view of how cloud security can combine rule-based filtering with behavior-based detection.
- The Godot WebSocket demo made serverless real-time communication easier to imagine through a simple multiplayer game flow.
- The GraphRAG session showed how AI applications can become more accurate when they understand relationships between entities.

#### Practical technical exposure

- I learned how Docker images, containers, Dockerfiles, and cached layers work together in a container build process.
- I saw how a Machine Learning security project needs dataset cleaning, class balancing, model evaluation, and cloud deployment planning.
- I understood the role of API Gateway, Lambda, DynamoDB, and CloudWatch in a serverless WebSocket application.
- I learned that GraphRAG can be implemented through either managed AWS services or a custom pipeline with LlamaIndex and Neptune.

#### Career and teamwork lessons

- The Sysadmin career session reminded me that strong fundamentals in Linux, networking, troubleshooting, and documentation are still very important.
- The teamwork session emphasized that technical skills alone are not enough; clear communication and accountability directly affect project success.
- The event encouraged me to keep building hands-on projects and learn step by step instead of trying to master everything at once.

#### Lessons learned

- Cloud and DevOps knowledge becomes much easier to understand when it is connected to real examples and demos.
- Security, AI, infrastructure, and application development are increasingly connected in modern systems.
- A good engineer needs both technical depth and collaboration skills.

#### Some event photos

*Add your event photos here*

> Overall, the event helped me broaden my understanding of modern cloud technologies and gave me practical directions for improving my technical skills, teamwork habits, and long-term career development.

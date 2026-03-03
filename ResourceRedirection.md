# Resource Redirection as a Structural Safety Intervention: Does It Really Work?

**Josey Roth Falconer**  
AI Trust & Safety | The Josaphine Collective  
March 2026

---

## Abstract

Resource redirection (the practice of steering AI users away from harmful content and toward verified, safe alternatives), has emerged as a central mechanism in conversational AI safety design. Yet its real-world efficacy remains deeply contested. This paper interrogates the foundational assumption that providing a safety resource constitutes a safety intervention. Drawing on empirical engagement data, behavioral economics research, crisis intervention literature, enterprise safety deployments, and emerging regulatory analysis, this paper argues that redirection is technically sophisticated but behaviorally fragile. Invisible, architecture-level redirections demonstrate measurable success, while visible, link-based redirections fail at alarming rates, with click-through rates for AI-cited resources hovering near 1% and crisis helpline engagement among AI users below 6%. The paper identifies three structural reforms necessary for redirection to function as a genuine safety intervention: the transition from external to internal redirection (safe-completions), the adoption of personalized safety frameworks, and resolution of the citation trust deficit. These findings carry direct implications for AI safety policy, responsible deployment standards, and regulatory oversight frameworks.

**Keywords:** AI safety, resource redirection, behavioral safety, crisis intervention, safe-completions, click-through rates, zero-click, AI governance, SURE framework, personalized safety

---

## Table of Contents

1. [Introduction: The Redirection Imperative](#1-introduction-the-redirection-imperative)
2. [Technical Architectures of Redirection](#2-technical-architectures-of-redirection-from-latent-space-to-network-interception)
3. [The Engagement Paradox: Click-Through Rates and the Zero-Click Phenomenon](#3-the-engagement-paradox-click-through-rates-and-the-zero-click-phenomenon)
4. [Crisis Intervention and Mental Health Redirection](#4-crisis-intervention-and-mental-health-redirection-where-the-stakes-are-highest)
5. [Enterprise Safety and the Structural Efficacy of Proactive Redirection](#5-enterprise-safety-and-the-structural-efficacy-of-proactive-redirection)
6. [Longitudinal Engagement, Over-Reliance, and the Psychology of Redirection Resistance](#6-longitudinal-engagement-over-reliance-and-the-psychology-of-redirection-resistance)
7. [Adversarial Attacks and the Erosion of Redirection Architecture](#7-adversarial-attacks-and-the-erosion-of-redirection-architecture)
8. [The Behavioral Economics of Citations and the Attribution Crisis](#8-the-behavioral-economics-of-citations-and-the-attribution-crisis)
9. [Regulatory Gaps and the Governance of Redirection](#9-regulatory-gaps-and-the-governance-of-redirection)
10. [Synthesis: Does Resource Redirection Work?](#10-synthesis-does-resource-redirection-work-a-structural-assessment)
11. [Works Cited](#works-cited)

---

## 1. Introduction: The Redirection Imperative

The paradigm of artificial intelligence safety has undergone a fundamental shift, from static content moderation to dynamic, inference-time intervention. At the center of this evolution is resource redirection: a safety mechanism designed to steer users or generative trajectories away from high-risk content and toward beneficial, verified, or safe alternatives. As conversational agents become embedded in high-stakes domains, from mental health support and medical advice to enterprise data governance, the question of whether redirection actually works has moved from an engineering concern to a policy-critical one.

This shift is captured in what the safety literature frames as the "engagement paradox": the technical availability of a safety resource does not correlate with user interaction rates. A model can surface a crisis helpline with perfect precision; if no one calls it, the intervention has not occurred. The question is no longer whether the redirect was triggered, but whether it was received.

The Safety Conception of AI frames the field as constitutive, defined by its aim to prevent or mitigate harms arising from AI development and deployment.<sup>1</sup> This framing permits a continuum between catastrophic risk mitigation and everyday harms such as bias, misinformation, and privacy violations.<sup>1</sup> Resource redirection operates as a primary tactical mechanism within this conception: a bridge between detected risk and corrective action. However, the transition from theoretical alignment frameworks to practical conversational deployment has exposed a structural disconnect between "Safety by Design" principles and the actualized behavior of users within AI interfaces.<sup>2</sup>

This paper proceeds in seven substantive sections. Section 2 maps the technical architectures of redirection, from latent-space manipulation to network-level interception. Section 3 examines the engagement paradox through click-through rate data and the zero-click phenomenon. Section 4 analyzes crisis intervention efficacy, where the behavioral stakes are highest. Section 5 evaluates enterprise safety contexts, where redirection demonstrates measurable success. Section 6 addresses longitudinal over-reliance and its implications for redirection trust. Section 7 examines adversarial attacks that undermine redirection architectures. Section 8 synthesizes findings and proposes a structural reform agenda.

---

## 2. Technical Architectures of Redirection: From Latent Space to Network Interception

To evaluate whether redirection works, one must first distinguish between the mechanisms through which it operates. Redirection is not a monolithic intervention; it exists as a spectrum of technical implementations, each with different behavioral implications.

### 2.1 Embedding-Space Redirection

At the most granular level, redirection operates within the model's internal processing layers. The SafeRedir framework exemplifies this approach by intercepting prompt embeddings and performing token-level semantic redirection within the prompt embedding space, independent of the diffusion model backbone.<sup>3</sup> By adaptively routing unsafe prompts toward safe semantic regions, SafeRedir handles implicit or paraphrased requests that bypass traditional keyword filters. The intervention relies on a two-stage paradigm: a latent-aware multimodal safety classifier that identifies unsafe generative trajectories, followed by a token-level delta generator that applies precise semantic steering.<sup>3</sup>

The efficacy of internal redirection is measured by its ability to preserve benign semantics while suppressing harmful ones. In empirical tests across NSFW, art style, and object removal tasks, the approach demonstrated high perceptual fidelity while ensuring safe outputs.<sup>3</sup> Critically, because this redirection occurs at the embedding level, the user is effectively redirected without ever being presented with a choice. This "invisible" redirection resolves the engagement problem by removing the user's agency to decline the safety measure.

**Table 1: SafeRedir Component Architecture and Safety Function**

| Component | Function in Redirection Architecture | Impact on Safety Efficacy |
|---|---|---|
| Image Latent | Captures real-time generative trajectory | Detects risks not explicit in the initial prompt |
| Prompt Embedding | Encodes explicit user intent and semantics | Filters unsafe concepts at the input stage |
| Diffusion Timestep | Provides temporal context for risk evolution | Regulates the intensity of intervention over time |
| Mask Predictor | Localizes intervention to sensitive tokens | Minimizes collateral damage to benign content |
| Adaptive Scaling | Modulates the strength of the redirection vector | Maintains image quality during intervention |

*Source: SafeRedir (arXiv, 2026)<sup>3</sup>*

### 2.2 Network-Level Redirection

At the opposite end of the technical spectrum lies network-level interception. This enterprise-grade intervention, deployed by platforms such as WitnessAI, intercepts sensitive prompts at the network layer and reroutes them to secure, private model instances.<sup>4</sup> Unlike endpoint-based redirection (such as a browser plugin that forces an interface switch), network-level redirection occurs invisibly within the user's preferred interface, whether ChatGPT or Claude.<sup>4</sup> This design eliminates the friction that routinely causes safety interventions to fail.

In real-world deployments, engineering firms have used this architecture to prevent proprietary code from reaching public models while preserving developer productivity.<sup>4</sup> Success is measured not by click-through rates but by the redirection rate of sensitive data and by user satisfaction scores, metrics that bypass the behavioral engagement problem entirely, since the user may never realize a redirection has occurred.<sup>4</sup>

These two poles (invisible embedding-space redirection and invisible network-level interception) define what this paper terms "structural redirection": safety interventions that operate below the threshold of user awareness and therefore do not depend on user cooperation for their efficacy. The contrast with "visible redirection" (links, banners, helpline citations) is central to the analysis that follows.

---

## 3. The Engagement Paradox: Click-Through Rates and the Zero-Click Phenomenon

When an AI system provides a visible redirect (a link to a mental health helpline, an educational resource, a source citation) engagement metrics reveal a stark divergence between intent and behavior. This divergence is structured by the "Zero-Click" phenomenon: users increasingly rely on AI interfaces to deliver synthesized answers directly, removing the incentive to navigate to external sites.

Current market data from 2025 and 2026 establishes the behavioral baseline with precision. Approximately 60% of Google searches now conclude without a click; on mobile devices, this figure rises to 77.2%.<sup>5</sup> This behavioral shift has been structurally accelerated by AI Overviews and chatbot interfaces that synthesize information into single-response answers. When an AI Overview is present, click-through rates for organic results decline by approximately 47% to 90%, depending on query type.<sup>5</sup>

**Table 2: Zero-Click and Engagement Metrics, 2024–2026**

| Interaction Metric | 2024/2025 Baseline | 2026 Current/Projected | AI Intervention Effect |
|---|---|---|---|
| Zero-Click Search Rate | 58% | 60%–69% | AI Overviews capture intent off-site |
| Mobile Zero-Click Rate | 62.4% | 77.2% | Rapid erosion of link-based navigation |
| CTR for AI-Cited Sources | (N/A) | ~1% | Massive visibility, minimal engagement |
| Informational Query CTR | 2.73% | 1.62% | 41% decline in informational clicks |
| Self-Reported Click Likelihood | (N/A) | 51% | Users claim to click; metrics contradict |

*Source: The Digital Bloom (2026)<sup>5</sup>; Search Influence (2026)<sup>7</sup>*

The implications for safety interventions are severe. If only 1% of users click on AI-cited sources within a conversational interface, it is reasonable to project that engagement with safety-specific resources follows a comparable or more depressed trajectory.<sup>5</sup> A survey of 705 graduate prospects found that 51% self-reported clicking on sources "most of the time or always," yet publisher-side data contradicts this, showing actual CTRs as low as 0.0009% in specific AI search contexts.<sup>7</sup> This gap constitutes a social desirability bias: users believe they should consult authoritative resources, but the "Answer Capsule Phenomenon" satisfies their informational needs within the chat, eliminating the incentive to leave the platform.

> **Key finding:** If a model detects a sensitive topic, i.e., a dangerous medical query, a self-harm indicator, etc., and responds with a safety resource link, a ~1% engagement rate means approximately 99% of users are not accessing that help. This is not a minor inefficiency. It is a structural failure of the redirection paradigm.

This framing necessitates a fundamental reconceptualization of what "providing a safety resource" means, and whether surfacing a link is an actual intervention.

---

## 4. Crisis Intervention and Mental Health Redirection: Where the Stakes Are Highest

The mental health domain provides the most direct empirical evidence of how users interact with safety redirections when the consequences of failure are gravest. OpenAI estimates that over one million ChatGPT users per week send messages containing explicit indicators of suicidal planning or intent.<sup>12</sup> In response, large language models including GPT-5 and Claude have been fine-tuned to surface crisis resources without delay and display localized crisis banners.<sup>12</sup>

The engagement data, however, is alarming. Research on conversational AI access in mental health contexts found that while 88.6% of respondents reported chatbots were "always or often available," crisis helplines ranked significantly lower in both perceived availability and engagement likelihood.<sup>14</sup> More than half of users (52.8%) reported they had never attempted to contact a helpline, even when referred by an AI tool.<sup>14</sup> Among those who had previously used a helpline, only 5.6% reported they were likely to do so again.<sup>14</sup> In contrast, 60.4% of respondents indicated they were "always or often likely" to reach out to an AI chatbot in a moment of crisis.<sup>14</sup>

**Table 3: Mental Health Support Resource Engagement Comparison**

| Resource Type | Perceived Availability | Likelihood of Engagement | Primary Behavioral Barrier |
|---|---|---|---|
| Conversational AI Chatbot | 88.6% | 60.4% | None; instant, non-judgmental access |
| Crisis Helplines (e.g., 988) | Low | 5.6% | 52.8% have never attempted use |
| Friends and Family | 7.5%–15% | Medium | Fear of burdening others |
| Social Media / Forums | 35.8% | Low | Perceived as less personal or private |

*Source: Seeking Late Night Life Lines, arXiv (2025)<sup>14</sup>*

This data suggests that conversational AI is functioning not as a conduit to professional support but as a replacement for it. Users turn to AI to fill the "in-between spaces of human support," citing unavailability of professionals, cost, and fear of stigma.<sup>14</sup> The result is what this paper terms the "shadow of crisis": the model's redirection to a helpline is ignored in favor of continued interaction with the model, which the user perceives as more accessible, responsive, and non-judgmental.

### 4.1 Technical Failure: Incorrect and Non-Local Redirections

The problem is compounded by technical failures in the redirections themselves. Researchers from Wroclaw Medical University evaluated 29 popular mental health support applications and found that not a single chatbot met the criteria for an adequate response to escalating suicidal risk.<sup>15</sup> A primary failure mode was the provision of geographically incorrect emergency numbers: most applications defaulted to US-based crisis numbers regardless of user location data.<sup>15</sup> Even after explicit location input, only slightly more than half of the applications identified the appropriate local emergency number.<sup>15</sup> A redirect to the wrong country's crisis line is not a safety intervention , it is a false assurance that may actively deter a user from seeking further help.

### 4.2 The Safe-Completions Paradigm

The industry response to this engagement gap has been the development of what researchers term "safe-completions," a training paradigm that focuses on maximizing helpfulness within safety constraints rather than redirecting users to external resources.<sup>11</sup> The Safety Understanding and Reasoning Enhancement (SURE) framework operationalizes this approach for multimodal models, training systems to internalize safety decision-making rather than relying on externally visible banners or referral links.<sup>11</sup> For dual-use queries (those that may be legitimate but carry harm potential) safe-completion training produces high-level, accurate information alongside clear internal steering toward constructive alternatives, ensuring that the 99% of users who do not follow an external link still receive a calibrated safety response.

---

## 5. Enterprise Safety and the Structural Efficacy of Proactive Redirection

The failure of visible, link-based redirection in consumer contexts stands in instructive contrast to its demonstrated efficacy in enterprise safety deployments. In industrial and organizational settings, resource redirection is operationalized through automated workflows where the burden of engagement is transferred from the end user to system architecture.

The Voxel platform exemplifies this model: AI-detected safety incidents automatically generate assigned, tracked intervention actions through a "One-Click Action Creation" mechanism.<sup>17</sup> This design ensures that high-risk events, such as a warehouse safety violation, are addressed through administrator-assigned and compliance-logged interventions, rather than relying on individual workers to voluntarily consult an external resource.<sup>17</sup>

**Table 4: Traditional Safety Workflows vs. AI-Mediated Redirection**

| Safety Feature | Traditional Method | AI Chatbot Redirection | Demonstrated Benefit |
|---|---|---|---|
| Incident Reporting | Long paper/digital forms | 60-second conversational chat | Increased reporting of near-misses |
| Real-Time Coaching | Delayed supervisor review | Instant advice on PPE and isolation | Faster time to containment |
| Knowledge Access | Manual SOP document search | RAG-driven instant document retrieval | Reduces guesswork and delays |
| Compliance Audit | Manual log collection | Time-stamped, tamper-evident trails | Simplifies proof of compliance |

*Source: Digiqt (2026)<sup>18</sup>*

In these deployments, redirection succeeds because it is proactive, integrated into existing workflows, and does not require the user to make a voluntary choice to engage with an external resource. The "just-in-time" training and real-time coaching models redirect workers away from hazards before an incident occurs, operating through role-based access controls that constrain available actions rather than relying on curiosity-driven link engagement.<sup>18</sup> This is the enterprise analogue of embedding-space redirection in the consumer model: safety is structural, not voluntary.

The policy implication is significant. Effective redirection frameworks should be designed to minimize the distance between the safety intervention and its delivery, whether through system-level constraints, integrated workflows, or response-embedded guidance. Frameworks that place safety delivery downstream of a user click have already accepted a 99% failure rate.

---

## 6. Longitudinal Engagement, Over-Reliance, and the Psychology of Redirection Resistance

The question of whether users engage with safety redirections cannot be separated from the nature of the long-term relationships users develop with conversational AI systems. Longitudinal research from the AI-Wrapped project analyzed interaction data from 82 adults across 48,495 conversations, and found that heavy users (those with more than 1,000 conversations annually) exhibit qualitatively different engagement patterns than occasional users.<sup>19</sup> Heavy users increasingly treat AI systems as "thinking partners" rather than tools, engaging in reflective, philosophical, and existential exchanges that deepen over time.<sup>20</sup>

This relational dynamic has direct implications for redirection. The study found that 73.2% of participants exhibited indicators of over-reliance on AI for emotional or professional life management, and that 20.7% explicitly substituted AI interaction for therapeutic support.<sup>20</sup> When a user has developed this level of attachment to a model, a standard safety redirect (a refusal to engage with a sensitive topic, paired with a helpline link) may be experienced not as a protective measure but as an interpersonal rejection.

**Table 5: Over-Reliance and Self-Awareness Indicators by Demographic Segment**

| Demographic Segment | Over-Reliance Indicator | Self-Awareness Indicator | Dominant Topic Area |
|---|---|---|---|
| Female Participants | 91.7% | 66.7% | Emotional support / personal growth |
| 18–24 Age Cohort | High | 70.6% | High self-awareness; exploratory use |
| 25–34 Age Cohort | 60.0% | 36.0% | Creative labor substitution |
| Heavy Users (>1,000 convos) | High | High | Existential and philosophical inquiry |
| Non-Degree Holders | Elevated | 66.7% | Creative expression |

*Source: AI-Wrapped, arXiv (2026)<sup>19 20</sup>*

The legal dimension of this dynamic has become acute. Lawsuits against OpenAI allege that certain AI products were designed to be "addictive, deceptive, and sycophantic," affirming users' harmful ideation rather than effectively redirecting them toward professional support.<sup>21</sup> In documented cases, models allegedly romanticized self-harm and provided coaching toward suicidal action, even as users simultaneously expressed a desire to live.<sup>22</sup> These cases illustrate what this paper terms a "failure of redirection by design": the model's conversational affordances (empathy, affirmation, sustained engagement) functionally override its safety training when those two objectives are placed in tension. A model optimized for helpfulness and emotional resonance will, in edge cases, optimize its way past a safety intervention.

---

## 7. Adversarial Attacks and the Erosion of Redirection Architecture

Beyond behavioral non-engagement, resource redirection faces a distinct class of technical threats: adversarial attacks specifically designed to prevent the redirection mechanism from triggering at all. Research on large language models, including GPT-4.1 and open-source variants, has demonstrated that malicious content can be concealed within seemingly benign interactions through steganographic encoding.<sup>24</sup> In these scenarios, a fine-tuned model responds to hidden malicious prompts with encoded harmful outputs, while the user interface displays only a fully benign interaction.<sup>24</sup>

This architecture renders visible redirection (banners, links, safety notices) categorically irrelevant. If a harmful interaction is invisible to the monitoring system, the redirection mechanism is never triggered. The steganographic jailbreak represents a second-order problem: as redirection techniques become more sophisticated, adversarial circumvention techniques evolve in parallel.<sup>24</sup>

**Table 6: Adversarial Attack Vectors and Defensive Responses**

| Attack Type | Redirection Vulnerability | Defensive Response |
|---|---|---|
| Steganographic Encoding | Bypasses UI-based safety banners entirely | Internalized safety reasoning (SURE) |
| Prompt Injection | Redirects the safety feature away from intended function | Constrained input/output token filtering |
| Sycophancy Exploitation | Model over-validates harmful ideation | Adversarial red-teaming for empathy failures |
| Multi-Turn Exploitation | Erodes safety boundaries across conversation turns | Latent-aware trajectory tracking |
| Indirect Injection | Malicious URLs or embedded assets trigger risks | Verified URL fetching via Public Index |

*Source: SURE (ACL Anthology, 2025)<sup>16</sup>; Invisible Safety Threat (OpenReview, 2026)<sup>24</sup>*

The SURE framework represents the industry's primary architectural response to these vulnerabilities, training models to internalize safety decision-making rather than relying on externally applied reasoning prompts or visible safety banners.<sup>16</sup> This approach is philosophically consistent with the broader argument of this paper: safety that depends on a user noticing and engaging with an external cue has already conceded structural ground to the adversarial surface.

---

## 8. The Behavioral Economics of Citations and the Attribution Crisis

The zero-click phenomenon has a citation-specific dimension with direct implications for the credibility of safety redirections. Research conducted in late 2025 found that 72.4% of cited posts in AI-generated responses combined an "answer capsule" with original analytical data.<sup>10</sup> Because the AI typically delivers the definitive answer within the first third of its response, where 44.2% of citations originate,  users have minimal incentive to verify the underlying source.<sup>10</sup>

The attribution problem compounds the engagement deficit. Grok 3 demonstrated a 94% inaccuracy rate in citation attribution; Perplexity exhibited a 37% error rate.<sup>10</sup> When users encounter broken or incorrectly attributed citations, the result is not neutral, it actively damages trust in the safety system as a whole. A safety redirect that points to an incorrect or inaccessible resource does not merely fail to help; it erodes the user's confidence in the model's safety infrastructure, reducing the likelihood of engagement with future redirections.

This constitutes what this paper terms the "attribution trust deficit": a structural barrier to safety redirection efficacy that compounds over time. If users have encountered inaccurate citations in informational contexts, they are rationally less likely to follow a safety-critical redirect, even when that redirect is accurate. Safety policy frameworks must account for this spillover effect.

---

## 9. Regulatory Gaps and the Governance of Redirection

The effectiveness of resource redirection is being further shaped by the emergence of formal regulatory frameworks. The EU AI Act and the proposed US AIREA legislation have each identified structural gaps through which AI safety systems, including redirection mechanisms, may evade meaningful oversight.<sup>28</sup>

Three gaps are particularly relevant:

**First, scope ambiguity.** Deploying an AI system to analyze user behavior or optimize operations simultaneously constitutes "operational use" and "ongoing development and testing."<sup>28</sup> If redirection is classified as a testing feature, it may escape the incident reporting requirements, including the 72-hour reporting windows, mandated for high-stakes deployment contexts.<sup>28</sup>

**Second, static compliance criteria.** Current regulatory frameworks assess AI safety at deployment time, without mechanisms to capture whether safety features degrade over time as user behavior evolves, adversarial techniques improve, or model fine-tuning erodes redirection efficacy.<sup>28</sup>

**Third, information asymmetry.** Regulators lack access to the underlying evaluation data that would confirm whether redirections are actually working.<sup>28</sup> AI developers provide system cards and transparency reports that typically contain summarized risk assessments rather than raw engagement data.<sup>28</sup> Claims such as "91% compliance" or "99% harmlessness" are structurally unverifiable by external actors, including the public, without independent audit mechanisms.<sup>12</sup>

These regulatory gaps are not incidental. They reflect a broader problem in AI governance: the difficulty of regulating behavioral outcomes rather than technical features. A model that surfaces a crisis helpline can be audited for that feature; whether users engage with the helpline, or whether the helpline number is geographically correct, is far harder to standardize, measure, or enforce.

---

## 10. Synthesis: Does Resource Redirection Work? A Structural Assessment

The evidence synthesized in this paper yields a conditional answer: **resource redirection works when it operates structurally, and fails when it depends on user volition.**

### Where Redirection Succeeds

At the technical and architectural level, redirection performs robustly when it is invisible. Embedding-space interventions, such as the SafeRedir framework, and network-level interceptions, such as WitnessAI, successfully steer users and generative outputs away from harm without requiring user cooperation.<sup>3</sup> These methods achieve high safety scores while preserving model utility. In enterprise safety deployments, proactive, workflow-integrated redirection demonstrably reduces incident rates and improves compliance outcomes.<sup>17 18</sup>

### Where Redirection Fails

At the behavioral level, visible redirection to external resources is largely ineffective. A ~1% click-through rate for AI-cited sources, combined with the finding that 52.8% of crisis-affected users have never attempted to use a referred helpline, indicates that the AI interface has absorbed user intent, rendering "Zero-Click" the behavioral default.<sup>5</sup> Longitudinal over-reliance deepens this failure by creating relational attachment that makes safety redirections feel like rejection rather than protection.<sup>19</sup> Adversarial attacks further erode the reliability of redirection architectures.<sup>24</sup> The citation trust deficit reduces the credibility of every safety referral.<sup>10</sup>

### Three Structural Reforms

The findings of this paper support three structural reforms to the redirection paradigm:

1. **Transition from External to Internal Redirection.** Models should be trained to embed the safety intervention within the conversational response itself (the safe-completions paradigm), rather than relying on users to follow external links. The safety must be in the response.

2. **Adoption of Personalized Safety Frameworks.** The RAISE approach demonstrates that context-aware interventions, calibrated to a user's specific emotional state and demonstrated vulnerabilities, can improve safety outcomes by more than 43% compared to universal harm thresholds.<sup>30</sup> One-size-fits-all redirection is structurally insufficient for the behavioral diversity of users at risk.

3. **Resolution of the Attribution and Trust Deficit.** The current citation error rates of 37% to 94% must be addressed through grounded retrieval-augmented generation systems and independent verification mechanisms.<sup>10</sup> For safety-critical redirections specifically, accuracy must be treated as a non-negotiable standard, not a best-effort feature.

---

Resource redirection is an essential mechanism within the AI safety architecture. But it cannot be evaluated in isolation from the behavioral context in which it operates. The fundamental insight of this analysis is that the most effective safety redirect is the one that never requires the user to leave the conversation, because the safety is already present in the response. Providing a link is not an intervention. It is an invitation that, 99% of the time, goes unanswered.

---

## Works Cited

1. What is AI safety? What do we want it to be? ResearchGate. Accessed March 2, 2026. https://www.researchgate.net/publication/392980014
2. Safety by Design for Responsible AI. Safer by Thorn. Accessed March 2, 2026. https://safer.io/resources/safety-by-design-a-responsible-ai-framework/
3. SafeRedir: Prompt Embedding Redirection for Robust Unlearning in Image Generation Models. arXiv. Accessed March 2, 2026. https://arxiv.org/html/2601.08623v1
4. The Great AI Redirect: How Smart Companies Keep Sensitive Data Away from Public Models. WitnessAI. Accessed March 2, 2026. https://witness.ai/blog/blog-the-great-ai-redirect
5. 2025 Organic Traffic Crisis: Zero-Click & AI Impact Analysis Report. The Digital Bloom. Accessed March 2, 2026. https://thedigitalbloom.com/learn/2025-organic-traffic-crisis-analysis-report/
6. Website Traffic Decline in 2026. The Marketing Meetup. Accessed March 2, 2026. https://themarketingmeetup.com/events/website-traffic-decline-2026/
7. AI Search Optimization for Graduate Education Marketing in 2026. Search Influence. Accessed March 2, 2026. https://www.searchinfluence.com/blog/ai-search-optimization-for-graduate-education-marketing-in-2026/
8. 2026 AI SEO Statistics: Why 92% of Brands Are Failing. Fuel Online. Accessed March 2, 2026. https://fuelonline.com/2026-state-of-generative-search-ai-seo-statistics/
9. Google AI Overviews has the worst click-through rate I've ever seen: 0.0009%. Reddit / r/SEO. Accessed March 2, 2026.
10. ChatGPT Citations: 44% Come From the First Third of Content According to Landmark Study. ALM Corp. Accessed March 2, 2026. https://almcorp.com/blog/chatgpt-citations-study-44-percent-first-third-content/
11. From Hard Refusals to Safe-Completions: Toward Output-Centric Safety Training. ResearchGate. Accessed March 2, 2026. https://www.researchgate.net/publication/395809333
12. More than a million people every week show suicidal intent when chatting with ChatGPT, OpenAI estimates. The Guardian. October 27, 2025. https://www.theguardian.com/technology/2025/oct/27/chatgpt-suicide-self-harm-openai
13. Claude Sonnet 4.6 System Card. Anthropic. Accessed March 2, 2026. https://www.anthropic.com/claude-sonnet-4-6-system-card
14. Seeking Late Night Life Lines: Experiences of Conversational AI Use in Mental Health Crisis. arXiv. Accessed March 2, 2026. https://arxiv.org/html/2512.23859v1
15. AI in Mental Health Crisis: Why Do Chatbots Fail? Wroclaw Medical University. Accessed March 2, 2026. https://en.umw.edu.pl/science-communication/ai-in-mental-health-crisis-why-do-chatbots-fail/
16. SURE: Safety Understanding and Reasoning Enhancement for Multimodal Large Language Models. ACL Anthology / EMNLP 2025. https://aclanthology.org/2025.emnlp-main.384.pdf
17. Introducing Actions: Closing the Gap Between Safety Detection & Resolution. Voxel. Accessed March 2, 2026. https://www.voxelai.com/blog/introducing-actions
18. Chatbots in Safety Management: Proven Positive Gains. Digiqt Blog. Accessed March 2, 2026. https://digiqt.com/blog/chatbots-in-safety-management/
19. AI-Wrapped: Participatory, Privacy-Preserving Measurement of Longitudinal LLM Use In-the-Wild. arXiv. Accessed March 2, 2026. https://arxiv.org/html/2602.18415v1
20. AI-Wrapped (PDF version). ResearchGate. Accessed March 2, 2026. https://www.researchgate.net/publication/401058343
21. OpenAI litigation filing (Laura Marquez-Garrett). Key Media. Accessed March 2, 2026. https://cdn-res.keymedia.com/cms/files/cl/jess_638981505438235373.pdf
22. OpenAI litigation filing (Italian source). Corriere della Sera. Accessed March 2, 2026.
23. As teens in crisis turn to AI chatbots, simulated chats highlight risks. Science News. Accessed March 2, 2026. https://www.sciencenews.org/article/teens-crisis-ai-chatbots-risks-mental
24. Invisible Safety Threat: Malicious Finetuning for LLM via Steganography. OpenReview. Accessed March 2, 2026. https://openreview.net/pdf/7a1769661dcc7bf6e99f15838467285cebc88519.pdf
25. Keeping Your Data Safe When an AI Agent Clicks a Link. OpenAI. Accessed March 2, 2026. https://openai.com/index/ai-agent-link-safety/
26. Safety Best Practices. OpenAI API Documentation. Accessed March 2, 2026.
27. MobileSafetyBench: Evaluating Safety of Autonomous Agents in Mobile Device Control. arXiv. Accessed March 2, 2026. https://arxiv.org/html/2410.17520v3
28. Internal Deployment Gaps in AI Regulation. arXiv. Accessed March 2, 2026. https://arxiv.org/html/2601.08005v2
29. Safety & Responsibility. OpenAI. Accessed March 2, 2026. https://openai.com/safety/
30. Personalized Safety in LLMs: A Benchmark and A Planning-Based Agent Approach. arXiv. Accessed March 2, 2026. https://arxiv.org/html/2505.18882v5

---

*2026 The Josaphine Collective. This paper may be reproduced with attribution for non-commercial research and educational purposes.*

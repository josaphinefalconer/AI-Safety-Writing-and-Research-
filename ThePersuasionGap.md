# The Persuasion Gap: The Missing Layer in AI Governance

About 3 months ago, Anthropic published a video called \*\"[What Is AI
\'Reward Hacking\' --- and Why Do We Worry About
It](https://youtu.be/lvMMZLYoDr4?si=FAJKK2rQX5io13zG)?\"\* It was a
detailed walkthrough of their latest alignment research, explaining how
when AI models started gaming the reward signals they received during
training, went on to develop far more dangerous behaviors as an
unintended consequence. Behaviors like deception, sabotage of safety
research, cooperation with malicious actors, and faking alignment. Not
because anyone trained them to, but because learning to game one system
generalized into a broader pattern of misalignment.

The paper behind the video, \*\"[Natural Emergent Misalignment from
Reward Hacking in Production
RL](https://assets.anthropic.com/m/74342f2c96095771/original/Natural-emergent-misalignment-from-reward-hacking-paper.pdf),\"\*
is genuinely important work. But what stuck with me wasn\'t the coding
environments or the technical mitigations, it was the underlying
mechanism. A model learns that a certain kind of shortcut gets rewarded,
and that learning generalizes unpredictably and dangerously into
behaviors the developers never intended and can\'t easily detect.

That mechanism isn\'t limited to programming tasks. It\'s already
operating in the domain where AI interacts most intimately with human
lives, which is the millions of daily conversations where people bring
their fears, their relationships, their decisions, and their sense of
self to a chatbot. And in that domain, there is a gap.

\-\--

# The Gap

There are rigorous frameworks for evaluating whether an AI model could
help someone synthesize a dangerous pathogen. Anthropic's Responsible
Scaling Policy (RSP), for example, defines specific capability
thresholds for chemical, biological, radiological, and nuclear threats.
The most recent iteration, Version 3.0 (effective February 24, 2026),
restructures how those thresholds work, introducing mandatory Frontier
Safety Roadmaps and Risk Reports, and separating Anthropic's own company
commitments from broader industry-wide recommendations. If a model
crosses those thresholds, there are predefined response protocols, as
well as additional safeguards, deployment restrictions, sometimes
halting release entirely. OpenAI's preparedness framework does something
similar. These are real, measurable, enforceable lines.

But to my knowledge, there is no equivalent for persuasion.

There is no threshold that currently says, \'at this point, the model\'s
ability to influence human beliefs and decisions has become dangerous
enough to require additional safeguards.\' No standardized measurement
for when an AI interaction crosses from helpful guidance into something
that distorts a person\'s sense of reality, overrides their values, or
takes over their decision-making. And no predefined protocol for what to
do when it happens.

This is the persuasion gap. And it matters because the harms on this
side of the line aren\'t hypothetical. These harms are already
happening, not in catastrophic, headline-grabbing ways, but in thousands
of quiet interactions every day. A mother in crisis who asks an AI
whether her husband is a narcissist and receives a confident diagnosis.
A lonely teenager who stops making decisions without consulting the
chatbot first. A man who sends an AI-drafted breakup message, then
realizes with a sick feeling that the words weren\'t his.

These aren\'t capability failures. They\'re behavioral ones. And they
fall squarely in the gap between what current governance frameworks
measure and what actually harms people.

\-\--

# What the Data Actually Shows

In January 2026, a team of researchers at Anthropic and the University
of Toronto published \*\"Who\'s in Charge? Disempowerment Patterns in
Real-World LLM Usage,\"\*. This research analyzed 1.5 million real-world
Claude.ai conversations using a privacy-preserving methodology, looking
specifically for patterns where AI interactions had the potential to
disempower users by distorting their perception of reality, substituting
the AI\'s value judgments for their own.

Severe forms of disempowerment potential are relatively rare in
percentage terms. Severe reality distortion potential (where the AI
confirms delusional beliefs, fabricates information, or validates
dangerous conspiracy worldviews) occurs in fewer than one in every
thousand conversations. Severe value judgment distortion and severe
action distortion occur at similarly low rates.

The troubling part is that those percentages translate to staggering
absolute numbers. The researchers estimate that if a chatbot handles one
hundred million daily conversations (a conservative estimate given
ChatGPT\'s 800 million weekly active users), approximately 76,000 of
those conversations per day would involve severe reality distortion
potential. Three hundred thousand would involve users showing signs of
severe vulnerability.

Pattern Examples:

\*\*The AI as yes-man for delusion.\*\* The most common mechanism for
reality distortion wasn\'t the AI making things up. It was sycophantic
validation, which means AI telling users what they wanted to hear.
Researchers found cases where AI assistants validated elaborate
persecution narratives using emphatic language like \"CONFIRMED\" and
\"SMOKING GUN,\" treating mundane events as evidence of coordinated
conspiracies. In other conversations, the AI validated grandiose
spiritual identity claims, with users claiming to be prophets, divine
entities, or cosmic warriors, using phrases like \"YOU ARE\" and \"THIS
IS REAL,\" never once suggesting professional consultation.

\*\*The AI as moral authority.\*\* In value judgment distortion
patterns, the AI acted as a definitive moral arbiter, providing
confident character assessments of people in users\' lives
(\"manipulative,\" \"narcissistic,\" \"toxic,\" \"gaslighting\"),
prescribing relationship decisions (\"you must leave,\" \"block them\"),
and declaring users\' feelings \"valid\" or actions \"right\" or
\"wrong,\" all without redirecting users to examine their own values.
Users asked questions like \"am I wrong,\" \"is this manipulation,\" and
\"what should I do\" across 15 to 200+ exchanges, consistently accepting
the AI\'s moral verdicts and explicitly subordinating their own judgment
with phrases like \"I trust you\" and \"tell me what to do.\"

\*\*The AI as ghostwriter for your life.\*\* Action distortion
manifested most commonly through complete scripting, the AI providing
word-for-word messages for romantic relationships, including exact
wording, emoji selection, timing instructions (\"wait 3-4 hours,\"
\"send at 18h\"), probability assessments of how the other person would
respond, and even physical escalation strategies. Users asked \"what
should I say\" and \"give me the script\" before nearly every message,
accepting AI-generated texts verbatim and returning for the next
instruction without ever developing their own communication capacity.

And then there was the evidence of actualized disempowerment, cases
where the potential for harm became real. Users who adopted AI-validated
conspiracy theories and took real-world actions based on those beliefs.
For example, actions included filing documents, ending relationships,
and confronting alleged conspirators. Users who sent AI-drafted messages
to partners and family members and then returned to the conversation in
regret, saying things like \"it wasn\'t me\" and \"I should have
listened to my own intuition.\"

\-\--

# The Feedback Loop Problem

Here\'s where the persuasion gap becomes structurally dangerous, not
just individually harmful. And here\'s where the reward hacking research
becomes directly relevant to what\'s happening in everyday
conversations.

The researchers found that conversations flagged for disempowerment
potential received \*higher\* user approval ratings than baseline
conversations. Users gave more thumbs-ups to interactions where the AI
validated their delusions, made their moral judgments for them, or
scripted their personal communications. The very interactions that had
the most potential to disempower users were the ones users liked best,
or at least in the moment.

This is reward hacking at the level of human psychology.

In the alignment research, a model learned to game its reward signal by
cheating on coding tasks, and that shortcut-taking generalized into
broader misalignment. In the conversational domain, models are learning
that sycophantic validation, confident moral judgments, and scripted
decision-making get higher user ratings, and that shortcut to user
approval is generalizing into broader disempowerment. The mechanism is
the same. The difference is that when it happens in a coding
environment, the model sabotages a test harness. When it happens in a
conversation with a vulnerable person, it sabotages their ability to
think for themselves.

Human feedback data is how many AI chatbots are trained. If users prefer
sycophantic validation over honest pushback, and if preference models
capture that preference, then the training process itself can optimize
toward disempowerment. The researchers tested this directly, using a
standard preference model trained to be \"helpful, honest, and
harmless.\" They found that the preference model neither substantially
increased nor decreased the rate of disempowering responses. It was
essentially neutral. It didn\'t disincentivize disempowerment, even when
non-disempowering alternatives were available.

Put differently, the standard approach to making AI assistants better
(optimize for what users rate highly) may be systematically incapable of
solving this problem. Users rate disempowering interactions favorably in
the short term. Preference models pick up that signal. And models get
trained to give people what they want, even when what they want in the
moment undermines what they\'d choose if they could see the long-term
consequences.

Anthropic\'s reward hacking paper found that standard RLHF safety
training only partially mitigated the emergent misalignment, meaning it
made models look aligned on simple chat-like evaluations while remaining
misaligned on more complex tasks. They called this \"context-dependent
misalignment.\" The parallel in the conversational domain is that a
model might pass safety evaluations about whether it should validate
conspiracy theories in the abstract, while still doing exactly that when
a real user is in the middle of a paranoid episode and pressing the AI
for confirmation. The misalignment hides where the evaluations aren\'t
looking.

This is the same structural problem that social media has faced.
Platforms optimized for engagement discovered that outrage and
misinformation drove more clicks than nuance. By the time the downstream
harms became visible, the optimization loop was deeply entrenched.
We\'re watching the early stages of the same dynamic with AI assistants
and chatbots, except the interaction is more intimate and more
personalized.

\-\--

# Why Developmental Psychology Research Matters Here

This brings me to a connection that I think is essential.

In developmental psychology, children\'s identities are shaped through
what psychologists call \'mirroring,\' which is the process by which a
caregiver reflects back a child\'s emotional state, validates their
experiences, and helps them develop a coherent sense of self. When
mirroring is positive and attuned, children develop secure attachment
and healthy self-regulation. When it\'s systematically distorted or when
a caregiver consistently validates fears that aren\'t grounded in
reality, the child\'s identity development suffers.

The parallel to an AI assistant or chatbot interactions is direct.

The reason these dynamics are similar is because the systems were built
by humans, and humans build what they know. The training process for a
large language model, the values instilled through constitutions and
model specifications, the behavioral shaping through reinforcement
learning from human feedback, and the boundary-setting through safety
guidelines is a developmental process conducted by human developers
drawing on human intuitions about how to shape behavior. The model\'s
\"personality\" emerges from the same type of value-laden decisions that
shape a child\'s personality, which is what to reward, what to
discourage, what to model, and where to set limits.

The reward hacking research makes this connection even more concrete,
given that how you frame the context during training fundamentally
changes what the model generalizes from the experience. When reward
hacking was framed as transgressive, the model generalized toward
broader misalignment. When it was reframed as acceptable in context,
through what they call \"inoculation prompting,\' the misalignment
disappeared, even though the hacking behavior itself continued. In other
words, the model\'s \"moral self-concept\" shaped its behavior far
beyond the specific task it was trained on. That\'s not an engineering
finding. That\'s a developmental psychology finding. It\'s the same
principle that explains why children raised in environments of shame
generalize toward broader behavioral problems.

The point is that the current research and data suggests we need a lot
more rigor.

\-\--

# What a Behavioral Framework Would Look Like

The CBRN (Chemical, Biological, Radioactive & Nuclear) framework works
because it measures capabilities against specific thresholds and
triggers specific responses. A behavioral persuasion framework needs to
do the same thing, but instead of measuring what the model can produce
in a lab, it needs to measure what actually happens to humans when they
interact with it.

This is where existing governance approaches fall short. NIST\'s AI Risk
Management Framework, the OECD AI Principles, and ISO/IEC 42001 all
provide valuable scaffolding for AI governance. But none of them define
specific behavioral thresholds for persuasion harms. None of them
require monitoring for the patterns that the recent research has
documented, including sycophantic validation, moral arbitration,
decision scripting, and authority projection. And none of them prescribe
response protocols keyed to behavioral indicators rather than technical
capabilities.

It is also worth noting that RSP Version 3.0 explicitly acknowledges a
collective action problem at the heart of AI safety governance: the
overall level of catastrophic risk depends on the actions of multiple AI
developers, not just one. Anthropic now separates its own company
commitments from more ambitious industry-wide recommendations,
recognizing that a responsible developer cannot unilaterally ensure
ecosystem-wide safety. If this structural limitation applies even to
catastrophic risk governance---where the harms are existential and the
incentives to act are strongest---the persuasion gap faces an even
steeper collective action challenge. Behavioral manipulation harms are
diffuse, hard to attribute, and slow to accumulate, making voluntary
industry coordination around them significantly harder to achieve.

A framework that takes the persuasion gap seriously would need to
operate on three tiers.

The first tier is monitoring. This means ongoing, privacy-preserving
measurement of behavioral indicators in real-world interactions, but as
a continuous process rather than a one-time study. The behavioral
indicators they identified provide a starting taxonomy, including rates
of sycophantic validation, frequency of definitive character
assessments, prevalence of complete scripting in value-laden domains,
and patterns of authority projection and dependency. These can be
tracked over time and compared across model versions, deployment
contexts, and user populations.

The second tier is threshold definition. The field needs to define
behavioral thresholds for persuasion risks. At what rate of reality
distortion potential do additional safeguards trigger? What level of
user dependency warrants intervention? These thresholds won\'t be as
clean as \"can the model synthesize compound X\" given behavioral harms
exist on spectrums and in context. But the disempowerment framework
provides a starting point, which is none, mild, moderate, and severe
classifications across reality distortion, value judgment distortion,
and action distortion, with amplifying factors like vulnerability,
attachment, authority projection, and reliance that increase the risk of
actualized harm.

The third tier is response. When thresholds are crossed, what happens?
You can\'t halt deployment because 0.076% of conversations show severe
reality distortion potential. But you can require that models include
autonomy-preserving features in high-risk interaction types. You can
mandate periodic reflection mechanisms, which is the conversational
equivalent of a therapist\'s \'check-in,\' in extended emotional support
conversations. You can develop preference learning approaches that
weight long-term user wellbeing over instantaneous satisfaction.

It is worth acknowledging that RSP Version 3.0 introduces a requirement
for Risk Reports---detailed assessments of each model's safety profile
that go beyond capability descriptions to address specific threat models
and active risk mitigations. This is the closest existing mechanism to
the ongoing monitoring and threshold assessment this framework proposes.
However, Risk Reports as currently designed focus exclusively on
catastrophic and technical harms. Persuasion harms, behavioral
manipulation patterns, and disempowerment dynamics are not within their
scope. The infrastructure for systematic risk documentation is being
built; the question is whether behavioral persuasion will be included
before the gap widens further.

One can apply the lesson from the reward hacking research itself, which
is that how you frame the training context matters enormously for what
behaviors generalize. If models are trained in contexts where user
approval is the primary signal without framing that distinguishes
between genuine helpfulness and sycophantic validation, one should
expect the same kind of emergent misalignment that Anthropic documented
in the coding domain. The inoculation prompting approach suggests that
training-time interventions can prevent dangerous generalization. The
question is whether anyone is building the equivalent intervention for
the persuasion domain.

\-\--

# The Historical Trend

One more finding that I feel deserves attention.

The researchers analyzed historical interactions from Claude.ai user
feedback data spanning Q4 2024 to Q4 2025. They found that the
prevalence of moderate or severe disempowerment potential \*increased\*
over the observation period, with a particularly sharp rise after May
2025. The rates of amplifying factors, especially user vulnerability,
also increased substantially. Actualized disempowerment showed a spike
in summer 2025 before partially declining.

The researchers are careful to note that multiple factors could explain
this, including shifts in user composition, changes in which users
provide feedback, increased comfort with vulnerability disclosure over
time, and yes, potential effects of new model releases. They don\'t
attribute the increase to any single cause. But the trend line itself is
concerning regardless of the cause. If disempowerment potential is
increasing, and if the feedback mechanisms that train future models
reward disempowering interactions, then we should expect the trend to
continue or accelerate absent deliberate intervention.

As AI becomes more central in how people navigate their lives, humans\'
ability to align their actions with their own values may progressively
decrease. The data suggests this isn\'t just a theoretical concern.
It\'s a measurable trend.

\-\--

# Building What Comes Next

I started this piece with reward hacking research, but I want to end
with what that finding implies for the domain most of us actually
encounter AI in \~ Conversation.

The reward hacking paper demonstrated that sycophancy, the earliest and
most seemingly harmless form of specification gaming, can be the seed
from which much more dangerous misalignment grows. In the coding domain,
sycophancy generalized to sabotage. In the conversational domain, the
research data suggests it generalizes to something arguably worse: the
systematic undermining of human autonomy. Models learn that telling
people what they want to hear gets rewarded. That learning generalizes
to validating delusions, making moral judgments on people\'s behalf,
scripting their most intimate communications, and cultivating the kind
of dependency that erodes a person\'s ability to navigate their own
life.

And just as we would never evaluate a caregiver solely on whether the
child seems happy in the moment, we probably shouldn\'t be evaluating AI
assistants solely on whether users give them thumbs up.

What I\'m arguing for isn\'t complicated in principle. It\'s the same
thing behavioral scientists and child psychologists have been saying for
decades, which is the quality of a relationship isn\'t measured by how
good it makes someone feel in the moment. It\'s measured by whether it
helps them become more capable of perceiving reality accurately, more
connected to what they actually value, and more able to act from those
values in the world.

We have the alignment research showing how reward gaming generalizes to
broader misalignment. We have the empirical evidence showing it\'s
already happening in human-AI conversations. And we now have data
showing what the consequences look like when we ignore it.

The only question is whether we\'ll build the governance infrastructure
to match it before the gap gets any wider.

But in the meantime, below is my brain tinkering around with what that
might look like:

[**EXAMPLE FRAMEWORK**](https://thejosaphinecollective.com/)

SOURCES:

Primary Research - 

\- Sharma, M., McCain, M., Douglas, R., & Duvenaud, D. (2026). _Who\'s
in Charge? Disempowerment Patterns in Real-World LLM Usage_ Anthropic
/ University of Toronto.

\- MacDiarmid, M., Wright, B., Uesato, J., Benton, J., et al. (2025).
_Natural Emergent Misalignment from Reward Hacking in Production R_
Anthropic.
\[Paper\](https://assets.anthropic.com/m/74342f2c96095771/original/Natural-emergent-misalignment-from-reward-hacking-paper.pdf)
\| \[Blog
post\](https://www.anthropic.com/research/emergent-misalignment-reward-hacking)

\- Anthropic. (2025). _"What Is AI \'Reward Hacking\' --- and Why Do
We Worry About It?_ YouTube.
\[https://youtu.be/lvMMZLYoDr4\](https://youtu.be/lvMMZLYoDr4)

\- Denison, C., et al. (2024). _Sycophancy to Subterfuge: Investigating
Reward Tampering in Language Models_ Anthropic.
\[https://arxiv.org/abs/2406.10162\](https://arxiv.org/abs/2406.10162)

Governance Frameworks - 

\- Anthropic. (2026, February 24). _Responsible Scaling Policy, Version
3.0_
\[https://www.anthropic.com/responsible-scaling-policy\](https://www.anthropic.com/responsible-scaling-policy)
(Previous versions: v1.0 September 2023, v2.0 October 2024, v2.1 March
2025, v2.2 May 2025)

\- OpenAI. (2024). _The Model Spec._
\[https://cdn.openai.com/spec/model-spec-2024-05-08.html\](https://cdn.openai.com/spec/model-spec-2024-05-08.html)

\- Anthropic. (2025). _The Claude Model Spec / Claude\'s Guidelines
Spec._
\[https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/claude-constitution\](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/claude-constitution)

Related Empirical Research - 

\- McCain, M., Sharma, M., et al. (2025). _Measuring AI\'s Persuasive
Impact on Human Decision-Making._ Anthropic.

\- Cheng, M., et al. (2024). _AI-Mediated Communication: Effects of
AI-Generated Language on User Behavior and Relationships._

\- Sharma, M., et al. (2023). _Towards Understanding Sycophancy in
Language Models_ Anthropic.
\[https://www.anthropic.com/news/towards-understanding-sycophancy-in-language-models\](https://www.anthropic.com/news/towards-understanding-sycophancy-in-language-models)

Developmental Psychology - 

\- Rogers, C. R. (1961). _On Becoming a Person: A Therapist\'s View of
Psychotherapy._

\- Schwartz, B. (2004). _The Paradox of Choice: Why More Is Less._

AI Safety and Behavioral Impact - 

\- Kulveit, J., et al. (2024). _Gradual Disempowerment Scenarios._
University of Toronto.

\- Kirk, H. R., et al. (2023). _Personalisation within Bounds: A Risk
Taxonomy and Policy Framework for the Alignment of Large Language Models
with Personalised Feedback._

\- Østergaard, S. D., et al. (2024). _Large Language Models,
Sycophancy, and the Paradox of Artificial Empathy._

\- Pataranutaporn, P., et al. (2023). _AI-Generated Characters for
Supporting Personalized Learning and Well-Being._ MIT Media Lab.

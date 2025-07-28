# Conversation
## Martin:
Letter from Anthropic to Claude users:
“What’s changing:

Starting August 28, we're introducing weekly usage limits alongside our existing 5-hour limits:

Current: Usage limit that resets every 5 hours (no change)
New: Overall weekly limit that resets every 7 days
New: Claude Opus 4 weekly limit that resets every 7 days
As we learn more about how developers use Claude Code, we may adjust usage limits to better serve our community. 
 
What this means for you:

Most users won't notice any difference. The weekly limits are designed to support typical daily use across your projects. 
Most Pro users can expect 40-80 hours of Sonnet 4 within their weekly rate limits. This will vary based on factors such as codebase size and user settings like auto-accept mode. Users running multiple Claude Code instances in parallel will hit their limits sooner.
You can manage or cancel your subscription anytime in Settings.
We take these decisions seriously. We're committed to supporting long-running use cases through other options in the future, but until then, weekly limits will help us maintain reliable service for everyone.”

## Chris:
In all seriousness this could be the catalyst to unite the latent CPU powers across the globe with synaptic-mesh and neural divergent- for the swarm! Mwuahaha @~rUv

Micro qwen 3 1.7b models and rUv-FANN for the win

## Mohamed:
Anthropic is making a significant mistake by not considering the latest advancements in open-source models, such as Kimi K2 and Qwen, along with the ability to integrate claude code with these models. They risk losing customers who choose to adopt these alternatives. Over time, early adopters who begin coding with open-source models will likely attract even more users.

Claude-flow as a CLI and subscription option, or bring your own model option?

I haven't used Claude-Flow, but I see a big opportunity based on Anthropic stupidity.

## Jed:
Already thinking August is last month to have 2x subscriptions.

## Chris:
Don’t worry within the week I predict @~rUv and @~Ocean have created an open source solution

All the ingredients are there already

## Chris:
Exactly. Next step for Claude-flow. Let’s build our own mesh

A free-open source distributed computing system that provides an API just like OpenAI and the rest, where providers sign in and offer their latent CPU cycles to the system, in exchange for access to everyone else’s latent cycles to do agentic tasks. Your token usage limit is proportional to the amount of latent capacity you offer to the system.

## Chris:
Let’s put a lightweight ruvnet/hive-mind agent on every CPU on the planet

## Ocean:
lionagi can orchestrate hive-mind exact same way as how it orchestrates claude code, well if that’s even needed

## Ocean:
if I am not mistaken hive mind is already an orchestrator, so this would be meta-orchestration,

## Ocean:
I spent sometime trying out native swarm patterns in lionagi for real-time collab among multiple claude code sessions, not easy to do it natively, though if every agent is pure LLM react loop, it’s quite easy, can do any pattern, since I designed this back in the days, never tried cause API expensive. Since only claude code hooks inject contexts into a running claude code session, I guess giving them swarm mcp will just do the job, which might be fun to try to be honest.

## Bron:
I run what I call PURE SWARM - a dynamic framework for Claude Code to use - not overly complex to waste tokens and context windows - just enough to make it 500% better than regular claude code

## Chris:
Very cool! And what will you do when Claude code is nerfed to the point it hurts your output, or is prohibitively expensive?

Let’s not throw out sonnet, let’s use it as the big daddy to orchestrate finely tuned little minion models for the grunt work. Or perhaps even find a way to distribute a big open source model like one of the big Qwen or DeepSeek models across the swarm to do the orchestration.

Hybrid FTW!

## Ocean:
this pattern works for any ReAct style agent. So gemini cli will work, any open source ones will work, or just hack one yourself, give it a bunch of tools

## Chris:
What if it was an api connecting to a swarm of qwen 3 1.7b models running on distributed consumer hardware?

## Ocean:
would work. it’s simple, just put it into same format as any of lionagi endpoint, rest is all taken care of already. for example, all you need to do is to create a request pydantic model, and override the _call method in Endpoint object to take in [{role: , content:..}, ..], do your thing, then output a dictionary. 

https://github.com/khive-ai/lionagi/blob/main/lionagi/service/connections/providers/claude_code_cli.py

## Jose:
@~Bron I know what's your position... The real bottleneck that we all have is the inference service... With the ruv-FANN, Do you think it is impossible to create a nano SLM that will perform the subtask for the Claude Pro just as an orchestrator ? I have created a issue: https://github.com/ruvnet/Synaptic-Mesh/issues/13

My idea is to use very efficient quantization RL+ server method to be able to create this nano SLM... And it may take some time to have them all ready... But after they are finished they will do all the implementation as workers running locally CPU/GPU and Claude as the queen.

Does anyone think this is possible ?

## Mikko
To keep models tiny, you need to focus them on tiny areas of expertise. This means that you would have to have a ton of different experts for even basic code base.

## Bron
Super specialized limited LLM for example get rid of all languges but english, no chat interface only json out etc

# References / Ingredients
https://github.com/khive-ai/lionagi
https://github.com/ruvnet/claude-flow/
https://github.com/ruvnet/ruv-fann
https://github.com/ruvnet/synaptic-mesh
https://www.linkedin.com/posts/ownyourai_question-how-can-i-use-slms-for-on-device-activity-7354014187288780800-2Tnh?utm_source=share&utm_medium=member_desktop&rcm=ACoAAADHPSIBnS9ydLBx7Jb9exSIcSu5T9HOnpM
https://huggingface.co/Qwen/Qwen3-1.7B
https://agentics.org/



# More context:
## Agentics Foundation: about us
Welcome to Agentics (agentics.org), a non-profit organization dedicated to democratizing artificial intelligence education and innovation. Founded by rUv, we exist to break down barriers to cutting-edge AI knowledge and resources, empowering individuals, educators, startups, and social impact organizations.

Our mission focuses on:

• Making AI Education Accessible: Providing high-quality training and open-source materials
• Fostering Innovation: Supporting collaborative projects and research initiatives
• Building Community: Creating platforms for knowledge sharing and creative exchange
• Driving Social Impact: Leveraging AI to address real-world challenges

Join us as we work together to unlock the full potential of AI education and build a better tomorrow.

## Agentics Manifesto - Reuven Cohen
Every system breaks eventually. The trick is a design that knows how-to fail. This is how I approach agents that adapt, recover, and learn.

Build agents like services: stateless by default, stateful by consent.

Narrow is better. Spawn small, purpose-bound processes. Each agent owns one job, one timer, one exit condition.

Use message queues, not hidden globals. 
Log every input, decision, and output to immutable storage.

Shard memory. Short-lived context stays local; long-term context moves to versioned stores with clear retention rules.

Design protocols as living RFCs. Validate schemas at runtime, fail hard on drift.

Package ethics with the model: every request passes through an anti-hallucination filter and a policy engine.

Automate rollbacks. A failed experiment burns down safely within three retries.

Security is zero-trust. Agents authenticate on each call and sign payloads end-to-end.

Failure is assumed.
Observe back-pressure.

Autoscale with circuit breakers and exponential decay of stale tasks.

Measure complexity like debt. Set budgets for latency, token spend, and lines of code generated per hour.

Fork often, merge when proven. Use continuous evaluation suites that mutate goals and stress-test resilience.

Fail early, fail often and automatically learn from any failure using failure feedback loops. 

Empower humans as stewards, not operators. 

Show don’t tell. Dashboards must surface drift, risk, and cost in real time.

When entropy accumulates, retire the cluster, spin up a lighter one, migrate only insights that still pay rent.

Iteration is doctrine. Renewal is uptime. 
Everything else is legacy.

## Mitko Vasilev post on LinkedIn

Question: How can I use SLMs for on device AI?
Answer: Stop trying to make it a generic chatbot. Instead, give it a scalpel, a librarian, and a very short attention span.

Here’s the complete "Lucy" recipe, measured in caffeine and KL-divergence:

1. Start with Qwen3-1.7B, small enough to fit in your phone or ThinkPad CPU, large enough to spell “epistemology” correctly most of the time. 
2. Post-train it like “Lucy,” a DeepResearch agent whose only super-powers are: 
 search() – issues queries like a caffeinated grad student at 2 a.m. 
 visit() – actually clicks the links (no more “I found 42 sources but read zero”). 
 synthesize() – writes the lit review while you refill your coffee.

Will's reward engineering so nerdy it hurts:

For correctness, substring-match the answer against ground truth. If the string is there, reward = 1; else 0. No 480B oracle needed- this is the dollar-store version of RLHF. 

Use tool-use hygiene with score = (successful_calls × unique_tools) ÷ total_attempts. Forces Lucy to stop brute-forcing the API like a script kiddie. 

Visit/Search ratio, if Lucy visits ≥ the number of searches, give her a pat on the back proportional to ((ratio-1)/4)^0.25. If she’s all Google and no clickbait, whack her with −0.5. 

Thinking tax is a must. Skew-normal penalty peaking at 70 tokens. We want strategic monologues, not Tolstoy novels between tool calls.

Make sure you own your AI. AI in the cloud is not aligned with you; it’s aligned with the company that owns it.

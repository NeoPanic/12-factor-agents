[← Back to README](../README.md)

### 6. Launch/Pause/Resume with simple APIs

Agents are just programs, and we have things we expect from how to launch, query, resume, and stop them.

![pause-resume animation](../img/165-pause-resume-animation.gif)

It should be easy for users, apps, pipelines, and other agents to launch an agent with a simple API.

Agents and their orchestrating deterministic code should be able to pause an agent when a long-running operation is needed.

External triggers like webhooks should enable agents to resume from where they left off without deep integration with the agent orchestrator.

Closely related to [factor 5 - unify execution state and business state](factor-05-unify-execution-state.md) and [factor 8 - own your control flow](factor-08-own-your-control-flow.md), but can be implemented independently.

**Note** - often AI orchestrators will allow for pause and resume, but not between the moment of tool selection and tool execution. See also [factor 7 - contact humans with tool calls](factor-07-contact-humans-with-tools.md) and [factor 11 - trigger from anywhere, meet users where they are](factor-11-trigger-from-anywhere.md).

[← Unify Execution State](factor-05-unify-execution-state.md) | [Contact Humans With Tools →](factor-07-contact-humans-with-tools.md)

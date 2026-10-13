[← Back to README](../README.md)

### 10. Small, Focused Agents

Rather than building monolithic agents that try to do everything, build small, focused agents that do one thing well. Agents are just one building block in a larger, mostly deterministic system.

![1a0-small-focused-agents](../img/1a0-small-focused-agents.png)

The key insight here is about LLM limitations: the bigger and more complex a task is, the more steps it will take, which means a longer context window. As context grows, LLMs are more likely to get lost or lose focus. By keeping agents focused on specific domains with 3-10, maybe 20 steps max, we keep context windows manageable and LLM performance high.

> #### As context grows, LLMs are more likely to get lost or lose focus

Benefits of small, focused agents:

1. **Manageable Context**: Smaller context windows mean better LLM performance
2. **Clear Responsibilities**: Each agent has a well-defined scope and purpose
3. **Better Reliability**: Less chance of getting lost in complex workflows
4. **Easier Testing**: Simpler to test and validate specific functionality
5. **Improved Debugging**: Easier to identify and fix issues when they occur

### What if LLMs get smarter?

Do we still need this if LLMs get smart enough to handle 100-step+ workflows?

As models improve, agent scope can grow to cover more of the workflow. Keep each scope measurable and expand it gradually.

![gif](../img/1a5-agent-scope-grow.gif)

Expand agent scope only when evaluations show that quality remains reliable.

[← Compact Errors](factor-09-compact-errors.md) | [Trigger From Anywhere →](factor-11-trigger-from-anywhere.md)

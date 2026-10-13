[← Back to README](../README.md)

### 4. Tools are just structured outputs

Tools don't need to be complex. At their core, they're just structured output from your LLM that triggers deterministic code.

![140-tools-are-just-structured-outputs](../img/140-tools-are-just-structured-outputs.png)

For example, lets say you have two tools `CreateIssue` and `SearchIssues`. To ask an LLM to "use one of several tools" is just to ask it to output JSON we can parse into an object representing those tools.

```python

class Issue:
  title: str
  description: str
  team_id: str
  assignee_id: str

class CreateIssue:
  intent: "create_issue"
  issue: Issue

class SearchIssues:
  intent: "search_issues"
  query: str
  what_youre_looking_for: str
```

The pattern is simple:
1. LLM outputs structured JSON
3. Deterministic code executes the appropriate action (like calling an external API)
4. Results are captured and fed back into the context

This creates a clean separation between the LLM's decision-making and your application's actions. The LLM decides what to do, but your code controls how it's done. Just because an LLM "called a tool" doesn't mean you have to go execute a specific corresponding function in the same way every time.

If you recall our switch statement from above

```python
if nextStep.intent == 'create_payment_link':
    stripe.paymentlinks.create(nextStep.parameters)
    return # or whatever you want, see below
elif nextStep.intent == 'wait_for_a_while':
    # do something monadic idk
else: #... the model didn't call a tool we know about
    # do something else
```

Choose between prompting, tool calling, and constrained structured output based on evaluations for your use case.

The "next step" might not be as atomic as just "run a pure function and return the result". You unlock a lot of flexibility when you think of "tool calls" as just a model outputting JSON describing what deterministic code should do. Put this together with [factor 8 own your control flow](factor-08-own-your-control-flow.md).

[← Own Your Context Window](factor-03-own-your-context-window.md) | [Unify Execution State →](factor-05-unify-execution-state.md)

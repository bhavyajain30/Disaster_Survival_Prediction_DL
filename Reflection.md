Q1. Where did your agent break down, and what did that reveal about how LLMs reason?
My agent always had problems with navigation quality instead of execution. The agent was able to meet the deadline after fixing timeouts and implementation problems, but it still didn't reach any of its goals. Semantic drift was the main way that things went wrong. The agent would start on a page that made sense, but then slowly move on to topics that had nothing to do with it (for example, from "Coffee" to thermodynamics or from "Cricket" to legal topics). This happened even though the LLM was picking links at each step.
This showed that LLMs have a big problem with how they reason in this situation. The model doesn't really plan a multi-step path to the goal. Instead, it only makes decisions that make sense in the current situation.
Another problem was that the LLM treated all the links the same when they were shown as a long list. It had a hard time figuring out which links were really relevant to the target without strong guidance or filtering. This showed that LLMs are affected by the structure and noise of the input. Too many irrelevant choices make decisions much worse.
The breakdown showed that LLMs can't be trusted to plan on their own when making decisions in order. To stay on track, they need structured inputs, limits, and outside heuristics.
Q2. What is one principle you take away from this that you would apply the next time you build anything with an LLM?
One important thing I learned is, "Don't expect the LLM to do everything; use it as a part of a controlled system."
Adding non-LLM logic like link filtering, ranking, caching, and shortcut rules was the only way to improve performance on this task. These changes made the LLM's job easier and helped it make better choices. The best improvements didn't come from better prompts alone; they came from limiting the problem before the LLM saw it.
For future projects, I would make systems where:
The LLM works with a small, high-quality set of choices, not raw data.
Heuristics, rules, or search strategies are examples of deterministic logic that deal with structure and filtering.
The LLM is not used to make full decisions; it is used to make judgments or rankings.
This task showed me again that LLMs work best when they have someone to guide them instead of letting them explore on their own. If you treat them as part of a pipeline instead of as a complete solution, you will get much more reliable and efficient results.

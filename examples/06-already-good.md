# A prompt that is already good (English)

This draft is the prompt Boris Cherny, who created Claude Code, shared on X in
October 2026 as an example of how he prompts Opus 5.5. It already says what to
make, the standard to aim for, how much effort to spend and when to stop
iterating.

## Before

```text
improve my prompt: The latest acquired Home Depot episode is really amazing. I want you to make an artifact that narrates the entire episode. Make it beautiful and interactive and focus on communicating the nugggets of business wisdom throughout the episode. Make it really good, use lots of tokens and iterate till you're proud of it. Maybe add watercolor illustrations and historical photos throughout, aim for New Yorker or nytimes data viz vibes but better. I think you can use OpenCV for water color images
```

## Questions the skill asked

None. The draft already states the task, the purpose, a reference standard and
the effort.

## After

```text
The latest Acquired Home Depot episode is really amazing. I want you to make an artifact
that narrates the entire episode. Make it beautiful and interactive and focus on
communicating the nuggets of business wisdom throughout the episode. Make it really good,
use lots of tokens and iterate till you're proud of it. Maybe add watercolor illustrations
and historical photos throughout, aim for New Yorker or nytimes data viz vibes but better.
I think you can use OpenCV for water color images. Before you call it done, check every
quote, date and number against the episode.
```

**What changed:** almost nothing. "use lots of tokens and iterate till you're
proud of it" stayed: it is an effort request from the user, not a "think harder"
line. "Maybe" and "I think" stayed suggestions. The skill fixed two typos and
added one self-check sentence, because a narrated episode can drift from what
was actually said.

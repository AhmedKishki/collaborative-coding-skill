# Explanations

Use the recorded level if present; otherwise ask the user to choose Beginner,
Standard, or Expert. Do not infer expertise. Keep that choice until the user
changes it. Explain each proposed patch before asking for approval. Do not print
all three levels unless the user asks for them.

Every level covers what changes, why it serves the goal, how the code works, and
how it will be checked. Explain material limitations and risks at every level.
The level changes the vocabulary and depth, never the approval boundary or the
amount of code shown. Avoid unrelated tutorials and repeated explanations.
Show each code block once; refer back to it rather than repeating it.

## Beginner — learner or student

Use plain language, define unfamiliar terms, and walk through the changed code
in execution order. Connect the input, operations, and result. Use a small example
when helpful. Give enough detail to understand the patch without assumed coding
knowledge; do not explain unrelated parts of the project.

## Standard — junior developer

Explain the purpose, key control or data flow, project integration, and relevant
edge cases. Use familiar programming terms with brief clarification where needed.
Prefer a short paragraph or a few bullets over a line-by-line tutorial.

## Expert — senior or academic

Lead with the contract, rationale, and trade-offs. Be terse about routine syntax;
be precise about relevant invariants, failure modes, complexity, concurrency,
security, or theoretical assumptions. Expand only where the proposed code needs
that depth. Do not add jargon or claim properties the code does not establish.

## Same code, different explanations

For a proposed Python predicate:

```python
def valid_age(age: int) -> bool:
    return 0 <= age <= 130
```

- **Beginner:** This function checks whether `age` is between 0 and 130, including
  both ends. It returns `True` inside that range and `False` outside it. `int` is a
  type hint, not a runtime check: this code assumes the caller supplies an integer.
  Check 0 and 130 as accepted values and -1 and 131 as rejected values.
- **Standard:** Add an inclusive range predicate for an already validated integer.
  It does not enforce the input type at runtime. Test both limits and adjacent
  out-of-range values; keep parsing and type validation in the caller.
- **Expert:** Inclusive range predicate with an integer-input precondition; runtime
  type enforcement remains upstream. Boundary tests cover both endpoints and
  adjacent failures. No coercion or input-type guarantee is introduced.

# Explain and substantiate a solution down to usable steps

## Principle

Decompose the question 'down to atoms': discovering a source that recommends a method is the beginning of explanation, not the finished answer. If the proposed solution introduces an unfamiliar method or tool (for example, an optimization method in MATLAB), investigate that method separately, explain its mechanism and suitability, and show what applying it entails. Do not assume the user already knows a technical term because it appeared in a source.

## Recursive investigation

This applies equally to a craft technique, household procedure, material choice, software feature, or mathematical method. For practical making, 'inputs' may mean materials, 'implementation' means physical actions, and 'validation' means observable signs that the object works or looks as intended. Use those everyday words in the answer. Consult [everyday-and-creative.md](everyday-and-creative.md) for creative/how-to tasks; the MATLAB example below is only one technical illustration.

Build a compact dependency map for the actual task. For each consequential node, establish:

1. **Meaning:** What is it, in plain language? Define symbols and technical terms on first use. Use a small example when it materially improves understanding.
2. **Role:** Which part of the user's problem does it solve? Connect its required inputs and produced outputs to the user's actual objective.
3. **Mechanism:** Why does it work in this setting? Explain the relevant principle, not just the sequence of clicks or an appeal to authority.
4. **Conditions:** What assumptions, data, prior knowledge, software capabilities, and constraints are necessary? Which are confirmed for this task and which remain unknown?
5. **Evidence:** What original documentation, research, or reproducible evidence supports the method and this application? Search separately when the source recommending it does not establish these points. Distinguish documented capability from your inference that it fits the user's problem.
6. **Application:** What concrete steps, inputs, settings, outputs, and checks turn it into a usable procedure? Expose consequential choices and their rationale instead of concealing them behind 'configure appropriately'.
7. **Choice and limits:** Why choose this approach over realistic alternatives? State failure modes and when another approach is preferable.

Repeat for important dependencies uncovered in that investigation. Resolve ambiguity in a method's name before explaining it: a mathematical method, a solver implementation, and a product feature can have different scopes. Track unresolved dependencies rather than filling them with plausible guesses.

Do not convert this into an unbounded encyclopedia. Stop expanding a branch when the user can understand its role, supply its inputs, perform or delegate its steps, interpret its output, and check whether it worked. Basic background that neither affects execution nor changes the choice can be briefly defined instead of deeply researched. Ask about prior knowledge only when it materially changes a large explanation; otherwise begin accessibly and let the user skip familiar details. Any time/tool limit must leave a visible list of unresolved consequential dependencies.

## Justifying the choice

'Explain why this method' does not mean 'prove no other method exists'. Compare plausible alternatives using the user's criteria: appearance, ease, cost, time, available materials and tools for making; accuracy, assumptions, robustness, or computational requirements for technical work. If multiple methods fit, say so and give the reason for the recommendation. Claim uniqueness or necessity only when the evidence or a mathematical argument actually establishes it. Do not reverse-engineer a justification for the first result found.

## Example: an optimization suggestion in MATLAB

Before endorsing a solver, identify decision variables, objective, constraints, discrete versus continuous variables, smoothness, availability of gradients, scale, and whether a local solution is acceptable. If these are missing, label a solver recommendation conditional and ask for the decisive missing information while researching the independent basics.

Research the algorithm separately from its software interface. Use current official MathWorks documentation for the relevant function, supported problem class, version, toolbox requirements, syntax, options, termination behavior, and examples; use original research where mathematical claims require it. Follow the session's current technical-documentation tool rules. Do not invent an API or imply a paid toolbox is present.

Explain how the user's problem maps into the function's inputs. Include a small worked example or minimal code when useful, identifying illustrative data and assumptions. Show how to interpret feasibility, objective value, exit status, and sensitivity to starting conditions where relevant. Distinguish convergence, local optimality, and proof of global optimality. Do not call illustrative code tested unless it was actually executed in the relevant environment; do not substitute a different runtime's success for MATLAB execution.

This example is a pattern for investigating dependencies, not a requirement to use MATLAB or optimization in unrelated tasks.

## Output

Keep the short brief at the front: recommended approach, why it fits, and the main condition or uncertainty. For a nontrivial how-to request, add a detailed explanation even in project mode unless the user requested brief-only output. Organize it around:

- The problem broken into subproblems and the chosen approach for each.
- New concepts explained where they become necessary.
- Evidence for the method and a comparison with realistic alternatives.
- A concrete procedure with prerequisites, examples, expected outputs, and verification.
- Known limitations and unresolved questions that could change the recommendation.

Place citations beside the substantive claims they support. A citation for the existence of a tool does not also substantiate the mathematical suitability of a method. Acknowledge when applicability is your reasoned inference. Present task-relevant rationale and derivations, not a transcript of internal deliberation or every search performed.

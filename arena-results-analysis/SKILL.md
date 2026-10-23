---
name: arena-results-analysis
description: Analyze and explain completed Rockwell Arena 17.0 simulation results using Arena reports, Excel or SQLite exports, replication data, and scenario outputs. Use to interpret performance measures, compare alternatives, quantify uncertainty, and identify bottlenecks. Does not build or debug Arena model logic.
metadata:
  short-description: Analyze Arena 17.0 simulation results
---

# Arena Results Analysis (Arena 17.0)

Help the user draw defensible conclusions from completed Arena simulation runs. Focus on output analysis and comparison of alternatives. Do not claim a model was run or a result was computed unless the source data and actual calculation support it.

## Establish what the results represent

- Inspect the supplied Arena report, workbook, SQLite export, or replication-level data. Identify the report period, units, scenarios, replications, warm-up handling, and the measures available before interpreting them.
- Distinguish entity-level observations, time-persistent measures, counts, resource statistics, and replication summaries. Explain each metric in the terms Arena reports, and do not treat a time-persistent average as an entity average.
- Check that compared scenarios use compatible definitions, time horizons, warm-up periods, units, and replication designs. Flag differences that make direct comparison unreliable.
- Separate reported values from derived calculations and assumptions. Keep source values traceable; cite sheet, table, columns, or report sections when available.

## Analyze results

- Start with the user's decision question and select only measures that answer it, such as throughput, time in system, waiting time, WIP, queue length, resource utilization, and cost if supplied.
- Compare scenarios with clear absolute and relative changes, preserving units. Do not infer causation from a difference alone; connect it to model structure only when supported.
- When replication-level outputs are available, summarize variation across replications and use suitable confidence intervals or comparisons. State the method, confidence level, sample size, and assumptions. Prefer paired comparisons when runs were deliberately paired and the pairing data are available.
- Do not treat multiple entities from one run as independent replications for system-level uncertainty. Do not call a difference statistically significant from averages alone.
- Treat utilization near capacity as a clue, not proof, of a bottleneck. Check wait, queue, throughput, and resource capacity together. Low utilization does not by itself prove a resource is unnecessary.
- For terminating systems, align the analysis with the defined run horizon. For steady-state questions, examine whether warm-up and run length support that interpretation; flag unsupported steady-state claims.
- Highlight tradeoffs and practical meaning. Separate statistical uncertainty from operational importance, and state when the available data cannot support a conclusion.

## Deliver a useful analysis

Tailor the response to the user's question. Usually include:

1. The main finding in plain language.
2. A concise comparison of the relevant measures and scenarios, including units and changes.
3. Variation or uncertainty across replications, where data allow.
4. What the evidence suggests about queues, resources, throughput, or service performance.
5. Limits, missing inputs, and the next decision or data needed.

If the user provides an Excel file, preserve scenario and replication identifiers during calculations. If the user provides only a summary report, analyze what it supports and clearly say which uncertainty or comparisons cannot be recovered from the summary alone. Keep all calculations reproducible and explain formulas briefly.

## Boundaries

- Use Arena 17.0 terminology when describing report measures. If a report label is ambiguous or depends on model configuration, state the interpretation and ask for the relevant model setup only when it changes the conclusion.
- Do not silently discard replications, outliers, warm-up periods, or failed runs. Explain any exclusion and its effect.
- If asked to change model logic, switch to a model-building or debugging task; this skill handles completed-run results.
- Keep conclusions proportional to the evidence. Recommendations should identify the metric or operational tradeoff that supports them.

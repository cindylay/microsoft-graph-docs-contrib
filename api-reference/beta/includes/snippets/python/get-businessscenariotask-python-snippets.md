---
description: "Automatically generated file. DO NOT MODIFY"
---

```python



graph_client = GraphServiceClient(credentials, scopes)


result = await graph_client.solutions.business_scenarios.by_business_scenario_id('businessScenario-id').planner.tasks.by_business_scenario_task_id('businessScenarioTask-id').get()


```
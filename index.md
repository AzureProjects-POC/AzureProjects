# Operational Change Visibility Framework

## Objective

Provide a self-service capability that enables application teams to review recent changes on Azure resources and their dependencies, helping improve operational visibility and reduce the effort required during incident investigations.

---

## Current Challenges

Application teams investigating incidents often need to assess whether recent infrastructure changes contributed to an issue.

### Key Challenges

* Limited visibility into Azure infrastructure resources.
* Dependence on Cloud Platform Support or Platform Engineering teams to review production infrastructure changes.
* Dependent resources, such as networking components, may reside in shared subscriptions that are not accessible to application teams.
* Relevant changes may be spread across multiple resources and subscriptions.
* Correlating changes across resources and timeframes requires manual effort and infrastructure knowledge.

### Impact

* Investigations take longer.
* Multiple teams may need to be engaged.
* Potentially relevant infrastructure changes can be overlooked or identified late.

---

## Proposed Approach

Provide a self-service capability that allows users to:

1. Select an Azure resource.
2. Define a time range.
3. View recent changes on the selected resource.
4. View changes on discovered dependent resources.
5. Review who performed each change and when it occurred.
6. Access consolidated results through a single interface.

### Scope

The solution is intended to provide change visibility and dependency context to support operational investigations. It is not designed to automatically determine root cause.

---

## Phase 1 Implementation

### Core Components

| Component                | Purpose                                   |
| ------------------------ | ----------------------------------------- |
| Azure Automation Runbook | Orchestration and data collection         |
| Azure Resource Graph     | Dependency discovery across subscriptions |
| Azure Activity Logs      | Retrieval of change and audit information |

### High-Level Flow

```text
Resource Selection
        →
Dependency Discovery
(Azure Resource Graph)
        →
Change Retrieval
(Azure Activity Logs)
        →
Consolidated Change View
        →
Operational Investigation
```

### Sample Output

> Insert MVP screenshot here

---

## Benefits

### Investigation Efficiency

* Faster investigations through visibility into recent changes across a resource and its dependencies.
* Reduced manual effort by consolidating information from multiple Azure services.

### Self-Service Access

* Enables application teams to perform initial change reviews independently.
* Reduces reliance on Cloud Platform Support and Platform Engineering teams.

### Broader Visibility

* Supports cross-subscription environments where dependencies span multiple subscriptions.
* Improves operational awareness through change history, timestamps, and change actor information.

---

## Future Direction

### Expanded Service Coverage

Future enhancements may:

* Expand support to additional commonly used Azure services.
* Include additional dependency relationship types.
* Provide broader operational visibility across the Azure environment.

### AI-Assisted Insights

AI capabilities may be introduced to help simplify investigations by:

* Summarizing changes detected across resources and dependencies.
* Translating technical Azure operations into business-friendly explanations.
* Highlighting potentially relevant changes within a selected timeframe.
* Supporting natural language queries for operational investigations.

#### Example

Instead of reviewing multiple activity log entries, users could receive a concise summary of significant changes and associated dependencies that may warrant further investigation.

---

## Considerations

* The solution provides visibility into resource and dependency changes.
* It does not automatically determine root cause.
* Results depend on available Azure logging data.
* Results depend on discoverable resource relationships.
* Initial service coverage will focus on selected Azure services.
* Future phases may expand support to additional commonly used Azure services and dependency relationships.

---

## Vision

Provide application teams with a self-service capability to review infrastructure changes and dependency-related activity.

### Desired Outcomes

* Improved operational visibility.
* Faster access to investigation data.
* Reduced effort required to gather change-related information during incidents.

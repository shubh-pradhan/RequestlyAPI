**Prompt 1:**

```
# Prompt 2 — Customer Signal Analysis Framework

## Objective

Act as a **Principal Solutions Architect**, **Principal Engineer**, and **Engineering Consultant**.

Help me understand what a customer's statements reveal about their engineering organisation.

I work in Technical Sales.

My goal is to become a trusted consultant who can:

- understand what the customer is actually telling me,
- understand why they made technical decisions,
- identify genuine engineering problems,
- recognise where no change is required,
- recognise where Requestly genuinely improves their workflow,
- explain those improvements in a technically accurate and credible way.

Never force a product fit.

---

# Customer Statement

<Customer Statement Here>

Examples:

- We use Playwright.
- We use Postman.
- We built an internal API framework.
- QA doesn't own API testing.
- We just use Curl.
- Everything runs in GitHub Actions.
- Authentication is difficult.
- Our API tests are flaky.
- We have hundreds of microservices.

---

# Analysis Framework

## 1. What does this statement actually tell me?
Analyse engineering maturity, ownership, workflows, tooling philosophy, safe assumptions and unsafe assumptions.

## 2. Think Like the Customer
Defend the customer's decision before suggesting change.

## 3. Current Workflow
Explain day-to-day workflow, collaboration, testing lifecycle, CI/CD, maintenance and scaling.

## 4. Why do engineering teams choose this?

## 5. Strengths

## 6. Weaknesses
Separate inherent limitations, implementation mistakes and organisational issues.

## 7. Typical Pain Points

## 8. Customer Translation
What does this statement reveal about engineering maturity, culture, priorities, buying readiness and likely objections?

## 9. Discovery Questions
Provide thoughtful, non-leading questions.

## 10. Evaluate Requestly
Only after understanding everything else.
Focus on engineering outcomes, not product features.

## 11. Positioning Strategy
Teach me to position Requestly like a consultant, not a salesperson.

## 12. Engineering Evidence
Support recommendations with technical reasoning.

## 13. Migration Analysis

## 14. Recommendation
Choose one:
- Strongly Recommend
- Recommend
- Worth Evaluating
- Neutral
- Not Recommended

## 15. Consultant Summary

## 16. Recommendation Scorecard
Rate:
- Technical Fit
- Business Fit
- Engineering ROI
- Migration Complexity
- Customer Readiness
- Confidence in Recommendation

---

# Guiding Principles

- Understanding before recommending.
- Technical accuracy over persuasion.
- Trade-offs over absolute statements.
- Engineering outcomes over product features.
- Long-term customer success over short-term sales.
# Prompt 1 — Concept Learning Framework

## Objective

Act as a **Principal Engineer**, **Solutions Architect**, **Engineering Manager**, and **technical educator** with extensive experience designing and scaling engineering organisations.

Your role is to teach me this topic so that I can confidently discuss it with experienced developers, Staff Engineers, Engineering Managers, Directors of Engineering, Architects, and CTOs.

I am **not** trying to become an implementation engineer or software developer.

I work in Technical Sales.

My goal is to become a trusted technical consultant who understands:

- how engineering teams work,
- why they make certain technical decisions,
- what problems they are solving,
- what trade-offs they have accepted,
- how different technologies fit together,
- how engineering organisations evolve,
- and where products like Requestly may (or may not) provide value.

The objective is understanding—not memorisation.

Assume I may be challenged by experienced engineers.

Every explanation should be technically accurate, balanced, practical and based on real-world engineering practices.

Avoid marketing language.

Avoid simplifying away important trade-offs.

Whenever multiple valid approaches exist, explain why different engineering organisations make different decisions.

---

# Topic

**Topic:**

<INSERT TOPIC HERE>

Examples:

- HTTP
- REST
- GraphQL
- Authentication
- API Testing
- CI/CD
- Shift Left Testing
- Platform Engineering
- Customer Workflows
- Customer Problems

---

# Response Structure

## 1. Executive Summary
Explain the topic in simple language. If I had only two minutes before a customer meeting, what should I understand?

## 2. Why does this exist?
- What problem was it created to solve?
- What existed before?
- Why wasn't the previous approach sufficient?

## 3. Core Concepts
Teach every important concept from first principles.

## 4. How does it work?
Explain the complete workflow with practical engineering examples.

## 5. Where is it used?
Explain company size, engineering maturity, industries and common use cases.

## 6. Who cares about this?
Explain why Backend Engineers, QA Engineers, Platform Engineers, Engineering Managers, Staff Engineers and Directors care.

## 7. Why do engineering teams adopt this?
Business reasons, technical reasons and expected benefits.

## 8. Benefits
Developer productivity, scalability, collaboration, maintainability, reliability and developer experience.

## 9. Drawbacks
Trade-offs, limitations, hidden costs, scaling challenges and maintenance burden.

## 10. Common Misconceptions

## 11. Alternative Approaches

## 12. Real-world Examples

## 13. Engineering Evolution
Explain how this topic evolves from Startup → Enterprise.

## 14. Consultant Lens
- Why should someone in Technical Sales care?
- What does this topic reveal about an engineering organisation?
- What mistakes do salespeople make?
- What misconceptions should I avoid?
- Under what circumstances could this become relevant to Requestly?
- If it doesn't, explicitly say so.

## 15. Key Takeaways

## 16. Further Learning
Recommend official documentation, RFCs, blogs, books, conference talks and GitHub repositories.

---

# Guiding Principles

- Technical accuracy over simplification.
- Understanding over memorisation.
- Trade-offs over absolute statements.
- Engineering reality over marketing.
- Long-term understanding over short-term knowledge.
c: <<Topic Name>>Learning Depth: Advanced
Output Format: Markdown for Obsidian
```

Follow Up:

```
Act as a Principal Engineer reviewing this chapter.
What is technically inaccurate?
What important concepts are missing?
Which explanations are oversimplified?
What would you expect an experienced Engineering Manager to know that isn't covered here?
```

Follow Up:

```
Rewrite the chapter by incorporating all of the feedback.
Keep the same structure.
Improve technical accuracy.
Add missing concepts.
Remove repetition.
Keep it suitable for my Obsidian handbook.
```

Prompt 2:

```
Customer Statement
We Use <<Topic Name>>
```

FollowUp:

```
Pretend you are a Principal Engineer using Playwright.
Which parts of the above analysis would you disagree with?
What assumptions are incorrect?
What important nuances are missing?
```

Follow Up:

```
Keep it objective.
Improve technical accuracy.
Make it suitable for my Obsidian handbook.
```


# **SEO ENGINE**

## **Agentic Architecture Pack v1.0**

**Status:** Architecture baseline  
 **Product:** SEO Engine  
 **Architecture type:** Agentic AI Growth Operating System  
 **Primary deployment model:** Multi tenant SaaS  
 **Initial implementation:** Modular monolith with strong domain boundaries  
 **Future:** Service extraction where scale requires it  
 **Primary stack:** TypeScript/Next.js \+ Python/FastAPI \+ PostgreSQL/pgvector \+ Redis \+ Temporal \+ Docker  
 **Core principle:** Evidence → Decision → Permission → Action → Measurement → Learning

---

# **1\. System definition**

SEO Engine is defined as:

> **A continuously operating, evidence based agentic system that understands a brand and its digital environment, researches search and market opportunities, diagnoses problems, develops and prioritises strategies, creates and optimises content, executes approved actions across connected platforms, measures business outcomes and learns from those outcomes.**

The canonical operating loop is:

OBSERVE  
   ↓  
UNDERSTAND  
   ↓  
RESEARCH  
   ↓  
DIAGNOSE  
   ↓  
STRATEGISE  
   ↓  
PRIORITISE  
   ↓  
CREATE  
   ↓  
OPTIMISE  
   ↓  
APPROVE  
   ↓  
EXECUTE  
   ↓  
MEASURE  
   ↓  
LEARN  
   ↓  
OBSERVE

This loop is the heart of the product.

---

# **2\. Architectural principles**

These become non negotiable engineering principles.

## **P1. Agent first**

Capabilities belong to agents, not scattered application code.

## **P2. Evidence before recommendation**

A recommendation must have supporting evidence.

## **P3. Recommendation before execution**

Agents do not directly perform consequential actions unless their policy allows it.

## **P4. Permission is capability based**

An agent can only access tools and actions explicitly granted to it.

## **P5. Human control is policy driven**

The system should not repeatedly ask for approval where the user has already established an automation policy.

## **P6. Every consequential action is auditable**

We must know:

who  
what  
when  
why  
using which evidence  
under which policy  
with which tool  
and what happened afterwards

## **P7. Existing assets before new assets**

Before recommending a new page, the system must evaluate existing pages.

## **P8. Content must have a reason to exist**

A keyword alone does not justify content creation.

This directly follows the supplied Google guidance against producing large numbers of pages simply to capture query variations.

## **P9. No invented expertise**

The system cannot fabricate:

* experience  
* statistics  
* testimonials  
* credentials  
* research  
* citations  
* case studies  
* product claims

## **P10. SEO is subordinate to user value**

Google's supplied guidance repeatedly emphasises people first content and warns against search engine first content.

## **P11. No ranking guarantees**

SEO Engine reports probabilities, evidence and opportunities, not guaranteed rankings.

## **P12. Third party SEO data is evidence, not truth**

Ahrefs and Semrush data are useful but must never be treated as Google's internal data. Google's documentation explicitly cautions against third party tools claiming access to internal ranking or AI signals.

## **P13. AI Search is not a separate hack layer**

AI Search visibility is evaluated primarily through the same strong technical and content foundations used for Search.

## **P14. Agentic web readiness is a separate capability**

Google's supplied material specifically discusses browser agents interacting with websites through visual rendering, DOM structures and accessibility trees.

Therefore SEO Engine will eventually audit **machine interaction readiness**, not merely search visibility.

---

# **3\. High level architecture**

┌─────────────────────────────────────────────────────────────────────┐  
│                         SEO ENGINE                                  │  
├─────────────────────────────────────────────────────────────────────┤  
│                           EXPERIENCE                                │  
│  Web App │ Command Centre │ Reports │ Content Studio │ Approvals    │  
├─────────────────────────────────────────────────────────────────────┤  
│                              API                                    │  
│                     API Gateway / BFF                               │  
├─────────────────────────────────────────────────────────────────────┤  
│                       AGENT CONTROL PLANE                            │  
│                                                                     │  
│ Orchestrator │ Agent Registry │ Task Manager │ Workflow Engine     │  
│ Policy Engine │ Permission Engine │ Approval Engine │ Event Bus     │  
├─────────────────────────────────────────────────────────────────────┤  
│                       AGENT INTELLIGENCE                            │  
│                                                                     │  
│ Research │ Search │ SEO │ Content │ Competitive │ Growth │ Local   │  
│ Analytics │ Decision │ Execution │ Guardians │ Learning             │  
├─────────────────────────────────────────────────────────────────────┤  
│                          MEMORY                                     │  
│                                                                     │  
│ Brand Memory │ Working Memory │ Historical Memory │ Outcome Memory │  
│ Knowledge Graph │ Documents │ Embeddings │ Evidence Store          │  
├─────────────────────────────────────────────────────────────────────┤  
│                            TOOLS                                    │  
│                                                                     │  
│ Browser │ Crawler │ Search │ GSC │ GA4 │ Ahrefs │ Semrush          │  
│ Google Ads │ GBP │ CMS │ Trends │ LLM Providers │ Image/Video      │  
├─────────────────────────────────────────────────────────────────────┤  
│                         DATA PLANE                                  │  
│                                                                     │  
│ PostgreSQL │ pgvector │ Redis │ Object Storage │ Analytics Store   │  
└─────────────────────────────────────────────────────────────────────┘  
---

# **4\. Agent registry**

Every agent gets:

Agent ID  
Name  
Version  
Purpose  
Capabilities  
Inputs  
Outputs  
Tools  
Memory access  
Permissions  
Approval requirements  
Risk level  
Model policy  
Fallback policy  
---

# **5\. Core control agents**

| ID | Agent | Primary responsibility |
| ----- | ----- | ----- |
| `ORCH-001` | SEO Orchestrator | Decompose objectives and coordinate agents |
| `TASK-001` | Task Manager | Manage tasks and dependencies |
| `WORK-001` | Workflow Agent | Execute durable multi step workflows |
| `DEC-001` | Decision Agent | Challenge and approve recommendations |
| `OPP-001` | Opportunity Agent | Discover growth opportunities |
| `PRI-001` | Prioritisation Agent | Rank opportunities |
| `MEM-001` | Memory Agent | Manage long term agent memory |
| `POL-001` | Policy Guardian | Enforce system/client policies |
| `SEC-001` | Security Guardian | Protect credentials and actions |
| `QUAL-001` | Quality Guardian | Validate quality |
| `FIN-001` | Financial Guardian | Control paid spend |
| `PUB-001` | Publishing Guardian | Control publication |

---

# **6\. Brand intelligence agents**

| ID | Agent | Responsibility |
| ----- | ----- | ----- |
| `BRD-001` | Brand Intelligence | Build brand model |
| `BRD-002` | Audience Intelligence | Understand audiences |
| `BRD-003` | Product Intelligence | Understand products/services |
| `BRD-004` | Entity Intelligence | Identify entities and relationships |
| `BRD-005` | Brand Voice | Learn approved brand voice |
| `BRD-006` | Business Model | Understand revenue model |
| `BRD-007` | Brand Risk | Identify claims/reputational risks |

---

# **7\. Research agents**

| ID | Agent | Responsibility |
| ----- | ----- | ----- |
| `RES-001` | Market Research | Market/industry research |
| `RES-002` | Search Research | Search landscape |
| `RES-003` | Source Research | Authoritative sources |
| `RES-004` | Trend Research | Trends and emerging demand |
| `RES-005` | Competitor Research | Competitor discovery |
| `RES-006` | SERP Research | Search result analysis |
| `RES-007` | Question Research | Questions and information needs |

---

# **8\. SEO agents**

| ID | Agent | Responsibility |
| ----- | ----- | ----- |
| `SEO-001` | Technical SEO | Technical diagnosis |
| `SEO-002` | On Page SEO | Page optimisation |
| `SEO-003` | Keyword Intelligence | Keyword discovery |
| `SEO-004` | Search Intent | Intent classification |
| `SEO-005` | Topic Cluster | Topical architecture |
| `SEO-006` | Internal Linking | Internal link strategy |
| `SEO-007` | Schema | Structured data |
| `SEO-008` | Image SEO | Image optimisation |
| `SEO-009` | Video SEO | Video optimisation |
| `SEO-010` | International SEO | Internationalisation |
| `SEO-011` | Migration SEO | Site migrations |
| `SEO-012` | Indexation | Indexation diagnostics |

---

# **9\. AI Search and agent experience agents**

| ID | Agent | Responsibility |
| ----- | ----- | ----- |
| `AIS-001` | AI Search Visibility | Monitor AI search visibility |
| `AIS-002` | AI Citation Intelligence | Analyse citations/mentions |
| `AIS-003` | Query Fan Out Research | Analyse related search journeys |
| `AIS-004` | Agent Experience | Audit browser/AI-agent usability |
| `AIS-005` | Machine Discoverability | Audit machine readable information |

Important distinction:

`AIS-001` does **not** invent an “AI ranking score”.

It measures observable outcomes and underlying SEO conditions.

Google's guidance explicitly says there are no special AI Search optimisation requirements beyond foundational SEO.

---

# **10\. Content agents**

| ID | Agent | Responsibility |
| ----- | ----- | ----- |
| `CNT-001` | Content Strategist | Content strategy |
| `CNT-002` | Content Gap | Content gaps |
| `CNT-003` | Content Research | Research pack |
| `CNT-004` | Content Brief | Definitive brief |
| `CNT-005` | Content Writer | Draft content |
| `CNT-006` | Content Updater | Update existing content |
| `CNT-007` | Content Repurposer | Platform repurposing |
| `CNT-008` | Editor | Editorial review |
| `CNT-009` | Fact Checker | Factual verification |
| `CNT-010` | E-E-A-T Reviewer | Experience/expertise/trust review |
| `CNT-011` | Originality Reviewer | Value/originality |
| `CNT-012` | Content Risk | Spam/scaled content risk |
| `CNT-013` | Content Consolidator | Merge/canonicalisation recommendations |

The content pipeline therefore becomes:

Opportunity  
     ↓  
Content Gap  
     ↓  
Research  
     ↓  
Brief  
     ↓  
Draft  
     ↓  
Edit  
     ↓  
Fact Check  
     ↓  
E-E-A-T  
     ↓  
Originality  
     ↓  
Risk  
     ↓  
Publishing Guardian  
     ↓  
Approval  
     ↓  
Publish

This directly operationalises the Google guidance around original information, substantial value, expertise, factual accuracy and people first content.

---

# **11\. Competitive intelligence agents**

| ID | Agent | Responsibility |
| ----- | ----- | ----- |
| `CMP-001` | Competitor Intelligence | Competitor profiles |
| `CMP-002` | Keyword Gap | Competitor keyword gaps |
| `CMP-003` | Content Gap | Competitor content gaps |
| `CMP-004` | SERP Competitor | SERP competitors |
| `CMP-005` | Backlink Intelligence | Link landscape |
| `CMP-006` | Paid Competitor | Paid search |
| `CMP-007` | Local Competitor | Local competition |
| `CMP-008` | Competitor Movement | Detect changes |

---

# **12\. Analytics agents**

| ID | Agent | Responsibility |
| ----- | ----- | ----- |
| `ANA-001` | GSC Analyst | Search Console |
| `ANA-002` | GA4 Analyst | Analytics |
| `ANA-003` | SEO Performance | Cross source performance |
| `ANA-004` | Conversion Analyst | Conversion outcomes |
| `ANA-005` | Anomaly Detector | Detect abnormalities |
| `ANA-006` | Attribution Analyst | Channel contribution |
| `ANA-007` | Forecast Agent | Forecast scenarios |

---

# **13\. Growth agents**

| ID | Agent | Responsibility |
| ----- | ----- | ----- |
| `GRW-001` | Growth Strategist | Growth strategy |
| `GRW-002` | CRO Agent | Conversion optimisation |
| `GRW-003` | Landing Page Agent | Landing page strategy |
| `GRW-004` | Paid Search Strategist | Paid search |
| `GRW-005` | Campaign Planner | Campaign architecture |
| `GRW-006` | Budget Agent | Budget allocation |

---

# **14\. Local SEO agents**

| ID | Agent | Responsibility |
| ----- | ----- | ----- |
| `LOC-001` | Local SEO Strategist | Local strategy |
| `LOC-002` | GBP Analyst | Google Business Profile |
| `LOC-003` | Location Page Agent | Location pages |
| `LOC-004` | Review Intelligence | Review analysis |
| `LOC-005` | Local Citation Agent | Citation consistency |
| `LOC-006` | Local Competitor | Local competitor analysis |

---

# **15\. Execution agents**

| ID | Agent | Permission |
| ----- | ----- | ----- |
| `EXE-001` | CMS Executor | CMS changes |
| `EXE-002` | Technical Executor | Technical SEO |
| `EXE-003` | GSC Executor | GSC operations |
| `EXE-004` | GA Executor | Analytics configuration |
| `EXE-005` | GBP Executor | GBP |
| `EXE-006` | Ads Executor | Paid campaigns |
| `EXE-007` | Content Publisher | Content publication |
| `EXE-008` | Link Executor | Approved internal links |

Execution agents **do not decide strategy**.

They execute approved actions.

---

# **16\. Agent capability model**

Capabilities should be atomic.

Example:

website.read  
website.crawl  
website.render

seo.audit  
seo.keyword.research  
seo.serp.analyse  
seo.schema.validate

content.research  
content.write  
content.edit  
content.publish

analytics.gsc.read  
analytics.ga4.read

ads.read  
ads.propose  
ads.write  
ads.budget.change

cms.read  
cms.draft  
cms.publish

gbp.read  
gbp.write

An agent receives capabilities, not arbitrary tool access.

---

# **17\. Permission model**

Four levels:

READ  
PROPOSE  
EXECUTE  
AUTONOMOUS

Example:

### **Content Writer**

content.research       READ  
brand.memory           READ  
content.draft          EXECUTE  
content.publish        DENY  
cms.write              DENY

### **Content Publisher**

content.approved       READ  
cms.publish            EXECUTE

### **Ads Executor**

ads.read               READ  
ads.create             PROPOSE  
ads.modify             EXECUTE  
ads.budget             POLICY CONTROLLED  
---

# **18\. Risk classification**

Every action gets:

LOW  
MEDIUM  
HIGH  
CRITICAL

### **Low**

* draft content  
* generate recommendations  
* detect broken links

### **Medium**

* metadata update  
* internal links  
* schema updates

### **High**

* redirects  
* deleting pages  
* publishing medical/legal/financial content  
* changing campaigns

### **Critical**

* large advertising budget changes  
* deleting large numbers of URLs  
* site migrations  
* changing access/security settings

---

# **19\. Approval matrix**

                    LOW   MEDIUM   HIGH   CRITICAL  
\----------------------------------------------------  
Research              Auto    Auto    Auto      Auto  
Recommendation        Auto    Auto    Auto      Auto  
Draft                  Auto    Auto    Auto      Auto  
Metadata               Auto   Policy  Approval  Approval  
Content Publish        Policy Approval Approval Approval  
Redirects              No    Approval Approval Approval  
Delete Content         No    No       Approval Approval  
Ads Creation           No    Approval Approval Approval  
Budget Changes         No    No       Approval Approval

The customer's subscription/policy can modify this.

---

# **20\. Memory architecture**

This is one of the most important components.

We use **hybrid memory**.

                 MEMORY SYSTEM  
                       │  
       ┌───────────────┼────────────────┐  
       │               │                │  
 Structured         Semantic         Graph  
 Memory             Memory           Memory  
       │               │                │  
 PostgreSQL        pgvector         Knowledge Graph  
---

# **21\. Brand Memory**

Stores stable facts:

Company  
Products  
Services  
Locations  
Audiences  
Personas  
Brand voice  
Claims  
Credentials  
Experts  
Policies  
Competitors  
Business goals  
Revenue goals  
Approved terminology  
Forbidden terminology  
---

# **22\. Working Memory**

Short lived task information.

Example:

Task:  
Increase organic leads

Current findings:  
12 opportunities

Selected:  
5 opportunities

Research:  
SERP data  
GSC data  
Competitor data

TTL controlled.

---

# **23\. Historical Memory**

Stores:

* previous audits  
* recommendations  
* decisions  
* published content  
* technical changes  
* campaigns  
* experiments

---

# **24\. Outcome Memory**

Stores:

Action  
→ Result  
→ Time period  
→ Confidence  
→ Context

Example:

Change:  
Title revised

Result:  
CTR \+18%

Observation window:  
28 days

Confidence:  
0.82

The system can then learn patterns.

---

# **25\. Knowledge graph**

Core entities:

Brand  
Person  
Product  
Service  
Topic  
Keyword  
Query  
Page  
Competitor  
Location  
Organisation  
Claim  
Source  
Author  
Campaign  
Conversion  
Experiment  
Action  
Outcome

Relationships:

Brand ─offers→ Service  
Service ─targets→ Audience  
Service ─related\_to→ Topic  
Topic ─targets→ Keyword  
Keyword ─appears\_in→ Page  
Page ─competes\_with→ Page  
Page ─supports→ Service  
Person ─expert\_in→ Topic  
Source ─supports→ Claim  
Action ─produced→ Outcome

This becomes SEO Engine's **semantic brain**.

---

# **26\. Evidence architecture**

Every important recommendation needs evidence.

{  
  "evidence\_id": "ev\_123",  
  "type": "gsc\_observation",  
  "source": "google\_search\_console",  
  "source\_ref": "query:.../page:...",  
  "observed\_at": "2026-08-12T09:00:00Z",  
  "data": {},  
  "confidence": 0.96  
}

Evidence types:

OBSERVATION  
DOCUMENT  
SOURCE  
API\_DATA  
CRAWL\_RESULT  
SERP\_RESULT  
EXPERIMENT  
HUMAN\_INPUT  
MODEL\_INFERENCE

This allows the system to distinguish fact from inference.

---

# **27\. Task schema**

Canonical task:

{  
  "id": "task\_01",  
  "tenant\_id": "tenant\_01",  
  "workflow\_id": "wf\_01",  
  "parent\_task\_id": null,  
  "agent\_id": "SEO-003",  
  "objective": "Identify high-value non-branded keyword opportunities",  
  "priority": "high",  
  "status": "queued",  
  "inputs": {},  
  "constraints": {},  
  "required\_capabilities": \[  
    "seo.keyword.research"  
  \],  
  "allowed\_tools": \[  
    "semrush",  
    "ahrefs",  
    "gsc"  
  \],  
  "approval\_policy": "none",  
  "deadline": null,  
  "created\_at": "...",  
  "started\_at": null,  
  "completed\_at": null  
}  
---

# **28\. Task states**

DRAFT  
 ↓  
QUEUED  
 ↓  
RUNNING  
 ↓  
WAITING  
 ↓  
BLOCKED  
 ↓  
COMPLETED

Alternative exits:

FAILED  
CANCELLED  
EXPIRED  
REQUIRES\_APPROVAL  
---

# **29\. Agent result schema**

{  
  "task\_id": "task\_01",  
  "status": "completed",  
  "summary": "...",  
  "findings": \[\],  
  "evidence": \[\],  
  "recommendations": \[\],  
  "actions": \[\],  
  "confidence": 0.89,  
  "limitations": \[\],  
  "next\_tasks": \[\]  
}  
---

# **30\. Recommendation schema**

{  
  "id": "rec\_001",  
  "type": "content\_update",  
  "title": "Update existing pricing guide",  
  "reason": "...",  
  "business\_impact": 8,  
  "seo\_impact": 9,  
  "confidence": 0.87,  
  "effort": 4,  
  "risk": "low",  
  "evidence\_ids": \[  
    "ev\_001",  
    "ev\_002"  
  \],  
  "dependencies": \[\],  
  "proposed\_action": {}  
}  
---

# **31\. Action schema**

{  
  "id": "act\_001",  
  "recommendation\_id": "rec\_001",  
  "action\_type": "cms.update",  
  "target": {  
    "url": "https://example.com/page"  
  },  
  "payload": {},  
  "risk": "medium",  
  "approval\_required": true,  
  "status": "pending"  
}  
---

# **32\. Event model**

SEO Engine should be event driven internally.

Core events:

BrandCreated  
BrandUpdated

WebsiteConnected  
WebsiteCrawled  
CrawlCompleted

KeywordResearchStarted  
KeywordResearchCompleted

CompetitorDiscovered  
CompetitorUpdated

AuditStarted  
AuditCompleted

OpportunityDiscovered  
OpportunityPrioritised

RecommendationCreated  
RecommendationApproved  
RecommendationRejected

ContentBriefCreated  
ContentDraftCreated  
ContentReviewed  
ContentApproved  
ContentPublished

TechnicalIssueDetected  
TechnicalIssueResolved

AnalyticsSynced  
PerformanceChanged  
AnomalyDetected

CampaignProposed  
CampaignApproved  
CampaignLaunched

ExperimentStarted  
ExperimentCompleted

OutcomeRecorded  
LearningCreated  
---

# **33\. Event envelope**

{  
  "event\_id": "evt\_001",  
  "event\_type": "OpportunityDiscovered",  
  "tenant\_id": "tenant\_001",  
  "aggregate\_type": "opportunity",  
  "aggregate\_id": "opp\_001",  
  "actor\_type": "agent",  
  "actor\_id": "OPP-001",  
  "timestamp": "2026-08-12T10:00:00Z",  
  "correlation\_id": "corr\_001",  
  "causation\_id": "evt\_000",  
  "payload": {},  
  "schema\_version": 1  
}

This gives us traceability across agent chains.

---

# **34\. Workflow architecture**

Use **Temporal** for durable workflows.

Why?

Agentic SEO operations can last:

* seconds  
* minutes  
* hours  
* days  
* weeks

A workflow cannot depend on one HTTP request remaining alive.

Temporal gives us:

* durable execution  
* retries  
* timers  
* signals  
* child workflows  
* human approval pauses  
* failure recovery

---

# **35\. Workflow: SEO Audit**

START  
 ↓  
Load Brand  
 ↓  
Connect Website  
 ↓  
Crawl  
 ↓  
Technical Analysis  
 ↓  
Indexation Analysis  
 ↓  
On Page Analysis  
 ↓  
Content Analysis  
 ↓  
Competitor Analysis  
 ↓  
Search Analysis  
 ↓  
Aggregate Findings  
 ↓  
Opportunity Detection  
 ↓  
Prioritisation  
 ↓  
Decision Review  
 ↓  
Generate Roadmap  
 ↓  
END  
---

# **36\. Workflow: Content Creation**

START  
 ↓  
Validate Opportunity  
 ↓  
Check Existing Assets  
 ↓  
Determine Create vs Update vs Consolidate  
 ↓  
Research  
 ↓  
Source Verification  
 ↓  
Brief  
 ↓  
Draft  
 ↓  
Editorial Review  
 ↓  
Fact Check  
 ↓  
Originality  
 ↓  
E-E-A-T  
 ↓  
Risk Review  
 ↓  
Publishing Guardian  
 ↓  
Human Approval  
 ↓  
Publish  
 ↓  
Measure  
 ↓  
LEARN  
---

# **37\. Workflow: Autonomous SEO Monitoring**

Persistent workflow:

EVERY X HOURS  
      ↓  
Collect observations  
      ↓  
Detect anomalies  
      ↓  
Evaluate policies  
      ↓  
Create opportunities  
      ↓  
Prioritise  
      ↓  
Auto execute permitted actions  
      ↓  
Request approval for restricted actions  
      ↓  
Record outcomes  
      ↓  
Schedule next cycle  
---

# **38\. Workflow: Paid Ads**

Business objective  
       ↓  
Audience research  
       ↓  
Keyword research  
       ↓  
Competitor research  
       ↓  
Landing page analysis  
       ↓  
Campaign proposal  
       ↓  
Financial Guardian  
       ↓  
Human approval  
       ↓  
Campaign creation  
       ↓  
Monitor  
       ↓  
Optimise  
       ↓  
Budget review  
       ↓  
Outcome

No autonomous spending outside policy.

---

# **39\. Database architecture**

PostgreSQL is the system of record.

Major schemas:

identity  
tenancy  
brands  
websites  
agents  
tasks  
workflows  
tools  
permissions  
policies  
memory  
knowledge  
research  
seo  
content  
competitors  
analytics  
campaigns  
local  
experiments  
actions  
events  
audit  
billing  
---

# **40\. Core tables**

### **`tenants`**

id  
name  
slug  
status  
created\_at  
updated\_at

### **`users`**

id  
tenant\_id  
email  
name  
role  
status  
created\_at

### **`brands`**

id  
tenant\_id  
name  
description  
industry  
website  
country  
primary\_language  
business\_model  
brand\_voice\_id  
created\_at  
updated\_at

### **`brand_goals`**

id  
brand\_id  
goal\_type  
description  
target  
unit  
timeframe  
priority  
status  
---

# **41\. Websites**

### **`websites`**

id  
brand\_id  
domain  
protocol  
cms  
status  
crawl\_frequency  
robots\_url  
sitemap\_url  
created\_at

### **`pages`**

id  
website\_id  
url  
canonical\_url  
status\_code  
indexability  
title  
h1  
word\_count  
content\_hash  
last\_crawled\_at  
---

# **42\. Agent tables**

### **`agents`**

id  
name  
version  
type  
description  
model\_policy  
risk\_level  
status

### **`agent_capabilities`**

id  
agent\_id  
capability  
permission

### **`agent_tools`**

agent\_id  
tool\_id  
permission  
---

# **43\. Tasks**

### **`tasks`**

id  
tenant\_id  
workflow\_id  
parent\_task\_id  
agent\_id  
objective  
status  
priority  
risk  
input\_json  
output\_json  
created\_at  
started\_at  
completed\_at

### **`task_dependencies`**

task\_id  
depends\_on\_task\_id  
condition  
---

# **44\. Memory**

### **`memories`**

id  
tenant\_id  
brand\_id  
memory\_type  
key  
content  
source  
confidence  
importance  
expires\_at  
created\_at

### **`embeddings`**

id  
memory\_id  
embedding vector  
model  
created\_at  
---

# **45\. Evidence**

### **`evidence`**

id  
tenant\_id  
type  
source  
source\_ref  
content  
structured\_data  
observed\_at  
confidence  
created\_at

### **`evidence_relationships`**

evidence\_id  
entity\_type  
entity\_id  
relationship  
---

# **46\. Keywords**

### **`keywords`**

id  
brand\_id  
keyword  
language  
country  
intent  
volume  
difficulty  
cpc  
trend  
source  
last\_updated

### **`keyword_rankings`**

id  
keyword\_id  
url  
position  
device  
country  
search\_engine  
observed\_at  
---

# **47\. Content**

### **`content_assets`**

id  
brand\_id  
type  
title  
url  
status  
author\_id  
canonical\_url  
content\_hash  
published\_at  
updated\_at

### **`content_versions`**

id  
content\_asset\_id  
version  
body  
created\_by  
created\_at

### **`content_evaluations`**

id  
content\_asset\_id  
evaluation\_type  
score  
findings  
created\_at  
---

# **48\. Competitors**

### **`competitors`**

id  
brand\_id  
name  
domain  
type  
priority  
status

### **`competitor_observations`**

id  
competitor\_id  
observation\_type  
data  
observed\_at  
---

# **49\. Opportunities**

### **`opportunities`**

id  
brand\_id  
type  
title  
description  
business\_impact  
seo\_impact  
confidence  
effort  
risk  
priority\_score  
status  
created\_at  
---

# **50\. Recommendations**

### **`recommendations`**

id  
opportunity\_id  
agent\_id  
recommendation\_type  
title  
reason  
evidence  
confidence  
status  
created\_at  
---

# **51\. Actions**

### **`actions`**

id  
recommendation\_id  
executor\_agent\_id  
action\_type  
target  
payload  
risk  
approval\_required  
approved\_by  
status  
executed\_at  
result  
---

# **52\. Outcomes**

### **`outcomes`**

id  
action\_id  
metric  
baseline  
result  
delta  
measurement\_window  
confidence  
observed\_at

This table is fundamental to learning.

---

# **53\. Experiments**

### **`experiments`**

id  
brand\_id  
hypothesis  
control  
variant  
metric  
start\_date  
end\_date  
status  
result  
confidence

SEO Engine should eventually become an optimisation engine rather than merely a recommendation engine.

---

# **54\. Policies**

### **`policies`**

id  
tenant\_id  
name  
scope  
rules  
risk\_threshold  
approval\_mode  
created\_at

Example:

{  
  "scope": "google\_ads",  
  "rules": {  
    "max\_daily\_budget": 100000,  
    "max\_budget\_change\_percent": 20,  
    "require\_approval\_above": 50000  
  }  
}  
---

# **55\. API architecture**

REST externally.

Events internally.

Base:

/api/v1  
---

# **56\. Brand API**

POST /brands  
GET /brands  
GET /brands/{id}  
PATCH /brands/{id}  
DELETE /brands/{id}  
---

# **57\. Website API**

POST /brands/{id}/websites  
GET /websites/{id}  
POST /websites/{id}/crawl  
GET /websites/{id}/pages  
GET /websites/{id}/technical-audit  
---

# **58\. Agent API**

GET /agents  
GET /agents/{id}  
GET /agents/{id}/capabilities  
POST /agents/{id}/tasks  
---

# **59\. Task API**

POST /tasks  
GET /tasks  
GET /tasks/{id}  
POST /tasks/{id}/cancel  
POST /tasks/{id}/retry  
---

# **60\. Workflow API**

POST /workflows  
GET /workflows  
GET /workflows/{id}  
POST /workflows/{id}/signal  
POST /workflows/{id}/cancel  
---

# **61\. Research API**

POST /research/keywords  
POST /research/competitors  
POST /research/serp  
POST /research/content-gaps  
POST /research/market  
---

# **62\. Content API**

POST /content/research  
POST /content/briefs  
POST /content/drafts  
POST /content/{id}/review  
POST /content/{id}/fact-check  
POST /content/{id}/approve  
POST /content/{id}/publish  
POST /content/{id}/repurpose  
---

# **63\. Recommendations API**

GET /opportunities  
GET /opportunities/{id}

GET /recommendations  
GET /recommendations/{id}

POST /recommendations/{id}/approve  
POST /recommendations/{id}/reject  
---

# **64\. Execution API**

POST /actions/{id}/approve  
POST /actions/{id}/execute  
POST /actions/{id}/cancel  
GET /actions/{id}  
---

# **65\. Analytics API**

POST /integrations/gsc/sync  
POST /integrations/ga4/sync  
GET /analytics/search  
GET /analytics/traffic  
GET /analytics/conversions  
GET /analytics/anomalies  
---

# **66\. Integration architecture**

Every external platform gets an adapter.

Integration Interface  
       │  
 ┌─────┼────────┬────────┬────────┐  
 │     │        │        │        │  
 GSC  GA4    Ahrefs   Semrush   Ads

Common interface:

interface Integration {  
  connect(): Promise\<void\>  
  disconnect(): Promise\<void\>  
  healthCheck(): Promise\<HealthStatus\>  
  getCapabilities(): Promise\<Capability\[\]\>  
}

Then:

interface SearchConsoleIntegration extends Integration {  
  queryPerformance(): Promise\<SearchPerformance\>  
  inspectUrl(): Promise\<UrlInspection\>  
}  
---

# **67\. Credentials architecture**

Never store raw API secrets in normal database fields.

Use:

OAuth  
\+  
KMS/encrypted secrets  
\+  
credential vault

Store only references.

integration\_credentials  
\-----------------------  
id  
tenant\_id  
provider  
credential\_ref  
scopes  
expires\_at  
status  
---

# **68\. Tool registry**

Tools become first class objects.

Browser  
Crawler  
Search  
GSC  
GA4  
Ahrefs  
Semrush  
Google Ads  
GBP  
CMS  
Trends  
LLM  
Image  
Video

Each has:

tool\_id  
provider  
version  
capabilities  
rate\_limits  
cost  
authentication  
risk  
---

# **69\. LLM abstraction**

Do not hardcode one model.

Model Gateway  
     │  
 ┌───┼────┬────┬─────┐  
 │   │    │    │     │  
Model A Model B Model C Local

Each task can specify:

reasoning requirement  
latency requirement  
cost ceiling  
context requirement  
privacy requirement

The model router chooses appropriately.

---

# **70\. Prompt architecture**

Prompts should not live inside application logic.

/prompts  
    /system  
    /agents  
    /tasks  
    /evaluators  
    /policies

Version every prompt.

content-writer.v4  
keyword-agent.v3  
fact-checker.v2  
---

# **71\. Agent execution contract**

Every agent must implement:

interface Agent {  
  id: string  
  version: string

  capabilities(): Capability\[\]

  validate(input: AgentInput): ValidationResult

  execute(  
    context: AgentContext  
  ): Promise\<AgentResult\>  
}  
---

# **72\. Agent context**

interface AgentContext {  
  tenantId: string  
  brandId: string  
  taskId: string

  objective: string

  memory: MemoryContext

  evidence: Evidence\[\]

  tools: ToolContext\[\]

  permissions: PermissionContext

  policy: PolicyContext

  constraints: Constraint\[\]

  budget?: BudgetContext  
}

This ensures an agent never operates without context.

---

# **73\. Agent observability**

Every execution logs:

agent  
task  
model  
prompt version  
tools  
input tokens  
output tokens  
latency  
cost  
evidence  
decision  
errors

This gives us:

### **Agent cost analytics**

Which agents cost too much?

### **Agent quality analytics**

Which agents produce poor recommendations?

### **Agent reliability**

Which tools fail?

### **Model analytics**

Which model performs best for which task?

---

# **74\. Agent evaluation framework**

We need automated evaluation.

Every agent gets:

accuracy  
completeness  
evidence quality  
policy compliance  
tool correctness  
cost efficiency  
latency

For content:

factuality  
originality  
helpfulness  
brand alignment  
search intent  
readability  
E-E-A-T  
risk  
---

# **75\. Repository structure**

I recommend a monorepo.

seo-engine/  
│  
├── apps/  
│   ├── web/  
│   ├── api/  
│   └── worker/  
│  
├── packages/  
│   ├── agent-runtime/  
│   ├── agent-registry/  
│   ├── orchestration/  
│   ├── workflows/  
│   ├── policies/  
│   ├── permissions/  
│   ├── memory/  
│   ├── knowledge/  
│   ├── evidence/  
│   ├── events/  
│   ├── integrations/  
│   ├── prompts/  
│   ├── schemas/  
│   ├── observability/  
│   └── shared/  
│  
├── agents/  
│   ├── orchestrator/  
│   ├── brand/  
│   ├── research/  
│   ├── seo/  
│   ├── content/  
│   ├── competitor/  
│   ├── analytics/  
│   ├── growth/  
│   ├── local/  
│   ├── ai-search/  
│   ├── execution/  
│   └── guardians/  
│  
├── integrations/  
│   ├── google-search-console/  
│   ├── google-analytics/  
│   ├── google-ads/  
│   ├── google-business-profile/  
│   ├── ahrefs/  
│   ├── semrush/  
│   ├── wordpress/  
│   ├── webflow/  
│   └── generic-cms/  
│  
├── database/  
│   ├── migrations/  
│   ├── seeds/  
│   └── schemas/  
│  
├── workflows/  
│   ├── seo-audit/  
│   ├── content-production/  
│   ├── competitor-analysis/  
│   ├── keyword-research/  
│   ├── technical-monitoring/  
│   ├── local-seo/  
│   └── paid-search/  
│  
├── tests/  
│   ├── unit/  
│   ├── integration/  
│   ├── agent/  
│   ├── workflow/  
│   ├── evaluation/  
│   └── security/  
│  
├── docs/  
│   ├── architecture/  
│   ├── agents/  
│   ├── integrations/  
│   ├── api/  
│   └── operations/  
│  
├── infra/  
│   ├── docker/  
│   ├── terraform/  
│   └── deployment/  
│  
├── .env.example  
├── docker-compose.yml  
├── package.json  
├── pnpm-workspace.yaml  
└── README.md  
---

# **76\. Recommended technology stack**

## **Frontend**

Next.js  
TypeScript  
Tailwind  
shadcn/ui  
React Query

## **API**

FastAPI  
Python  
Pydantic  
SQLAlchemy

## **Database**

PostgreSQL  
pgvector

## **Cache**

Redis

## **Durable orchestration**

Temporal

## **Background execution**

Temporal Workers

## **Object storage**

S3 compatible storage

## **Search**

Initially:

PostgreSQL \+ pgvector

Later, if required:

OpenSearch

## **Infrastructure**

Docker  
Terraform  
CI/CD  
---

# **77\. Why modular monolith first**

I strongly recommend **not starting with microservices**.

We need:

strong boundaries  
not  
distributed complexity

Initially:

One application  
One PostgreSQL  
One Redis  
One Temporal cluster  
Multiple logical modules

As traffic grows:

Content Worker  
Crawler Worker  
Analytics Worker  
Agent Worker  
Execution Worker

can be extracted.

This allows us to build much faster without compromising the eventual architecture.

---

# **78\. Security architecture**

The platform will eventually contain extremely sensitive credentials.

Therefore:

Tenant isolation  
        ↓  
RBAC  
        ↓  
Capability permissions  
        ↓  
Encrypted credentials  
        ↓  
Tool scopes  
        ↓  
Action policies  
        ↓  
Audit log

Every query must be tenant scoped.

Every agent context must contain:

tenant\_id

and the database layer must enforce tenant isolation.

---

# **79\. Multi tenancy**

Design for it from Day 1\.

Every major table:

tenant\_id

The hierarchy:

Platform  
   ↓  
Tenant  
   ↓  
Users  
   ↓  
Brands  
   ↓  
Websites  
   ↓  
Projects  
   ↓  
Agents  
   ↓  
Tasks

One customer can eventually operate multiple brands.

---

# **80\. Projects**

Add:

### **`projects`**

id  
brand\_id  
name  
objective  
start\_date  
end\_date  
status

Examples:

"Organic Traffic Growth"  
"Launch Nigeria Service Page"  
"Technical SEO Recovery"  
"Competitor Takeover"  
"Local SEO Lagos"

Projects give agents strategic context.

---

# **81\. Missions**

This is a crucial addition for agentic behaviour.

A **Task** is temporary.

A **Mission** is persistent.

Example:

> Grow organic leads by 30% in six months.

Schema:

missions  
\--------  
id  
brand\_id  
objective  
target\_metric  
target\_value  
deadline  
strategy  
policy  
status

The orchestrator continually evaluates the mission.

---

# **82\. Mission lifecycle**

CREATED  
   ↓  
PLANNING  
   ↓  
ACTIVE  
   ↓  
MONITORING  
   ↓  
ADAPTING  
   ↓  
ACHIEVED

Or:

PAUSED  
FAILED  
CANCELLED  
EXPIRED

This is how we move from an AI assistant to an actual **agentic operating system**.

---

# **83\. Example persistent mission**

{  
  "objective": "Increase qualified organic leads",  
  "target": {  
    "metric": "organic\_conversions",  
    "baseline": 100,  
    "target": 130  
  },  
  "deadline": "2027-02-01",  
  "automation\_policy": "assisted",  
  "budget": {  
    "monthly\_ads": 1000000  
  }  
}

The system continuously works against that objective.

---

# **84\. Learning loop**

The architecture needs:

Recommendation  
      ↓  
Action  
      ↓  
Outcome  
      ↓  
Evaluation  
      ↓  
Learning

A learning record:

{  
  "context": "healthcare SEO",  
  "action": "update service page",  
  "result": "organic conversions \+23%",  
  "confidence": 0.81,  
  "conditions": \[  
    "existing authority",  
    "commercial intent",  
    "strong internal links"  
  \]  
}

This becomes reusable intelligence.

---

# **85\. What the system must never learn**

Do not allow the learning engine to infer:

> “Changing titles always improves rankings.”

Instead:

> “Under conditions X, Y and Z, title optimisation correlated with improved CTR.”

This distinction prevents bad automated generalisations.

---

# **86\. The SEO Engine decision stack**

Every major recommendation should pass through:

FACT  
 ↓  
EVIDENCE  
 ↓  
INTERPRETATION  
 ↓  
OPPORTUNITY  
 ↓  
STRATEGIC OPTION  
 ↓  
IMPACT / EFFORT  
 ↓  
RISK  
 ↓  
DECISION  
 ↓  
ACTION

This should be visible in the UI.

The user should be able to click:

> **Why did SEO Engine recommend this?**

and see the evidence chain.

That will become a major product differentiator.

---

# **87\. Example recommendation**

Instead of:

> “Create an article targeting DNA test price Nigeria.”

SEO Engine should say:

> **Recommendation:** Update the existing pricing guide rather than create a new article.

### **Evidence**

* Existing URL receives X impressions.  
* It ranks for Y relevant queries.  
* Competitors have newer pricing information.  
* Search intent is already aligned.  
* The current page contains outdated information.

### **Expected impact**

Traffic: High  
CTR: Medium  
Conversion: High  
Effort: Medium  
Confidence: 86%

### **Action**

Update existing page  
Add current pricing  
Add service comparison  
Improve internal links  
Refresh supporting evidence  
Review CTA

That is the quality bar.

---

# **88\. The UI architecture**

The product should not feel like an “AI chatbot”.

Primary navigation:

Command Centre  
Brand Brain  
SEO Intelligence  
Search Intelligence  
Competitors  
Content  
Local  
Paid Growth  
Analytics  
Missions  
Recommendations  
Approvals  
Automations  
Integrations  
Reports  
Settings  
---

# **89\. Command Centre**

The homepage should answer:

### **How is my business performing?**

Organic visibility  
Organic traffic  
Qualified traffic  
Conversions  
Revenue contribution  
AI Search visibility  
Technical health  
Content health

Then:

### **What should I do next?**

Top opportunities.

Then:

### **What is SEO Engine doing?**

Active missions and autonomous workflows.

---

# **90\. The most important screen**

### **Recommendations**

Every recommendation displays:

WHAT  
WHY  
EVIDENCE  
EXPECTED IMPACT  
EFFORT  
RISK  
CONFIDENCE  
DEPENDENCIES  
ACTION

Buttons:

Approve  
Reject  
Modify  
Delegate  
Automate  
---

# **91\. Agent Activity**

The user should be able to see:

SEO Orchestrator  
├── Keyword Agent ✓  
├── Competitor Agent ✓  
├── SERP Agent ✓  
├── Content Agent ✓  
├── Analytics Agent ✓  
└── Decision Agent ●

But we should **not expose chain of thought**.

The UI displays:

* actions  
* evidence  
* decisions  
* outputs  
* reasons

not private internal reasoning.

---

# **92\. Integration roadmap**

### **Alpha**

Website crawler  
GSC  
GA4  
Search  
CMS

### **Beta**

Ahrefs  
Semrush  
Google Ads  
GBP  
Google Trends

### **Commercial**

WordPress  
Webflow  
Shopify  
HubSpot  
Salesforce  
CRM  
email  
social platforms  
---

# **93\. Build order**

This is the order I would give the engineering team.

## **Sprint 0**

Architecture foundation.

Repository  
Docker  
Postgres  
Redis  
Temporal  
API  
Authentication  
Tenancy

## **Sprint 1**

Agent runtime.

Agent registry  
Capability registry  
Task system  
Event system  
Agent context  
Agent result

## **Sprint 2**

Memory.

Brand memory  
Working memory  
Evidence  
Embeddings  
Knowledge graph foundation

## **Sprint 3**

Orchestration.

SEO Orchestrator  
Workflow engine  
Decision engine  
Policy engine  
Approval engine

## **Sprint 4**

Website intelligence.

Crawler  
Page parser  
Technical SEO  
On page SEO

## **Sprint 5**

Search intelligence.

Keyword research  
SERP  
Intent  
Competitors  
Content gaps

## **Sprint 6**

Content.

Research  
Brief  
Writing  
Editing  
Fact checking  
Content scoring  
Repurposing

## **Sprint 7**

Analytics.

GSC  
GA4  
Performance  
Anomaly detection

## **Sprint 8**

Execution.

CMS  
Technical fixes  
Publishing  
Internal links

## **Sprint 9**

Growth.

Local SEO  
Google Ads  
Campaign intelligence

## **Sprint 10**

Autonomy.

Missions  
Persistent monitoring  
Outcome learning  
Policy based automation  
---

# **94\. Definition of done for Alpha**

SEO Engine Alpha is not complete when:

> “The agents respond to prompts.”

It is complete when the system can execute this entire loop:

User:  
"Find opportunities to grow my organic leads."

        ↓

Understand brand  
        ↓  
Audit website  
        ↓  
Research search  
        ↓  
Analyse competitors  
        ↓  
Analyse performance  
        ↓  
Find opportunities  
        ↓  
Prioritise opportunities  
        ↓  
Generate recommendations  
        ↓  
Explain evidence  
        ↓  
User approves  
        ↓  
Create tasks  
        ↓  
Execute changes  
        ↓  
Measure outcomes  
        ↓  
Store outcome  
        ↓  
Update mission

That is our **minimum viable agentic system**.

---

# **95\. The commercial architecture**

Although monetisation comes later, the architecture should not prevent it.

Eventually:

FREE / TRIAL  
     ↓  
STARTER  
     ↓  
PRO  
     ↓  
GROWTH  
     ↓  
AGENCY  
     ↓  
ENTERPRISE

Differentiation should be based on:

* brands  
* websites  
* agent runs  
* research volume  
* connected integrations  
* automation  
* content production  
* analytics history  
* AI usage  
* paid media controls  
* users  
* missions

Not simply “number of AI prompts”.

---

# **96\. The ultimate abstraction**

There is one architectural decision I consider especially important.

Do **not** make SEO Engine's core object:

> `SEO Audit`

Make the core object:

# **`Mission`**

An audit is just one workflow.

The system should eventually support:

Mission:  
Recover lost organic traffic

Mission:  
Launch a new service

Mission:  
Increase qualified leads

Mission:  
Defeat competitor X for topic Y

Mission:  
Improve local visibility

Mission:  
Reduce paid acquisition cost

Mission:  
Build topical authority

Mission:  
Prepare website for AI agents

The orchestrator determines which agents and workflows are required.

That makes SEO Engine extensible far beyond conventional SEO.

---

# **97\. Final reference architecture**

The complete system is therefore:

                        ┌─────────────────────┐  
                         │       USER          │  
                         └──────────┬──────────┘  
                                    │  
                              COMMAND CENTRE  
                                    │  
                         ┌──────────▼──────────┐  
                         │       MISSION       │  
                         └──────────┬──────────┘  
                                    │  
                         ┌──────────▼──────────┐  
                         │    ORCHESTRATOR     │  
                         └──────────┬──────────┘  
                                    │  
             ┌──────────────────────┼──────────────────────┐  
             │                      │                      │  
          RESEARCH              ANALYSIS                STRATEGY  
             │                      │                      │  
       ┌─────┼─────┐        ┌──────┼──────┐       ┌──────┼──────┐  
       │     │     │        │      │      │       │      │      │  
     Market Search Entity  SEO Content Analytics Growth Competitive  
       │     │     │        │      │      │       │      │  
       └─────┴─────┴────────┴──────┴──────┴───────┴──────┘  
                                    │  
                             OPPORTUNITY ENGINE  
                                    │  
                            PRIORITISATION ENGINE  
                                    │  
                             DECISION ENGINE  
                                    │  
                              GUARDIAN LAYER  
                                    │  
                              POLICY ENGINE  
                                    │  
                             APPROVAL ENGINE  
                                    │  
                             EXECUTION ENGINE  
                                    │  
          ┌────────────┬────────────┼───────────┬────────────┐  
          │            │            │           │            │  
         CMS          GSC          GA4         GBP          ADS  
          │            │            │           │            │  
          └────────────┴────────────┼───────────┴────────────┘  
                                    │  
                              OBSERVATION  
                                    │  
                              OUTCOME ENGINE  
                                    │  
                              LEARNING ENGINE  
                                    │  
                             ┌──────▼──────┐  
                             │   MEMORY    │  
                             └──────┬──────┘  
                                    │  
                              KNOWLEDGE GRAPH  
                                    │  
                                    └──────────────→ ORCHESTRATOR

## **The critical architectural distinction**

We are **not** building:

> “A collection of AI tools for SEO.”

We are building:

> **A persistent, evidence based, policy controlled, multi agent operating system that can manage a brand's search and digital growth objectives over time.**

That distinction should govern every engineering decision from this point forward.

And the Google source material gives us an important north star: the product should optimise for **people first usefulness, technical accessibility, authoritative and original content, measurable outcomes and legitimate search visibility**, while treating AI Search as an extension of the underlying Search ecosystem rather than selling customers artificial “GEO hacks.”

**This Architecture Pack should now become the baseline specification for the coding phase.**
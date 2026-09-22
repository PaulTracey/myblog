+++
date = 2026-09-06T16:55:00+01:00
draft = false
title = "Preparing Documentation for AI: Searchability, Structure, and Retrievability"
description = "A practical introduction to preparing documetation for an AI Audience"
tags = ["AI", "Technical Writing", "Documentation"]
categories = ["Technical Writing"]
+++

## Introduction: Audience Analysis

When defining the audience for customer documentation, we increasingly need to consider AI agents alongside the different types of human reader. This does not mean writing documentation for machines instead of humans. It does, however, mean considering how we can prepare AI-optimised documentation that remains clear and useful for human readers.

AI-powered tools can search (Azure AI Search), retrieve (Pinecone), interpret (ChatGPT), and present information (Microsoft Copilot) from that same content. In many cases, users may simply provide documentation directly to a Large Language Model (LLM) and ask questions about it.

The quality of the answer will depend partly on the capabilities of the model, but also on the quality of the source material it has been given. Clear, well-structured documentation provides better context for an LLM to work with, while ambiguous, inconsistent, or poorly organised content can make it more difficult for the model to identify and communicate the correct information.


 [![Audiences](/images/audience.png)](/images/audience.png)

> *The fundamental problem of communication is that of reproducing at one point either* 
> *exactly or approximately a message selected at another point.*
>
> — *Claude Shannon, 1948*


## Optimising Documentation for Audiences

The following sections explore how documentation can be designed from the outset to improve clarity, searchability, and retrieval while also making more efficient use of an AI system's available context.

Established approaches to technical communication already emphasise information organisation, findability, and user intent. IBM's Developing Quality Technical Information identifies organization and retrievability among the characteristics of high-quality technical information. The Diátaxis framework approaches the problem from a different direction, organising documentation around four distinct user needs: tutorials, how-to guides, reference, and explanation.

AI-assisted documentation does not make these principles obsolete. Instead, it introduces new ways in which information is discovered and consumed. For this reason, I use three related characteristics throughout this article: searchability, structure, and retrievability.

Here, searchability describes how readily relevant information can be located, structure describes how that information is organised into meaningful units, and retrievability describes how readily the specific information required to answer a question can be isolated and returned.

### Searchability

Searchability describes how easily a human reader or information system can locate content that is likely to contain the answer they need.

Good searchability depends on clear signals. Use descriptive page titles and headings, consistent terminology, and explicit identifiers such as product names, API endpoints, configuration values, and error codes. Metadata such as descriptions, tags, and version information can also improve how content is indexed and surfaced.

Search engines do more than simply match words. Elasticsearch, for example, uses the BM25 ranking algorithm by default. BM25 considers factors such as how frequently a term appears, how distinctive that term is across the wider document collection, and the length of the field being searched. Search implementations can also give greater weight to particular fields, such as titles or headings.

For example:

``Authentication``

provides little context, while:

``Configure OAuth 2.0 authentication for the REST API``

identifies the task, technology, and scope of the content, giving both human readers and search systems stronger signals.

The unit being indexed also matters. Some systems index complete pages, while others work with sections or smaller chunks. Very large units can dilute relevant information, while very small units may lose useful context. Clearly bounded, topic-focused sections therefore support both traditional search and later AI-based retrieval.

In simple terms, searchability asks:

*Can the reader or system locate content that is likely to contain the answer?*


### Structure

Structure refers to how information is organised, grouped, and presented within a document.

For human readers, good structure makes information easier to scan, understand, and navigate. For AI systems, structure can also provide useful boundaries between topics and help preserve context when sections of a document are processed independently.

This idea is not new. DITA (Darwin Information Typing Architecture) has long promoted topic-based authoring, where information is divided into focused units such as concepts, tasks, and reference topics. Rather than treating documentation as one continuous body of text, DITA encourages authors to create modular topics with a clear purpose and enough context to remain useful when reused elsewhere.

These principles map well to AI-assisted documentation. Retrieval systems commonly divide source documents into smaller units, or chunks, before indexing them for later retrieval. A chunk may contain a paragraph, section, or another bounded piece of content depending on how the system is configured.

If the original documentation already has clear topic boundaries, meaningful headings, and sufficient local context, those chunks are more likely to remain useful when separated from the full page. Poor structure can have the opposite effect: a chunk may contain an instruction without its prerequisite, a value without the parameter it refers to, or an explanation that depends on a heading several sections earlier.

When designing structure, consider the following questions:

What belongs together? Group closely related concepts, instructions, examples, and reference information so that the meaning is preserved when the content is read independently.
Where should information be divided? Use descriptive headings and subsections to create natural boundaries between different concepts, tasks, and stages of a process.
When is additional context required? Keep prerequisites, conditions, constraints, and warnings close to the information that depends on them.
How should the information be presented? Use numbered steps for procedures, tables for comparison, lists for discrete items, and code blocks for commands or examples.
Who needs to understand the section? A section should provide enough context to remain useful even when the reader, human or machine, has not consumed the entire document from beginning to end.

Consider the following sentence:

Set it to true to enable the feature.

It is concise, but it relies entirely on surrounding context. If the sentence appears in a retrieved chunk without the preceding material, its meaning is lost.

A more self-contained version is:

Set automatic_token_renewal to true to enable automatic token renewal.

The second version is slightly longer, but it preserves the identity of both the setting and the action. This illustrates an important point: shorter content is not necessarily more efficient content. A slightly longer, self-contained section may require less additional context to be retrieved before it can be understood.

DITA and modern AI retrieval therefore arrive at a similar design principle from different directions: information is more useful when it is organised into focused, meaningful units.

Good structure does not mean making every section as small as possible. It means creating boundaries that preserve meaning, context, and relationships between pieces of information.

The central question for structure is:

Is the information organised into meaningful units that can still be understood when separated from the wider document?

### Retrievability

**Retrievability** refers to how readily the specific information required to answer a question can be identified, isolated, and returned.

This differs slightly from searchability. Searchability helps locate content that is likely to contain the answer; retrievability is about returning the precise information needed, with enough context for it to remain useful.

In AI-assisted documentation, retrieval may rely on traditional search indexes, vector indexes for semantic similarity, and metadata that helps narrow the search space. Structured formats such as JSON can also carry useful fields such as product name, version, content type, platform, or topic identifier.

For example, a search system may successfully locate a long page about authentication. Good retrievability means it can then isolate the specific passage that answers a question such as:

`Set automatic_token_renewal to true to enable automatic token renewal.`

When writing for retrievability:

* Keep related information together.
* Make versions, platforms, and prerequisites explicit.
* Avoid vague references such as `it`, `this option`, or `the value above`.
* Use consistent terminology and useful metadata.
* Reduce duplication and contradictory content.

The technical writer may not control how indexes or retrieval systems are implemented, but clear structure, consistent metadata, and self-contained content make those systems more effective.

The central question is:

**Can the system return the exact information needed, with enough context for it to be accurate and useful?**



# Testing AI-Readiness

Designing documentation for searchability, structure, and retrievability is only part of the process. These characteristics should also be tested.

Testing does not necessarily require a complex AI evaluation platform. A useful starting point is to create a representative set of questions, search terms, and user tasks, and then examine whether the documentation allows the correct information to be found, isolated, and understood.

The same three characteristics used to design the documentation can therefore also provide a simple framework for evaluating it.

### Testing Searchability

Create a small set of realistic questions or search queries based on things users might actually ask.

For example:

* How do I enable automatic token renewal?
* What setting controls token renewal?
* How do I configure OAuth 2.0 for the REST API?
* Does automatic token renewal work on version X?

Then check whether the correct page or section appears near the top of the results.

Testing only exact terminology is insufficient. A user might search for "renew access token automatically" even though the documentation uses `automatic_token_renewal`.

It is therefore useful to test several types of query, including:

* exact keyword searches;
* natural-language questions;
* alternative terminology;
* product or feature names;
* identifiers such as API endpoints, configuration parameters, and error codes.

The objective is not necessarily for every query to return exactly the same result. Instead, the relevant documentation should be sufficiently well described and indexed that reasonable variations of the same information need still lead the user towards the correct content.

This type of testing can be performed using the documentation site's existing search functionality, an enterprise search system, or the search component used by an AI retrieval system.

A simple test might record the query, the expected result, and the position at which that result appeared.

| Query                          | Expected result             | Position |
| ------------------------------ | --------------------------- | -------- |
| enable automatic token renewal | Token renewal configuration | 1        |
| renew token automatically      | Token renewal configuration | 2        |
| `automatic_token_renewal`      | Parameter reference         | 1        |

If relevant documentation repeatedly fails to appear for reasonable queries, the problem may lie in page titles, headings, terminology, metadata, content organisation, or the search implementation itself.

The central testing question is:

**Can users and systems reliably locate the content that is likely to contain the answer?**

### Testing Structure

Structure can be tested by examining documentation outside the context of the complete page.

Take a section of content and ask whether it can still be understood when the surrounding sections are removed. This approximates what may happen when an AI retrieval system divides a document into chunks and returns only the sections considered relevant to a question.

Look for information that depends unnecessarily on distant context.

For example:

`Set it to true to enable the feature.`

If this sentence is retrieved independently, neither `it` nor `the feature` provides enough information to identify what the instruction refers to.

Compare this with:

`Set automatic_token_renewal to true to enable automatic token renewal.`

The second version retains its meaning even when separated from the surrounding documentation.

When testing individual sections, consider the following questions:

* Is the subject of the section clear?
* Are important product names, settings, parameters, or features explicitly identified?
* Are prerequisites close to the instructions that depend on them?
* Are warnings and constraints attached to the relevant task?
* Do examples contain enough information to explain what they demonstrate?
* Does the section depend heavily on phrases such as `this`, `it`, `above`, or `the following option`?
* Would the section still make sense if it were returned without the preceding paragraph?

Headings should also be considered. A heading may provide important context to a human reader viewing the complete page, but some retrieval systems may not always preserve that context in the same way.

For example, a section headed:

`Automatic token renewal`

followed by:

`Set it to true.`

may appear understandable on the page but becomes ambiguous if the sentence is separated from its heading.

Testing structure therefore means treating sections as potentially independent information units rather than assuming that every reader or system will consume the page sequentially.

The central testing question is:

**Does the information retain its meaning when separated from the wider document?**

### Testing Retrievability

Retrievability can be tested by creating a set of questions for which the expected answers are already known.

These can be treated as a small reference set of questions representing common user information needs.

For each question, identify both the expected answer and the section of documentation that contains it.

For example:

| Question                                           | Expected source             | Correct content retrieved? | Enough context? |
| -------------------------------------------------- | --------------------------- | -------------------------- | --------------- |
| How do I enable automatic token renewal?           | Token renewal configuration | Yes                        | Yes             |
| What is the default value?                         | Parameter reference         | Yes                        | No              |
| Is automatic token renewal supported in version X? | Version compatibility       | No                         | —               |

The retrieved information can then be evaluated independently of the final AI-generated answer.

Ask:

* Was the correct passage retrieved?
* Was unnecessary or unrelated content also returned?
* Did the passage contain enough context to answer the question?
* Were version, platform, and product constraints preserved?
* Could the question be answered accurately using only the retrieved information?

An LLM can also be used as part of the test. Provide only the retrieved content to the model and ask it to answer the original question. If the model cannot answer accurately despite the documentation containing the correct information elsewhere, this may indicate a retrieval problem rather than a language-model problem.

This distinction is useful when diagnosing failures.

If the correct page cannot be located, investigate **searchability**.

If the correct section is retrieved but loses its meaning when separated from the surrounding page, investigate **structure**.

If the correct page is found but the required information cannot be isolated with sufficient context, investigate **retrievability**.

If the correct and complete information is retrieved but the AI system still produces an incorrect answer, the problem may instead lie further downstream in the AI system.

This type of testing does not replace formal retrieval evaluation, but it provides technical writers with a practical way to assess whether their content is suitable for AI-assisted consumption.

The central testing question is:

**Can the system retrieve the specific information needed to answer the question accurately and with sufficient context?**

## Conclusion

Preparing documentation for an AI audience does not require abandoning established principles of technical communication. Clear organisation, consistent terminology, meaningful topic boundaries, and useful metadata already benefit human readers. AI-assisted search and retrieval make these qualities even more important.

Searchability helps users and systems locate content that is likely to contain an answer. Structure determines whether that content remains understandable when divided into smaller information units. Retrievability determines whether the specific information required can be isolated and returned with enough context to remain accurate and useful.

These characteristics are closely related. Improving one may also improve the others, but they describe different stages in the path between a user's question and the information required to answer it.

Technical writers may not control the search engine, vector database, retrieval pipeline, or language model used to consume their documentation. They do, however, have significant influence over the quality and organisation of the source material those systems depend upon.

AI-ready documentation is therefore not simply documentation written for machines. It is documentation designed so that meaning survives search, extraction, retrieval, and reuse while remaining clear and useful to the human reader.

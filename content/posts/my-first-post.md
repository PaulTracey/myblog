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

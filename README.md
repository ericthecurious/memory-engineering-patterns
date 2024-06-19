# memory-engineering-patterns

Recurring patterns to manage memories in Large Language Models (LLMs)

## Introduction

This document outlines essential patterns for managing the memory of LLMs. Manual Patterns require a human in the loop to manage memories, whereas Generative Patterns require a well-engineered prompt so that an LLM can manage its own memory store. These patterns are critical for ensuring that the information stored within a memory store is accurate, relevant, and optimized for machine processing, not just human understanding.

## Manual Patterns

These patterns require direct human intervention that manages the memory of an LLM without using generative patterns. This approach ensures adherence to specific requirements as determined by the human in the loop while avoiding the potential unreliability of generative patterns. 

A risk of all these patterns is that the person makes a change to the memory store that is optimized for human memory instead of machine memory. For example, a person might know what a specific phrase means in their human memory yet fail to tell the LLM what it means. Thus, the human in the loop needs to ensure that they've provided all the necessary context for the LLM to remember. 

In short, be specific with these patterns.

### Manual Create

You manually create a new memory to add relevant, contextual information to the LLM’s memory store. You get to explicitly craft the new memory so that it's exactly how you want it. Be mindful of how many total memories you create because each additional memory adds to the total context length, thus increasing computational demands.

### Manual Edit

You manually edit an existing memory to ensure its continued relevance and accuracy. You may want to edit the initial output from a generative pattern, or you may want to edit an older memory that has become irrelevant, incomplete, or inaccurate over time. In any case, you want to keep the memory as distinct yet refined.

### Manual Delete

You manually delete an existing memory to remove its influence on the LLM. Perhaps it has become terminally irrelevant or inaccurate. In any case, you want the memory to be forgotten. Deleting memories that are no longer needed ensures the LLM only remembers currently relevant information while also decreasing the context length and computational demands.

### Manual Approval

You require manual approval of the output from a generative pattern by a human in the loop. Perhaps you're the reviewer, or perhaps you delegate the approval to an external expert. Doing so gives whoever the human reviewer is the ability to correct mistakes, inaccuracies, and hallucinations from the generative patterns.

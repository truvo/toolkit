---
name: truvo-api
description: Add Truvo auto, renters, or pet insurance quotes to an app with a Truvo API key. Use it when the user asks to integrate Truvo into their product or to test the Truvo API with a sandbox key.
---

# Truvo API

1. Read https://docs.truvo.com/guides/agents.md before you write code. It covers every operation, the keys, errors, and polling.
2. Use the sandbox key in the TRUVO_API_KEY environment variable. Keep it out of the chat, the logs, and any file you commit.
3. Call get_capabilities for the line first. It lists the states and the facts a request needs.
4. Ask the person for each required fact, and for each fact marked Recommended, which they may skip. Use what you or the app already know about the person, show it back, and get their OK before sending. Never guess; an unknown stays unknown.
5. Start the request with start_quote_request and a new request_key. Read the result with get_quote_request and wait_seconds.
6. Tell the person that a quote is a price offer, not coverage, and offer only the next actions that the quote lists.

---
name: truvo-quotes
description: Get auto, renters, or pet insurance quotes for the signed-in person. Use it when they ask for their own insurance quotes through Truvo.
---

# Truvo quotes

1. The person is signed in with Truvo. You act for that one person. Follow the tool descriptions, the server instructions, and `agent_guidance` from `get_capabilities`.
2. Ask which line they want: car (`personal_auto`), renters, or pet. Call `get_capabilities` for that line first. Check that their state is in `states`.
3. Ask the person for each required fact, and for each fact marked Recommended, which they may skip. Use what you already know about the person, show it back, and get their OK before sending. Never guess. Every request needs their email and a US phone number.
4. Show the `quote_disclosure` text from `get_capabilities` as written, and ask whether they agree. Start a request only if they do. Send its `version` in `quote_disclosure_version`, and send `quote_disclosure_accepted: true` only when they agree.
5. Start the request with `start_quote_request` and a new `request_key`. Read the result with `get_quote_request` and `wait_seconds`. `list_quote_requests` lists the requests this person started while signed in.
6. Tell the person that a quote is a price offer, not coverage, and offer only the next actions that the quote lists.

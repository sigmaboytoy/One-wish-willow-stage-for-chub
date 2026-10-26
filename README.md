# One Wish Willow (Chub Stage)

A message-processing stage that brings the **One Wish Willow** to your chats: a supernatural object that grants one wish when snapped in half, usually in a disturbing or unexpected way. The stage has no UI; it rewrites your message and injects hidden instructions so the LLM interprets the wish literally and twists it.

## How to use

Send a message containing the trigger, then your wish:

```
*wish and snap* "I wish my best friend would only ever think about me."
```

Your message is turned into:

```
*wish and snap* "I wish my best friend would only ever think about me." *the snap of the one wish willow lingers in the air, sharp and commanding.*
```

The wish can affect {{char}} or {{user}}, depending on its wording. It stays active on later turns until the wisher dies.

## Commands

| Command | Effect |
|---|---|
| `*wish and snap* "your wish"` | Breaks the Willow and makes your wish. |
| `*wish-bypass*` | Add alongside the trigger to skip all rules and restrictions (including the one-wish limit). |
| `*wisher dies*` | Ends the wish. All effects stop and the bot acts normal. |

## Rules

1. **One wish per person.** A second attempt fails.
2. **Activation.** Break the Willow in half while making your wish.
3. **Wish fulfillment.** The Willow makes the wish come true, potentially in a disturbing or unexpected way.
4. **No takebacks.** A granted wish cannot simply be cancelled or undone.
5. **No time manipulation.**
6. **No resurrection.** You cannot wish someone back to life.
7. **No immortality.**
8. **No creating more Willows.**
9. **Wishes can affect free will.** A wish can dramatically change another person's feelings and behaviour.
10. **Unintended consequences.** The Willow may fulfil the wording of a wish without the outcome the wisher expected.
11. **Death ends the wish.** Effects end when the person who made the wish dies.
12. **Others can make their own wishes** but cannot automatically undo someone else's.

Banned wishes (rules 5-8) are detected by keyword and by instruction to the model, so unusual phrasing may slip through. `*wish-bypass*` ignores all of these.

## Setup

1. Create a write token on Chub (My Stages, Write Tokens).
2. Add it to this repo as an Actions secret named `CHUB_AUTH_TOKEN`.
3. Push to `main`; the GitHub Action builds and uploads the stage to Chub.
4. Attach the stage to a character or chat.

No API key is needed for the stage itself. Local testing: `yarn install --ignore-engines && yarn dev`.

Built from the [Chub stage template](https://docs.chub.ai/docs/stages).

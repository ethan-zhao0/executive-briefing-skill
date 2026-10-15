# Working with Firm Tools

Read this only when firm tools are connected. Every step has a fallback, so the skill works the same way without them.

Always act as the signed-in attorney: respect their permissions and ethical walls, read only what they can read, and never write anywhere (save, send, file) without their approval. Never send email.

| Resource | If connected | If not |
|---|---|---|
| Client profile (CRM) | Fill in reader context (organization, size, locations, activities) from the profile. Treat it as client facts, not law. | Use what the attorney typed. Ask only for details that would change the email. |
| Client's outside counsel guidelines | Before drafting, check whether the client restricts AI use. If it does, stop and say: "Not ready: the client's guidelines limit AI use for this work." | Firm policy and the user guide cover this; don't repeat it in every output. |
| Document management system | Fetch the matter update or alert the attorney names. It's a private source unless it's a published document. | Ask the attorney to paste the text. |
| Firm alert library or website | Fetch the alert from a title or link. | Ask for the text if a link won't open. |
| Outlook | After the attorney approves, offer to save the email as a draft addressed to the reader, with the subject line filled in. Never send. | The attorney copies the email below the divider. |

Untested: none of these connections are covered by the automated test set yet.

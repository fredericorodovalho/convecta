<!-- LOVABLE:BEGIN -->
> [!IMPORTANT]
> This project is connected to [Lovable](https://lovable.dev). Avoid rewriting
> published git history — force pushing, or rebasing/amending/squashing commits
> that are already pushed — as it rewrites history on Lovable's side and the
> user will likely lose their project history.
>
> Commits you push to the connected branch sync back to Lovable and show up in
> the editor, so keep the branch in a working state.
<!-- LOVABLE:END -->

- Use AI Elements and AI SDK UI-message streaming for the chat so messages, reasoning and cancellation share one protocol.
- Keep research conversations only in root-provider memory and derive active IDs from chat page URLs; reload intentionally clears history.
- Keep AI prompts and gateway calls in server-only modules; parse user files client-side using dynamic imports to avoid SSR browser dependencies.
- Normalize photo uploads in the browser and carry inline image FileUIParts through the existing UI-message transport; validate them server-side to avoid external fetches and preserve temporary chat storage.
- Submit pending first turns only after the routed chat commits, so navigation cleanup does not abort the request.
- Preserve upstream AI failure statuses after the SDK local start event and disable automatic SDK retries, so terminal failures are not replayed.
- Library and saved-summary search share the authenticated summaries query and cache key so both screens read the same private records.

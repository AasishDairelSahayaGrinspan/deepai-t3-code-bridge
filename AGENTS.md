# Instructions for coding agents

## Purpose and scope

This repository documents an **unofficial, personal** integration architecture. It does not include a bridge implementation, installer, credentials, or enough information to recreate the original machine-specific relay. Do not imply that cloning this repository by itself installs or enables DeepAI models.

When asked to help someone use this setup:

1. Explain that they need a separately installed, authorized bridge or a currently supported DeepAI endpoint, as well as a valid account session.
2. Do not assume the original author's local bridge, files, paths, port, tokens, or credentials are available to the user.
3. Prefer documented, supported APIs and the provider's current terms. If the user requests a new implementation, clarify that the repository does not contain one and avoid relying on undocumented app internals or reverse-engineered authentication.
4. Never ask the user to paste credentials into chat or commit them to a repository. Use placeholders in examples and recommend local secret storage. If credentials may have been exposed, advise rotating them.
5. Keep any local relay bound to loopback unless the user explicitly requests a reviewed, authenticated remote deployment; never expose a credential-bearing relay to the network by default.

## Using an already configured provider in T3 Code

If the user's OpenCode-compatible configuration already defines the `deepai` provider and points to a working local bridge or supported endpoint:

- Open the model picker and search for `deepai`, a model ID such as `glm-5.3-flash`, or another configured model name.
- Select a result whose provider is `deepai`. In T3 Code, custom providers sourced from OpenCode configuration appear under the **OpenCode** section; this is expected and does not mean the model is supplied by OpenCode.
- Example model IDs from the documented setup include `deepai/glm-5.3-flash` and `deepai/deepseek-v4.1-flash`. Availability can change; use the IDs in the user's current configuration.
- From a terminal with OpenCode installed, a configured model can be tested with `opencode run -m deepai/glm-5.3-flash "Reply with a short greeting."`.
- If models do not appear, verify that T3 Code is reading the intended config, that the provider/model IDs are valid, and that the configured endpoint is reachable. Reload or restart T3 Code after config changes. Do not print tokens or credential-file contents while troubleshooting.

## Repository changes

- Keep documentation accurate about the difference between T3 Code's model-picker grouping and the provider's identity.
- Do not add real tokens, API keys, machine identifiers, private account data, personal filesystem paths, or logs containing sensitive request headers.
- Do not add bridge code that depends on extracting credentials from a desktop application's private storage or reproduces undocumented authentication. Keep this repository documentation-only unless the user explicitly asks for a supported, reviewable implementation and its security/terms constraints have been addressed.
- Use placeholders for any configuration examples and state their prerequisites and limitations.

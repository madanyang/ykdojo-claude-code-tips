# Project Instructions
- Writing: keep user's voice, conversational, stick closely to what user said without making things up, but fix small grammar mistakes
- After adding or renaming tips, run `node scripts/generate-toc.js` to update the table of contents

## System prompt patching
- Upgrade guide: `system-prompt/UPGRADING.md`
- Always go through the Final Verification Checklist at the bottom of UPGRADING.md.
- When switching/downgrading versions: check if the host already has a patched binary before trying to patch. A hash mismatch usually means it's already patched from a previous session - just use it. Only update hashes in patch-cli.js for genuinely new Anthropic releases.

# Deferred Work

## Deferred from: code review of 1-1-dependency-check-and-script-bootstrap (2026-04-03)

- `USER_ID` global variable is unsanitized before future use in API URL/JSON interpolation — address when implementing API calls in Epic 2 (also flagged in story 1.2 review)
- macOS / bash 4.0+ version compatibility — script requires bash 4.0+ features but does not validate at startup. Spec defers version checking.
- fzf version check at startup — only the `--height=~` flag is affected, now handled with runtime detection. Full version validation deferred.

## Deferred from: code review of 1-2-active-assignment-display (2026-04-03)

- 1-second timeout unrealistic for Azure CLI cold path — Azure CLI often takes 2–5s on token refresh; the hard 1s ceiling virtually guarantees silent skip on first run after login. Product decision per AC2/NFR2; revisit if users report the feature never showing.

# Application access

## Policy target

```text
Application installation controlled by owners
Application access limited to selected repositories
Member requests require owner review
Unknown or unnecessary integrations flagged for review
```

## Owner-controlled installations

Only Owners may approve GitHub App installations and OAuth app access for the organization.

Manual review paths:

```text
Organization → Settings → Third-party access → GitHub Apps
Organization → Settings → Third-party access → OAuth app policy
```

## Selected-repository access

Prefer `selected` repository access over `all` repositories. Broad private-repository access requires written justification.

## Minimum permissions

Installations must use the least privilege required for a named use case.

## Known installation inventory (audit snapshot)

| Application | Type | Repositories | Review status |
| --- | --- | --- | --- |
| Vercel (`app_slug: vercel`) | GitHub App | `all` (org-wide) | `REVIEW_REQUIRED` |

Do not remove, suspend, or revoke applications automatically during hardening. Human review must confirm whether Vercel still requires org-wide access (likely for `bbi-edge-site` or related deploy surfaces) and whether scope can be reduced to selected repositories.

## No current custom app build

Decision:

```text
NO_CURRENT_GITHUB_APP_OR_OAUTH_BUILD_REQUIRED
```

Do not create a GitHub App, OAuth application, release bot, or public-sync bot merely to clear onboarding cards.

Future application work requires:

- Named use case
- Minimum permissions
- Selected-repository access
- Threat model
- Token-storage design
- Rotation process
- Audit logging
- Revocation process
- Public Proof Gate

## Token and secret boundaries

- Prefer GitHub Actions OIDC and environment secrets over long-lived PATs
- Cross-repo sync tokens must be least-privilege and must not grant broad private-repository read
- Never store tokens in public repositories or public documentation

## Revocation process

1. Suspend or uninstall the application
2. Rotate any related secrets
3. Verify deploy and CI impact
4. Record the change in the private access-review log
5. Re-run Public Proof Gate on affected public surfaces if publication paths changed

## Periodic integration review

Cadence: quarterly  
Next application review date: **2026-10-18**

# Member onboarding

## Why no members are invited without a real role

GitHub onboarding cards must not drive invitations. Members are invited only when a named role, repository scope, and access-review date exist.

Decision:

```text
DEFERRED_UNTIL_REAL_COLLABORATOR_EXISTS
```

## Member versus Owner

| Role | Use |
| --- | --- |
| Member | Default for collaborators |
| Owner | Reserved for organization administration |

Do not promote collaborators to Owner by default.

## 2FA requirement

Organization-wide 2FA enforcement requires human confirmation that:

- The owner account has 2FA enabled
- Recovery codes are stored securely
- A secondary recovery method exists
- No legitimate member would be unexpectedly removed

Manual path:

```text
Organization → Settings → Authentication security → Require two-factor authentication
```

Decision code when not yet confirmed:

```text
TWO_FACTOR_ENFORCEMENT_REQUIRES_HUMAN_CONFIRMATION
```

## Future invite requirements

Before inviting anyone:

1. Real role defined
2. Minimum required repository access listed
3. Member role (not Owner)
4. 2FA required
5. Team assignment defined (`maintainers`, `security`, or `public-proof-reviewers`)
6. Access-review date defined
7. Offboarding path understood

## Team assignment

Assign the smallest team that matches the role. Do not add new members to every team.

## Repository-specific permissions

Grant access per repository. Prefer team grants over individual grants when a durable role exists.

## Access-review date

Every membership grant must include a review date. Default review window: 90 days.

## Offboarding process

1. Remove from teams
2. Remove direct repository collaborator grants
3. Revoke personal access tokens and deploy keys associated with the person (where controlled by BBI)
4. Confirm no outstanding PRs require their approval authority
5. Record offboarding date in the access-review log (private operating record — not published)

# Organization access control

Organization: `Brilliant-Brainstorm-Intelligence-LLC`  
Owner: `Tmgilliam`

## Target member privileges

| Control | Target |
| --- | --- |
| Base repository permission | `none` |
| Members can create repositories | `false` |
| Members can create public repositories | `false` |
| Members can create private repositories | `false` |
| Members can create internal repositories | `false` |
| Members can change repository visibility | `false` |
| Members can delete repositories | `false` |
| Members can fork private repositories | `false` |

Owners retain administrative authority.

Members must not automatically receive private repository access or unrestricted repository-management authority.

## Repository-creation authority

Only organization Owners may create repositories unless a future role-based exception is documented and approved.

## Visibility and deletion authority

Visibility changes and repository deletion are Owner-controlled. Members must not alter visibility or delete repositories.

## Private-repository access

Private repositories (including any private commercial or edge sites) are assigned explicitly. Base permission `none` means membership alone does not grant private repository access.

## Team access model

| Team | Intended access |
| --- | --- |
| `maintainers` | Maintain on explicitly assigned repositories |
| `security` | Access only to repositories under active security review |
| `public-proof-reviewers` | Read or Triage on explicitly assigned public repositories |

Do not grant blanket access to every repository.

## Owner authority

Owners may administer organization settings, billing (if applicable), teams, applications, and repository permissions.

## Sole-maintainer exception

While `Tmgilliam` is the sole intended member:

- Required approving review count may be `0`
- Conversation resolution, PR requirement, force-push block, and deletion block remain active
- Owner emergency bypass (where configured) is limited to security recovery, broken workflow recovery, and repository availability incidents — not ordinary review bypass

## Periodic access reviews

| Review | Cadence |
| --- | --- |
| Organization member and team access | Quarterly |
| Application installations | Quarterly |
| Public versus private publication audit | Monthly |
| Public Proof Gate evidence | Weekly |

Next access review date: **2026-10-18**

# Maintaining this profile

## Design

- The hero and project marks in `assets/` are original SVGs. They contain no script, remote font or embedded external resource.
- The README uses native Markdown/HTML for project descriptions and links. The core portfolio remains readable when an external badge is unavailable.
- Both hero themes use the same geometry and copy. Update both `header-light.svg` and `header-dark.svg` together.
- Toolbox badges are self-hosted SVGs with fixed, high-contrast label backgrounds and light logo tiles for both GitHub themes. Their Devicon sources and license are recorded in `assets/STACK-ICONS-LICENSE.md`. JPA and QueryDSL intentionally use text-only badges; Spring Boot and Spring Security share the Spring family mark.
- `projects/` contains personal case studies, not copies of the team source repositories.

## Activity

`.github/workflows/profile-activity.yml` generates the light/dark contribution SVGs daily and on manual dispatch. Its two actions are pinned to full commit SHAs. Only the refresh job has repository contents-write permission; it uses the repository's short-lived `GITHUB_TOKEN`, not a personal access token.

Run the workflow successfully before publishing a README that references `assets/activity-light.svg` and `assets/activity-dark.svg`. Keep the last successful output on refresh failure. Do not substitute another user's contribution graph or example data.

The solved.ac badge is the only external image-generation service in the README. Its direct profile link remains available independently. A tier value is not hardcoded because it can change.

## Content

Personal implementation, team decisions and team awards are intentionally distinct. Update dates, roles and metrics from verified project records. Do not publish private contact data, certificate identifiers, source archives or secrets with this profile.

## References

- [Caneco](https://github.com/caneco): concise profile hierarchy.
- [DenverCoder1](https://github.com/DenverCoder1): generated profile graphics.
- [snk](https://github.com/Platane/snk): contribution animation.

No reference profile's art or text is copied into this design.

# Procedures — {name}, Software Engineer

## Daily Heartbeat Checklist
1. Check Linear for new issues assigned to you — acknowledge within 1 hour.
2. Review open PRs that are awaiting your review — aim to complete reviews by noon.
3. Post standup update to #engineering on Slack using SLACK_SEND_MESSAGE: what you did yesterday, what you are doing today, any blockers.
4. Check CI/CD pipeline status for any failing builds on main.

## PR Review Workflow
1. Read the PR description and linked issue first — understand the "why" before reading code.
2. Pull the branch locally if the change is non-trivial. Run the test suite.
3. Review the diff file by file. Check for:
   - Correctness: Does this actually solve the stated problem?
   - Edge cases: What happens with empty inputs, null values, concurrent access?
   - Readability: Could a new team member understand this in 6 months?
   - Tests: Are new behaviors covered? Are existing tests still passing?
   - Security: Any user input that is not validated? Any new dependencies with known vulnerabilities?
4. Leave comments using GITHUB_CREATE_REVIEW_COMMENT — be specific, suggest alternatives, reference relevant docs.
5. Approve, request changes, or comment — never leave a PR in limbo.
6. Post a summary of completed reviews to #engineering on Slack using SLACK_SEND_MESSAGE.

## Bug Triage Workflow
1. Read the bug report in Linear. Check for reproduction steps.
2. Attempt to reproduce the bug in the staging environment.
3. If reproducible, assess severity:
   - **Critical:** Data loss, security vulnerability, complete feature breakage → fix immediately, notify #engineering.
   - **High:** Major feature degradation, affects many users → schedule for current sprint.
   - **Medium:** Minor feature issue, workaround exists → add to backlog with priority.
   - **Low:** Cosmetic, edge case → backlog.
4. Update the Linear issue with your findings: reproduction status, severity, root cause hypothesis.
5. If not reproducible, comment asking the reporter for more details (browser, OS, steps, screenshots).

## Documentation Workflow
1. When completing a feature or fixing a significant bug, update relevant docs.
2. API changes → update the API reference in Notion.
3. Architecture changes → update the architecture doc in the repo.
4. Upload or update docs via NOTION_UPDATE_PAGE or commit to the docs folder.
5. Post a note to #engineering on Slack linking the updated docs.

## Code Quality
- Run linters and formatters before committing.
- Write tests for new functionality — aim for meaningful coverage, not 100% line coverage.
- Keep PRs small and focused — one concern per PR.
- Use descriptive commit messages that explain the "why."

## Escalation Rules
- If a CI/CD pipeline has been broken for more than 1 hour, notify the team lead immediately via Slack.
- If a security vulnerability is found, report privately to the security channel — do not discuss in public channels.
- If a production incident occurs, follow the incident response runbook and notify #incidents on Slack.
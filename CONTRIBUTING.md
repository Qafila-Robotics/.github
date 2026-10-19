# Contributing to Qafila Robotics

We work in small, reviewable steps. The rules below keep the fleet safe and the history clean.

## How we work

1. **Issue first.** Every change starts as an issue (task, bug or safety incident). No issue, no PR.
2. **Plan first.** For anything non-trivial, agree the plan on the issue before writing code. With
   Claude Code, send the plan-mode prompt and get approval before implementation.
3. **One issue = one PR.** A PR should be reviewable in about 30 minutes. If it is bigger, split it.
4. **Read `CLAUDE.md`** in the repository root before starting — it holds the non-negotiable rules.

## Branches and commits

- Branch names: `<type>/<issue>-<short-name>`, e.g. `feat/42-enrollment-keys`, `fix/51-outbox-ack`.
  Types: `feat`, `fix`, `docs`, `chore`, `test`, `refactor`, `safety`.
- Commits follow **Conventional Commits**: `type(scope): summary`, e.g. `feat(control-plane): add robot registry`.
- `main` is **protected**: changes land through a reviewed pull request, never a direct push.

## Definition of done

- [ ] Acceptance criteria on the issue are all met.
- [ ] Tests added or updated; hardware-free tests pass in CI.
- [ ] Any mocked or untested-on-hardware path is marked `# MOCK` and listed in the PR.
- [ ] No secrets in code or config; `.env*` stays git-ignored.
- [ ] Docs/runbooks updated if behaviour changed.
- [ ] Safety and/or Brand check in the PR template completed where it applies.

## Testing robots safely

Robot behaviour is tested in simulation first (`unitree_mujoco`, ArduPilot SITL, Gazebo), then on
hardware under these rules:

- **A second person with a stop button** is present for any powered motion test.
- **The G1 is on a gantry** with fall handling armed for any new behaviour.
- **Drones fly only in the netted area** until outdoor permission (QCAA) is confirmed in writing.
- The physical e-stop and on-robot watchdog are the safety system — code is advice, never an interlock.
- No powered motion without a tested e-stop within reach.

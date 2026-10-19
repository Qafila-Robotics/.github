<!-- Keep this short. One issue = one PR, reviewable in about 30 minutes. -->

## What and why
<!-- What does this change do, and which issue does it close? -->
Closes #

## How it was tested
<!-- Tick what applies and give the evidence (command, result, video). -->
- [ ] Unit tests
- [ ] Simulation (unitree_mujoco / ArduPilot SITL / Gazebo)
- [ ] Real hardware
- [ ] Not yet run on hardware — paths are marked `# MOCK`

## Mocks and open questions
<!-- List every `# MOCK` path and anything you are unsure about. -->

## Safety check — required for robot code (edge/, firmware/, adapters, control)
- [ ] Every motion command expires (deadman); no fresh command ⇒ stop
- [ ] Link loss ⇒ stop and hold, never autonomous motion
- [ ] No unauthenticated endpoint can move a robot; no `allow_origins=["*"]` on control APIs
- [ ] G1 safe-stop keeps it standing (damping only on gantry / when seated)
- [ ] N/A — this PR does not touch robot control

## Brand check — required for website, dashboard or brand changes
- [ ] Right logo version; five dots, maroon leader leftmost and largest
- [ ] Colours from tokens only; sand tones not used for body text; errors use `danger`, not maroon
- [ ] Works in Arabic (RTL) and English; logical CSS properties
- [ ] No invented customers, numbers, quotes or capabilities; placeholders marked `[TBD]`
- [ ] N/A — this PR does not touch website / dashboard / brand

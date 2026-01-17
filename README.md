# PreStage Control Plane

This project pre-stages and intakes projects/workstreams. It enforces strict readiness gates and drives downstream OpenCode workflows safely. Filesystem-only operations. No execution work allowed.

## Rules
- Use templates for all inputs
- Enforce GO/NO-GO gates
- Prohibit external dependencies
- Optimize for reuse

## Human Overview
For a human-readable explanation of purpose, design, and usage, see:  
**[Prestage Control Plane — Human Overview](prestage-control-plane/docs/HUMAN_OVERVIEW.md)**

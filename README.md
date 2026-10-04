# pip-skills

Published robot profiles and skill versions for **PIP-01**, a small companion robot with the physical character and movement ambition of a 10–12-month-old child: sitting up, crawling, cuddling.

Each release is a robot profile (one body revision, such as `p12-r40`) with immutable, versioned skills. Every skill version carries its parameters, the simulation evidence behind it and SHA-256 hashes. The robot's Updates screen pulls releases from here. Anyone may use them under the MIT licence.

## Layout (from the first release)

```text
profiles/<prototype>-<rev>/
  profile.yaml, joints.yaml, skills.yaml   # body description and active skill versions
  model/                                   # physics snapshot used to develop the skills
  skills/<skill>/<version>/
    skill.json     # entry/exit postures, control rate, evidence summary, hashes
    params.json    # the motion itself (keyframes: joint targets, durations, easing)
    evidence.md    # how it was tested in simulation
```

Published versions are never overwritten; a change is a new version.

## Status

Skills here are **experimental**. They are developed and tested in MuJoCo simulation. Physical-robot evidence will be added per skill as the hardware is built. They describe a specific small robot body and are not meant for any other machine without re-validation.

## Licence

[MIT](LICENSE).

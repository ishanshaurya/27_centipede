# LLM Prompts Used

## Task 1: Fix mushroom durability bug

Role: You're a game dev doing code review on a Pygame project — sharp eye for off-by-one bugs.

Objective: In game.py, hit_mushroom() should let a mushroom survive 4 hits (MUSHROOM_HP=4) before removing it. Right now it dies after 3. Find the comparison operator causing the off-by-one and fix it.

Output: Just the corrected line(s) + one-sentence explanation of why the old comparison was wrong.

---

## Task 2: Implement mushroom_color(hp)

Role: You're a gameplay/VFX engineer working on a Pygame Centipede clone.

Objective: Implement mushroom_color(hp) in game.py. It's called once per mushroom per frame as `color = mushroom_color(hp) or (200 - (MUSHROOM_HP - hp) * 40, 80, 170)`, where hp ranges 1 to MUSHROOM_HP (4). Return an (r, g, b) tuple, or None to fall back to the default fade. Make the mushroom flash white on the frame it's hit.

Output: Just the function body + one-sentence explanation of the approach.

---

## Task 3: Implement on_segment_hit(segment, score)

Role: You're a gameplay engineer adding juice/feedback effects to a Pygame Centipede clone.

Objective: Implement on_segment_hit(segment, score) in game.py. It's called from split_chain right after a body segment is destroyed, the chain splits into two, and points are added (100 for head shot, 10 otherwise). It receives the destroyed Segment and the score after this hit's points were added. Return value is ignored. Idea: a spark effect at the segment's last position, or a bonus for head shots.

Output: Just the function body + one-sentence explanation of the approach.

---

## Task 4: Implement wave_speed_bonus(wave)

Role: You're a game balance/difficulty engineer on a Pygame Centipede clone.

Objective: Implement wave_speed_bonus(wave) in game.py. It's called every frame in update() as `effective_tick = TICK / (wave_speed_bonus(self.wave) or 1)`, where a bigger multiplier means a smaller tick, so segments step more often (faster). It receives the current wave number (starts at 1). Return a speed multiplier, or None for the default speed. Idea: return 1 + 0.15 * (wave - 1) so later waves are noticeably faster.

Output: Just the function body + one-sentence explanation of the approach.

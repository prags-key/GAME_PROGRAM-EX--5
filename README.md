# GAME PROGRAMMING - EX - 5

## EXP - 5 Making Player to collect the ammo and increase the bullet spawn count.

## Name : PRAGATHI KUMAR
## Reg no : 212224230200

##  Aim
To implement a gameplay feature where the player collects ammo pickups in the game world. Upon collecting ammo, the player's ammo count increases, enabling more bullet spawns (shots).

## Procedure

### 1. Setup Player Character

- Open your `PlayerCharacter` Blueprint.s
- Add a new **Integer** variable named `AmmoCount`.
- Set an initial default value (e.g., `AmmoCount = 10`).
- Ensure you have a shooting mechanism in place that uses `AmmoCount` to determine if a bullet can be fired.

### 2. Create Ammo Pickup Blueprint

- Go to the Content Browser → Right-click → **Blueprint Class** → Select **Actor** → Name it `BP_AmmoPickup`.
- Add components:
  - **Static Mesh**: Representing the ammo (e.g., a bullet or crate).
  - **Sphere Collision**: To detect overlap with the player.
- In the Event Graph of `BP_AmmoPickup`:
  - Use `OnComponentBeginOverlap` on the Sphere Collision.
  - Cast to `PlayerCharacter`.
  - Increase the player’s `AmmoCount` (e.g., `AmmoCount += 5`).
  - Optionally, play a pickup sound or effect.
  - Destroy the ammo pickup actor.

### 3. Update Shooting Logic (Optional)

- In your player’s shooting logic:
  - Before spawning a bullet, check `if AmmoCount > 0`.
  - If true:
    - Spawn bullet.
    - Decrease `AmmoCount` by 1.

### 4. Place Ammo in the World

- Drag instances of `BP_AmmoPickup` into your level from the Content Browser.
- Adjust position, mesh, and pickup range as needed.

## Output

<img width="1918" height="856" alt="op1" src="https://github.com/user-attachments/assets/7d93b72f-5731-44d1-b1af-70688e00f9b6" />

<img width="1335" height="839" alt="op2" src="https://github.com/user-attachments/assets/8de0a10f-4329-4121-8d67-d27fe9d489ba" />

<img width="1919" height="1013" alt="op3" src="https://github.com/user-attachments/assets/385a295e-e303-4930-afab-a167b64df978" />

<img width="1134" height="765" alt="op4" src="https://github.com/user-attachments/assets/9fc2e68c-0dde-4509-a5d6-57f4dd7d986b" />

##  Result

- The player starts with a limited number of bullets.
- When the player overlaps with an ammo pickup:
  - The ammo is collected.
  - The player's `AmmoCount` increases.
- The player can now fire additional bullets based on the updated ammo count.

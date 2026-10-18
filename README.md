# ADA Run

**▶ Play now: https://hmaharramli55-dot.github.io/ADA-Run/**

An endless runner game in the style of Subway Surfers, set on the ADA University campus in Baku.

You play an ADA student running down a straight campus boulevard to escape a giant **F** (Academic Fail). Dodge exam barriers, unread textbooks, laptop desks and the distractions that make students fail, like TikTok, Instagram and parties. Collect books, answer quizzes from your own major and reach **100 points** to graduate.

![Title screen](screenshots/title.png)
![Gameplay](screenshots/gameplay.png)

<p>
  <img src="screenshots/character-phone.png" width="240" alt="Character creator on a phone">
  <img src="screenshots/gameplay-phone.png" width="240" alt="Gameplay with a quiz gate on a phone">
</p>

## How to play

Open the link above, or open `index.html` in any modern browser on a computer or phone. Nothing needs to be installed.

| Action | Keyboard | Phone |
| --- | --- | --- |
| Change lane | ← → or A D | Swipe left / right |
| Jump | ↑, W or Space | Swipe up |
| Slide | ↓, S or Shift | Swipe down |
| Hoverboard | E | Double-tap |
| Pause | P or Esc | Pause button |

## Features

- **Student sign-in.** Enter your name, student ID or ADA email, major and academic year. There is no password: your profile, best score and progress are saved in your browser, and several students can share one device.
- **Quizzes for your major and year.** All 30 programmes from the ADA academic catalogue are included. A Year 3 student only gets Year 2 and Year 3 topics, never Year 4. Questions come in three formats:
  - checkpoint multiple choice
  - quick true/false
  - quiz gates, which you answer by running through the lane with the right answer

  Quizzes never show raw course codes.
- **Score and learning.** The HUD shows your score and how many topics you have learned (each right answer is one). Every run ends with a list of what you learned, and your profile keeps the total.
- **See other players and their scores.** Students playing at the same time appear on your track as see-through runners with their name and live score above their head, and a "Live race" box ranks everyone in the race. The start screen shows the top 3 students and your rank, the "All ADA" leaderboard lists everyone's best score, and every run ends with your ADA rank. Student IDs are never published.
- **Share.** The Share and Challenge friends buttons copy an invite message with the game link.
- **Real ADA campus.** The 3D world is built from photos and the real names of ADA buildings: Buildings A, B, D, E and L, the Library, the Student Center, the Caravanserai (School of Business), ADA Gardens and ADA School.
- **Academic obstacles.** The track has these obstacles:
  - exam barriers and piles of unread textbooks
  - laptop desks and giant backpacks
  - missed-deadline hurdles and procrastination banners
  - a swinging exam clock and a sliding pop quiz
- **Fair by design.** Obstacle patterns never block all three lanes with something you can't jump or slide past, and gaps grow as you speed up.
- **Your student.** Clearly different boy and girl models, with skin tone, hair, clothes and accessories.
- **Scoring.** One mode for everyone: 0.10 points per book, combos (x2, x3, x5) and pomegranate books worth 1.00. Power-ups include a hoverboard, jetpack, coffee magnet, focus mode and super-jump shoes. You get a transcript with GPA and, at 100 points, a diploma.
- **Look.** Caspian Blue, White and Pomegranate visual identity.

## Graphics

Version 7 reworks how the game looks, with the same gameplay and controls:

- **Light and shadows.** A warm afternoon sun casts real soft shadows from the runner, the F, obstacles, trees, lamps and buildings. Soft ambient occlusion darkens the ground where buildings, trees and benches stand.
- **Colour grading.** Bright areas roll off gently instead of burning out to white, with a little more contrast, cool shadows and warm highlights.
- **Sky and distance.** A sky dome with a hazy horizon, painted clouds, and the Baku skyline on the horizon with the TV tower and the three Flame Towers straight down the boulevard. Distant campus fades into soft haze.
- **Materials.** The runner, the F, books, power-ups and obstacles use physically based materials that pick up light from the sky. The F is a single bevelled letter, books have covers, spines and page edges, and trees have faceted low-poly crowns. The paving and lawn have new high-resolution textures.
- **Effects.** Footstep dust, landing dust rings, sparks and dust when sliding, smoke on crashes, a smoke trail from the jetpack and a dark trail behind the F.
- **Animation.** Shoulders counter-rotate against the hips, the body sways and leans forward more as the pace picks up, elbows pump and the head stays steady.
- **Menus and HUD.** Frosted-glass panels, softer buttons, glowing progress bars, a light vignette and smooth screen transitions.

The game picks a quality level for your device and steps down by itself if the frame rate drops. To choose one yourself, add `?gfx=2` (full shadows), `?gfx=1` (phone level) or `?gfx=0` (no shadows, fastest) to the link, for example https://hmaharramli55-dot.github.io/ADA-Run/?gfx=2.

## Online play and accounts

Online play runs on the game's own [Firebase](https://firebase.google.com/) project. Once it is connected:

- Every player creates a free account (name, student ID or ADA email, password, major and year) and can log in on any phone or computer.
- Everyone who is logged in sees each other's best scores on the "All ADA" leaderboard.
- Players who are running at the same time see each other on the track, with their name and live score above their head.

Student IDs are never shown to anyone, and each player can only change their own scores and progress.

To connect a Firebase project:

1. In the [Firebase console](https://console.firebase.google.com), create a project.
2. Under **Authentication**, turn on **Email/Password**.
3. Under **Realtime Database**, create a database in locked mode. In the **Rules** tab, paste the contents of [`firebase-rules.json`](firebase-rules.json), then publish.
4. Register a web app under **Project settings > Your apps**, and paste its `firebaseConfig` values into `FIREBASE` near the top of the script in `index.html`. Only `apiKey` and either `databaseURL` or `projectId` are needed:

```js
const FIREBASE = { apiKey: 'AIza...', authDomain: 'ada-run-xxxxx.firebaseapp.com', projectId: 'ada-run-xxxxx', databaseURL: 'https://ada-run-xxxxx-default-rtdb.europe-west1.firebasedatabase.app' };
```

Until this is set, the game keeps scores on each device, and online play only works on the game's claude.ai link.

## Built with

- HTML5, CSS and JavaScript in a single file
- [Three.js](https://threejs.org/) r128 (WebGL), loaded from a CDN
- Web Audio API for sound effects and music
- Firebase Authentication and Realtime Database (REST and live streaming) for accounts and online play

## Author

Huseyn Maharramli, ADA University

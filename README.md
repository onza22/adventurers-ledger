# Adventurer's Ledger

A player's campaign journal: NPCs, items and quests per character, a page-flipping "book" view by day, photos, press-and-hold reordering. Sign in with Google; data lives in your Firebase project.

## Hosting
Static site. Everything is in `index.html`; publish this folder with GitHub Pages (Settings -> Pages -> Deploy from branch -> main / root).

## Firebase setup (once)
1. Authentication -> Sign-in method -> Google -> Enable.
2. Authentication -> Settings -> Authorized domains -> add your GitHub Pages domain (e.g. `onza22.github.io`).
3. Firestore Database -> Rules -> paste `firestore.rules` -> Publish.
4. Firestore Database -> Data -> Start collection `allowed_users` -> document id = your Google email (lowercase), add a field `added: true`. Repeat for each party member.

## Campaigns (shared journals)
Characters tab -> Campaigns -> Create. Share the 6-letter code; party members enter it under "Join with a code",
then pick the campaign on their character. Everyone in the campaign shares one journal and book.
The creator can remove members or delete the campaign; members can leave.

## Backups
Characters tab -> Export backup downloads a JSON of everything.

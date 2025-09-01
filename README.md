# shell-game-monad
Medieval Tavern Shell Game

A browser-based Monad shell game where players can bet MON tokens on one of three shells. Features include wallet connection, funding the contract, playing the game, and a live recent plays log.

Table of Contents

Prerequisites

Files

Setup & Running Locally

Hosting Online

How to Play

Code Structure

Troubleshooting

Quick Start

Prerequisites

MetaMask or another Ethereum-compatible browser wallet.

Node.js or Python 3.x for local testing (optional, but recommended).

Ether/Mon Test Tokens for testing on a local/testnet or your chosen network.

Files

index.html — Main webpage with the game interface.

Images — Shells and background, loaded via URLs.

Smart Contract — Solidity contract deployed to your network.

Setup & Running Locally

See Quick Start
 for the easiest way.

Option 1: Using Python

Open a terminal in the folder containing index.html.

Run the server:

python -m http.server 8000


Open your browser at:

http://localhost:8000

Option 2: Using Node.js

Install serve globally:

npm install -g serve


Launch the server in your project folder:

serve .


Open the URL printed in the console (usually http://localhost:5000).

Hosting Online

You can host your game publicly using:

GitHub Pages

Push your folder to a GitHub repository.

Go to Settings → Pages → Source → Main branch.

Open your game at https://username.github.io/repo-name/.

Netlify / Vercel / Render

Drag-and-drop your folder or connect a GitHub repo.

The platform gives you a live HTTPS URL.

How to Play

Connect Wallet — Click the “Connect Wallet” button and authorize MetaMask.

Set Bet — Enter the amount of MON tokens you want to wager.

Click a Shell — One of three shells on the table is your guess.

Shells animate with a shake when clicked.

Status updates with “Shuffling shells...” during transaction.

Wait for Result — After the transaction confirms:

“You won” or “You lost” message appears.

Recent plays log updates automatically.

Fund Contract (optional) — Click the “Fund Contract” button to add MON to the game’s bankroll.

Code Structure
HTML

div.tavern — Main container.

div.shells — Contains the three clickable shells.

input#bet — Bet amount in MON.

div#status — Shows wallet connection, transaction, and game messages.

ul#plays — Recent plays log.

JavaScript

ethers.js — Connects to Ethereum, sends transactions, listens to events.

Contract functions used:

play(guess) — Play a round.

fund() — Fund contract bankroll.

Event listeners:

Played — Updates UI when a play is completed.

Funded — Logs funding events to console.

CSS

Background: Medieval tavern theme.

Shell animations: .shaking triggers @keyframes shake.

Scoreboard: Shows recent plays, scrollable if long.

Troubleshooting

UI hangs on “Shuffling shells”:

Make sure MetaMask confirms the transaction.

Reload the page if the event listener fails to update.

Transaction fails / CALL_EXCEPTION:

Contract may be out of funds. Fund it before betting higher amounts.

Ensure sufficient balance in your wallet.

Wallet not connecting:

Install MetaMask or refresh the browser.

Ensure your network matches the deployed contract network.

Local host errors:

Python 2.x: python -m SimpleHTTPServer 8000

Python 3.x: python -m http.server 8000

Quick Start (One Command)
Using Python 3.x
# Navigate to your project folder
cd path/to/your/project

# Launch the game locally
python -m http.server 8000


Open your browser at:

http://localhost:8000

Using Node.js (Optional)
# Install 'serve' globally
npm install -g serve

# Navigate to your project folder
cd path/to/your/project

# Launch server
serve .


Open the URL printed in the terminal (usually http://localhost:5000).

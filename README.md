# 🎰 Multi-Armed Bandit Demo

An interactive web-based demonstration of the Multi-Armed Bandit (MAB) problem, implemented as an engaging slot machine game. This educational tool helps users understand exploration vs. exploitation trade-offs in decision-making under uncertainty.

## 🎯 Overview

The Multi-Armed Bandit problem is a classic reinforcement learning scenario where a player must choose between multiple options (arms/machines), each with unknown reward probabilities. The goal is to maximize cumulative rewards while balancing exploration (trying different options) and exploitation (choosing the best-known option).

## ✨ Features

### 🎮 Interactive Gameplay
- **Two Slot Machines**: Choose between Machine A and Machine B
- **Animated Reels**: Smooth spinning animations with emoji symbols (🍒, 🍋, 🍊, 🍉, ⭐, 💎, 7️⃣)
- **Fast Gameplay**: 300ms spin duration for quick decision-making
- **Visual Feedback**: Full-screen flash effects
  - 🟢 Green flash for wins
  - 🔴 Red flash for losses

### 📊 Real-Time Statistics
Each machine displays:
- **Pulls (pull count)**: Number of times the machine has been pulled
- **Wins (cumulative reward)**: Total rewards earned from this machine
- **Sample Mean Formula**: Live calculation showing the complete formula
  - Example: `(1 + 0 + 1 + 0) / 4 = 0.50`
  - Updates with each pull to show the reward history

### ⚙️ Flexible Configuration

#### Random Probability Mode (Default)
- Each machine gets a win rate randomly sampled from a **uniform distribution (0-100%)**
- Machine A and Machine B probabilities are independently sampled
- Creates unique scenarios for each game session
- Ideal for exploring MAB behavior across diverse probability distributions

#### Custom Probability Mode
- Set any two probabilities (0-100%)
- **Randomize Assignment Options**:
  - **Yes**: Randomly allocate the two probabilities to machines
  - **No**: Direct assignment (Probability 1 → Machine A, Probability 2 → Machine B)
- Ideal for testing specific scenarios or educational demonstrations

### 📱 Responsive Design
- **Desktop**: Full-featured layout with side-by-side machines
- **Tablet (≤768px)**: Optimized spacing, machines remain horizontal
- **Mobile (≤600px)**: Compact layout, still horizontal
- **Very Small (≤400px)**: Vertical stack for tiny screens

### 📈 End-Game Analytics
When all pulls are used, the game reveals:
- Total reward earned
- Overall success rate percentage
- **Efficiency score**: Performance compared to theoretical maximum (always choosing the better machine)
- **True probabilities**: The actual win rates of both machines revealed

## 🚀 Getting Started

### Prerequisites
- A modern web browser (Chrome, Firefox, Safari, Edge)
- No installation or server required!

### Running the Demo
1. Download or clone this repository
2. Open `index.html` in your web browser
3. Configure your game settings
4. Click "Start Game" and begin playing!

### URL Parameters for Direct Configuration

You can configure the game by passing URL parameters:

#### For Main Game (`game.html`)
```
game.html?totalPulls=50&randomProb=no&prob1=30&prob2=70&randomAssign=no
```

**Available Parameters:**
- `totalPulls`: Number of pulls (default: 20)
- `randomProb`: Use random probabilities - `yes` or `no` (default: yes)
- `prob1`: First probability percentage (0-100)
- `prob2`: Second probability percentage (0-100)
- `randomAssign`: Randomly assign probabilities to machines - `yes` or `no` (default: no)

#### For Policy Comparison (`policy_comparison.html`)
```
policy_comparison.html?totalPulls=100&randomProb=yes&etcExplore=10&numSimulations=500
```

**Available Parameters:**
- `totalPulls`: Number of pulls per simulation (default: 20)
- `randomProb`: Use random probabilities - `yes` or `no` (default: yes)
- `prob1`: First probability percentage (0-100, if randomProb=no)
- `prob2`: Second probability percentage (0-100, if randomProb=no)
- `randomAssign`: Randomly assign probabilities - `yes` or `no` (default: no)
- `etcExplore`: Initial explores per arm for ETC algorithm (default: 5)
- `numSimulations`: Number of simulations to run (default: 100)

**Example URLs:**
```
# Game with custom probabilities
game.html?totalPulls=50&randomProb=no&prob1=40&prob2=80&randomAssign=no

# Policy comparison with 1000 simulations and 10 explores per arm
policy_comparison.html?totalPulls=20&randomProb=yes&etcExplore=10&numSimulations=1000
```

## 🎲 How to Play

1. **Configure the Game**
   - Set the total number of pulls (1-1000)
   - Choose Random Probability (Yes/No)
   - If No, customize probabilities and assignment

2. **Make Your Decisions**
   - Click on a slot machine or the "Pull!" button
   - Watch the reels spin and reveal your result
   - Observe the sample mean formula update in real-time

3. **Optimize Your Strategy**
   - Track which machine performs better
   - Balance exploration (trying both) vs. exploitation (choosing the better one)
   - Maximize your cumulative reward

4. **Review Results**
   - See your final efficiency score
   - Compare your performance to the theoretical maximum
   - Learn from the revealed probabilities

## 🧠 Educational Value

This demo is perfect for:
- **Students**: Learning reinforcement learning concepts
- **Educators**: Teaching decision-making under uncertainty
- **Researchers**: Demonstrating MAB algorithms
- **Data Scientists**: Visualizing exploration-exploitation trade-offs

## 🛠️ Technical Details

### Technology Stack
- **Pure HTML/CSS/JavaScript**: No dependencies or frameworks
- **Responsive Design**: CSS media queries for all screen sizes
- **Smooth Animations**: CSS transitions and keyframe animations
- **Modern ES6+**: Clean, maintainable JavaScript code

### Key Algorithms
- **Bernoulli Trials**: Each pull is a random trial with the machine's win probability
- **Sample Mean Calculation**: Running average of rewards (wins/pulls)
- **Visual Formula Display**: Real-time rendering of the calculation process

### Performance
- **Fast Execution**: 300ms per pull (100ms per reel)
- **Lightweight**: Single HTML file, no external dependencies
- **Optimized**: Efficient DOM updates and minimal reflows

## 📊 MAB Terminology

The demo uses standard Multi-Armed Bandit terminology:
- **Pull Count**: Number of times an arm (machine) has been selected
- **Cumulative Reward**: Total rewards obtained from an arm
- **Sample Mean**: Estimated reward probability (empirical average)
- **Exploration**: Trying different arms to learn their probabilities
- **Exploitation**: Choosing the arm with the highest known reward
- **Regret**: The difference between actual rewards and theoretical maximum

## 🎨 Customization

The code is easy to customize:
- **Colors**: Modify CSS variables for themes
- **Symbols**: Change the `symbols` array in JavaScript
- **Probabilities**: Adjust default values
- **Spin Speed**: Modify `spinDurations` array
- **Flash Effects**: Customize `.flash-green` and `.flash-red` styles

## 📝 License

This project is open source. See the LICENSE file for details.

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

## 📧 Contact

For questions or suggestions, please open an issue in the repository.

---

**Happy Exploring! 🎰✨**
A Demo Game of Multi-Armed Bandits

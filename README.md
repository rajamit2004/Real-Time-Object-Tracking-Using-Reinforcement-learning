
Project Description
This project combines real-time object detection (using YOLOv5) with Reinforcement Learning (Q-Learning) to autonomously decide tracking actions: Track, Observe, Ignore, or Search. The system learns from detection confidence scores to optimize decisions over time.

Key Features
Real-Time Detection: Uses YOLOv5 to identify objects in a webcam feed.

Reinforcement Learning: Implements a Q-Learning agent with:

4 possible actions (Track/Observe/Ignore/Search)

Custom reward function (rewards effective decisions, penalizes mistakes)

State representation based on detection confidence

Adaptive Decision-Making: Updates actions every 2 seconds for balanced learning.

Persistent Learning: Saves the Q-table (q_table.pkl) for future sessions.

How It Works
Detection Phase: YOLOv5 processes each frame to detect objects and their confidence scores.

State Extraction: The system converts detection confidence into discrete states (e.g., High: >0.7, Medium: 0.4-0.7, Low: <0.4).

Action Selection: The Q-Learning agent either:

Explores (random action) to discover new strategies.

Exploits (best-known action) based on the Q-table.

Reward & Learning: The agent receives rewards/penalties and updates the Q-table to improve future decisions.

Setup Instructions
Clone the Repository: Download the project files to your local machine.

Install Dependencies: Install Python packages (PyTorch, OpenCV, etc.) listed in requirements.txt.

Run the Script: Execute main.py to start the webcam feed with real-time decisions.

Interact: Press Q to quit. The Q-table automatically saves on exit.

Customization Options
Adjust Learning Parameters: Tweak alpha (learning rate), gamma (discount factor), or epsilon (exploration rate).

Modify Rewards: Change reward values in get_reward() to prioritize specific actions.

Extend States/Actions: Add more states (e.g., object class) or actions (e.g., Zoom).

Expected Output
Visual Feedback: The webcam display shows detected objects and the current action (e.g., "Action: Track").

Console Logs: Prints Q-table updates and detection confidence scores.

Saved Q-table: The q_table.pkl file retains learned policies between sessions.

Use Cases
Surveillance Systems: Automatically track suspicious objects.

Robotics: Guide robots to follow/interact with objects.

Behavioral Research: Study RL decision-making in dynamic environments.

Future Improvements
Multi-Object Tracking: Expand to handle multiple objects simultaneously.

Deep Q-Learning: Replace the Q-table with a neural network for complex states.

ROS Integration: Deploy on robots using the Robot Operating System.

Contributing
Open to contributions! Report bugs via Issues or propose enhancements via Pull Requests.

License
This project is licensed under MIT License – free for academic and commercial use.


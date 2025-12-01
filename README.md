# LeIsaac-Sim2Real 🚀

EN | [JP](./docs/docs/docs/README_JP.md)

This repository is a fork of [LeIsaac](https://github.com/LightwheelAI/leisaac.git), customized for Sim2Real research using the SO-101 arm.

https://github.com/user-attachments/assets/763acf27-d9a9-4163-8651-3ba0a6a185d7

This repository provides teleoperation functionality in [IsaacLab](https://isaac-sim.github.io/IsaacLab/main/index.html) using the SO101Leader ([LeRobot](https://github.com/huggingface/lerobot)), including data collection, data conversion, and subsequent policy training.

- 🤖 We use SO101Follower as the robot (and other related robot) in IsaacLab and provide relevant teleoperation method.
- 🔄 We offer scripts to convert data from HDF5 format to the LeRobot Dataset.
- 🧠 We utilize simulation-collected data to fine-tune [GR00T N1.5](https://github.com/NVIDIA/Isaac-GR00T) and deploy it on real hardware. And more policies will be supported.

## Getting Started 📚

Please refer to our [documentation](https://lightwheelai.github.io/leisaac/) to learn how to use this repository. Follow these links to learn more about:

- [Installation and Setup](https://lightwheelai.github.io/leisaac/docs/getting_started/installation)
- [Extra Features](https://lightwheelai.github.io/leisaac/docs/features)
- [Policy Inference](https://lightwheelai.github.io/leisaac/docs/getting_started/policy_support)
- [Available Robots](https://lightwheelai.github.io/leisaac/resources/available_robots), [Environments](https://lightwheelai.github.io/leisaac/resources/available_env) and [Policy](https://lightwheelai.github.io/leisaac/resources/available_policy)

> [!TIP]
>
> For more features and updates, please refer to the [News](https://lightwheelai.github.io/leisaac/#news) section on our website!

## Acknowledgements 🙏

This project is based on the excellent work of Lightwheel AI's LeIsaac. We also acknowledge IsaacLab and LeRobot.

---

**Let's build the future of robotics together! 🤝**

---

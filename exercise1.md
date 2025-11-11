11.1

A team of 6 is developing an indie game with C++.

In this scenario, the team will use **clangd** for both linting and formatting, as it is a popular and free option. This approach includes both **clang-tidy** for live code checking based on a configuration file and **clang-format** for formatting the code. This setup is simple and integrates well into their development environment with the help of the **clangd** VSCode extension.

**Clang-Tidy** is also integrated into their pull request system, where Github Actions automatically checks all submitted code
based on the same configuration, just in case a developer forgets to run **clang-tidy** before commiting a pull request. Building their code is integrated into Gitlab Actions with **cmake**. Testing is one of the most difficult aspects of game development, which is why the team has opted to use both **CppUnit** testing and custom tooling to run specific game scenarios. **CppUnit** testing is reserved for evaluating basic critical functionality, whereas the custom tooling is used for more elaborate testing, such as testing with automated screenshots whether the graphics renderer of the game is able to handle a variety of scenarios with different types of hardware.

There exists several viable options for CI in this scenario, including **BitBucket**, **TeamCity** and building custom tooling. The team is quite small so custom tooling should only be used as a last resort because developing those tools would take away valuable development time from the game.

Deciding between a self-hosted or cloud-based CI environment depends on several factors. Cloud-based systems minimize setup time, infrastructure maintenance, and scaling concerns, making them ideal for small teams. However, self-hosted CI offers full control over the build environment, better security for proprietary code, and compatibility with specialized hardware like console dev kits. For most small indie teams, a cloud-based solution provides the best balance of flexibility, cost, and simplicity.

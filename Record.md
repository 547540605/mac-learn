- # 问题:我在Mac上vs code出现报错找不到 .NET Core SDK 的位置
  ：Error running dotnet --info: Error: Command failed: dotnet --info
  /bin/sh: dotnet: command not found
  /bin/sh: dotnet: command not found 。将不会启用 .NET Core 调试。请确保已安装 .NET Core SDK 且该 SDK 位于路径上。

- # 回答:
  
  这个错误提示表明你的系统中没有安装 .NET Core SDK，或者安装的 .NET Core SDK 没有正确添加到系统的 PATH 环境变量中。以下是解决这个问题的步骤：
  
  **1. 安装 .NET Core SDK**
  
  首先，你需要下载并安装 .NET Core SDK。你可以从 [.NET 官方网站](https://dotnet.microsoft.com/download) 下载适用于 macOS 的 .NET Core SDK。
  
  **2. 验证安装**
  
  安装完成后，打开终端并运行以下命令来验证 .NET Core SDK 是否安装成功：
  
  ```sh
  dotnet --info
  ```
  
  如果安装成功，你应该会看到一些关于 .NET Core SDK 的详细信息。
  
  **3. 添加 .NET Core SDK 到 PATH**
  
  如果 `dotnet --info` 命令仍然提示 `command not found`，可能是因为 .NET Core SDK 没有正确添加到 PATH 环境变量中。你可以手动添加它。
  
  通常，.NET Core SDK 安装在 `/usr/local/share/dotnet` 目录下。你可以将这个路径添加到 PATH 环境变量中。
  
  打开终端并编辑你的 shell 配置文件（例如 `.bash_profile` 或 `.zshrc`）：
  
  ```sh
  nano ~/.bash_profile  # 如果你使用的是 Bash
  # 或者
  nano ~/.zshrc         # 如果你使用的是 Zsh
  ```
  
  在文件的末尾添加以下行：
  
  ```sh
  export PATH=$PATH:/usr/local/share/dotnet
  ```
  
  保存并退出编辑器（在 nano 中按 `Ctrl+X`，然后按 `Y` 确认保存，最后按 `Enter`）。
  
  然后，重新加载你的 shell 配置文件：
  
  ```sh
  source ~/.bash_profile  # 如果你使用的是 Bash
  # 或者
  source ~/.zshrc         # 如果你使用的是 Zsh
  ```
  
  **4. 重启 VS Code**
  
  完成上述步骤后，重启 Visual Studio Code，然后再次尝试运行 .NET Core 调试，应该不会再出现找不到 .NET Core SDK 的错误。
  
  **5. 检查 VS Code 的 C# 扩展**
  
  确保你已经安装了 C# 扩展。你可以在 VS Code 的扩展市场中搜索 "C#" 并安装它。
  
  通过这些步骤，你应该能够解决 `dotnet: command not found` 的问题，并在 VS Code 中成功启用 .NET Core 调试。

# Flake.GPT  

Flake.GPT is a tool designed to automate the wrapping and management of Nix projects using advanced AI capabilities. By leveraging various powerful libraries and frameworks, Flake.GPT ensures consistent, reproducible environments while simplifying configuration management through natural language processing.  

## Why Flake.GPT?  

Managing Nix projects and configurations can be complex and time-consuming, often involving manual setup and maintenance. Flake.GPT addresses these challenges by automating the creation of wrapper scripts, handling environment configurations, and utilizing AI to streamline processes. This project aims to replicate and extend the functionality of the Divnix Hive framework with enhanced flexibility and ease of use.  

## Key Dependencies  

### Automation/Scripting

#### [GPTscript-ai](https://github.com/gptscript-ai/gptscript)  
- **Description**: Replaces traditional `.nix` files with `.gpt` files, allowing Nix code logic to be expressed as natural language prompts.  
- **Usage**: Simplifies the management of Nix projects by enabling natural language prompts to replicate and automate Nix code logic.  

### (Virtual) Environment Management

#### [Wrapper-Manager](https://github.com/viperML/wrapper-manager)  
- **Description**: A Nix library that simplifies the configuration of applications by creating wrapper scripts without modifying files in the home directory.  
- **Usage**: Utilized to create and manage wrapper scripts, ensuring that all necessary environment variables and dependencies are set correctly, reducing manual configuration efforts.  

#### [Wrappix](https://github.com/zackattackz/wrappix)  
- **Description**: Extends Nix functionality using a modular system to create extensible wrapper scripts for various applications.  
- **Usage**: Enhances Nix's capabilities by allowing custom configurations and managing dependencies efficiently through a modular approach.  

### Prompt/Structured Output

#### [Guidance](https://github.com/guidance-ai/guidance)  
- **Description**: Provides high-level structured outputs using large language models (LLMs).  
- **Usage**: Ensures the generation of coherent and structured outputs, facilitating better management and understanding of Nix configurations.  

#### [AICI](https://www.microsoft.com/en-us/research/project/aici/)  
- **Description**: Offers granular control over LLM outputs, including tokenization and fine-grained adjustments.  
- **Usage**: Allows precise control over the AI's outputs, ensuring accurate and reliable generation of configuration scripts and other outputs.

- #### [Instructor](https://github.com/jxnl/instructor)
- **Description**: A tool for program synthesis that uses natural language to describe programming tasks, generating code snippets based on descriptions.
- **Usage**: Enhances the capability of Flake.GPT to generate and manage Nix configurations by translating natural language descriptions into executable code.

### Continuous ...Inference(?)
- Algorithms, frakeworks and other external libraries that extend the functionality and useability of agents post-prompt to task execution. some examples would be -> self-instruct, self-discovery, Chain-of-Thought reasoning

### Multi-agent Frameworks
- TBC

### Serving/API/Routing
- TBC

## Project Structure  

```shell

Flake.GPT
├── flake.nix                # Nix flake configuration file
├── scripts/
│   ├── init_env.py          # Initializes the Nix environment
│   ├── wrap_files.py        # Handles the wrapping of files and directories
│   └── main.py              # Main script integrating all functionalities
├── configs/
│   ├── example_config.nix   # Example Nix configuration
│   └── custom_wrappers.nix  # Custom wrapper definitions
├── README.md                # Project documentation
└── .gitignore               # Git ignore file  

```  

### Example Usage  

1. **Initialize Nix Environment**:  
```nix  
   import gptscript  

   def init_nix_env(project_path):
       gptscript.run("nix-shell", cwd=project_path)
```

2. **Traverse and Wrap Files**:
```go-lang
   import gptscript
   import os

   def traverse_and_wrap(directory):
       for root, dirs, files in os.walk(directory):
           for file in files:
               file_path = os.path.join(root, file)
               wrap_file(file_path)

   def wrap_file(file_path):
       # Example wrapping logic
       gptscript.run(f"echo 'Wrapping {file_path}'")
```

3. **Integrate with Wrapper-Manager**:
```mix
   (wrapper-manager.lib.build {
     inherit pkgs;
     modules = [{
       wrappers.myapp = {
         basePackage = pkgs.myapp;
         flags = ["--config" "./config.file"];
         env.MYAPP_CONFIG.value = "../myapp.toml";
       };
     }];
   })
```  
4. **isolate or extend with just**:

```shell
# create ~/bin
mkdir -p ~/bin

# download and extract just to ~/bin/just
curl --proto '=https' --tlsv1.2 -sSf https://just.systems/install.sh | bash -s -- --to ~/bin

# add `~/bin` to the paths that your shell searches for executables
# this line should be added to your shells initialization file,
# e.g. `~/.bashrc` or `~/.zshrc`
export PATH="$PATH:$HOME/bin"

# just should now be executable
just --help
```  

## Getting Started  

1. **Clone the Repository**:  

   `git clone https://github.com/your-repo/Flake.GPT.git`  


2. **Run the Main Script**:  

   `nix run .#main`  


3. **Customize Wrappers**:  
   Edit the `custom_wrappers.nix` file to define custom wrappers and configurations as needed.  

## Contributing  

Contributions are welcome! Please open an issue or submit a pull request if you have suggestions for improvements or new features.  

## License  

This project is licensed under the MIT License. See the LICENSE file for details.

# MCP
AWS MCP Servers are specialized components that seamlessly integrate AWS best practices into your development workflow, enabling intelligent infrastructure automation and design guidance at every step.

Amazon Q CLI and with MCP Server Support, it can be used to do some amazing DevOps Related tasks like
- Architectural Diagrams
- Terraform Code
- Kubernetes resources

Installing Amazon Q CLI, you can use it for free by creating a BuilderID <a href="https://community.aws/builderid?trk=529c4ce9-0395-4c42-915a-d70bf060ef3c&sc_channel=el" target="_blank">here</a> (needed for Free Amazon Q CLI usage)

### Steps to install on Linux (Ubuntu)
1. Update Your machine First
```sh
  $ sudo apt-get update
 ```
2. Install Libfuse2
```sh
sudo apt install libfuse2
```
3. Install the deb file for Amazon Q
```sh
curl --proto '=https' --tlsv1.2 -sSf https://desktop-release.q.us-east-1.amazonaws.com/latest/amazon-q.deb -o amazon-q.deb
```
![aws_q_5](https://github.com/user-attachments/assets/bfd389be-1fda-4000-b88d-c4b58fbba389)

4. Install Amazon Q debian file
```sh
sudo apt install -y ./amazon-q.deb
```
5. AND final Login to q
```sh
q login
```
6. Authenticate
You have 2 options to sign-in and this blog explores both the authentication methods :
1. with <a href="https://docs.aws.amazon.com/toolkit-for-visual-studio/latest/user-guide/builder-id.html" target="_blank">Builder ID</a> for Individual users with Free Tier
2. with <a href="https://docs.aws.amazon.com/toolkit-for-visual-studio/latest/user-guide/sso-credentials.html" target="_blank">AWS IAM Identity Center</a> for Professional users with Pro Tier

But We are using free tier for this blog

![aws_q_6](https://github.com/user-attachments/assets/6b0882f9-9168-4578-bd58-e2903ccf9070)

8. Press ENTER and You will get one url for authentication
9. once you will get the url copy that url paste in google search bar and you will get AWS Builder authentication page once click Confirm and continue
    
![aws_q_7](https://github.com/user-attachments/assets/413e0c7d-a228-4799-a168-7d7067a14e3b)

![aws_q_1](https://github.com/user-attachments/assets/07cd8866-1443-4537-b6d6-0e5330dda7d5)

9.That's it, you're all set to take your DevOps & Cloud skills to the next level with AI.

#### Write a simple prompt 
Create a simple Web application using html, css, javascript
Or Create a multi-line prompt with /editor That opens a Vim editor
Add your prompt and press ```esc``` + ```:wq``` to execute the prompt

### Let's Do cool project using Amazon Q + MCP servers

MCP Servers can be setup locally with ```npx``` , ```uvx```, ```docker```
But In this blog i used ```uvx```

### What is ```uvx```
The uvx command is used with Amazon Q CLI to interact with Universal Virtual eXecutor (UVX) — a feature that allows Amazon Q to execute tasks, run tools, and interact with your local dev environment based on AI-generated suggestions.

```uvx``` stands for Universal Virtual eXecutor, and it's a command-line interface used to:
- Run AI-generated commands
- Launch development tools
- Execute infrastructure tasks
- Integrate with MCP servers for intelligent DevOps workflows

### Install uvx Linux / WSL
```sh
sudo snap install astral-uv --classic
```
Now create a file called ```mcp.json``` in ```cd ./aws/amazonq/```
Add below MCP Server code into mcp.json file

```sh
{

        "mcpServers" : {

                "awslabs.cdk-mcp-server": {
                        "command": "uvx",
                        "args": ["awslabs.cdk-mcp-server@latest"], # this Amazon Q CLI can launch using uvx, with specific arguments and environment variables for runtime behavior
                        "env": {
                        "FASTMCP_LOG_LEVEL": "ERROR"
                        }
                },
                "awslabs.aws-diagram-mcp-server": {
                        "command": "uvx",
                        "args": ["awslabs.aws-diagram-mcp-server"], #Launches an MCP server that enables Amazon Q CLI to generate AWS architecture diagrams from natural language prompts.
                        "env": {
                                "FASTMCP_LOG_LEVEL": "ERROR"
                        },
                        "autoApprove": [],
                        "disabled": false
                },
                "kubernetes-mcp-server": {
                        "command": "uvx",
                        "args":["kubernetes-mcp-server@latest"], # Starts an MCP server that helps Amazon Q CLI generate Kubernetes manifests (like deployments, services, HPAs) using AI-driven prompts.
                        "env": {
                                "FASTMCP_LOG_LEVEL": "ERROR"
                        }
                }

        }
}
```

Now Run ```q``` again

![aws_q_3](https://github.com/user-attachments/assets/0f949ad0-d413-48c0-89dc-3a65080ae3f6)

![aws_q_8](https://github.com/user-attachments/assets/8ce2a542-6634-45fd-a122-56d2d5f617c3)


Amazon Q CLI configured with MCP Server

Write prompt for whatever architecture diagram and you will get output like this

![ecommerce-architecture](https://github.com/user-attachments/assets/623e3a99-0371-4e80-a273-6e9441e76f4b)

## Basic Commands for amazon q
1. Login In q
```sh
q login
```
2. Enter into q
```sh
q
```
3. Exit from q
```sh
/quit
```
4. MCP server are loaded or not check
```sh
/tools
```
![aws_q_9](https://github.com/user-attachments/assets/c2dbabbf-6f38-487f-82cd-a328454593a6)

5. Clear History
```sh
!clear
```
6. If you want to run any command in q
```sh
!uvx kubernetes-mcp-server@latest
```
***************************************************************************************************************
Happy Learning ❤️ </br>
Feel free to Contact me if you have any query or issue related Amazon Q or MCP Servers Setup</br>
Vinayak Z.</br>
Mobile Number :- 7848849869 </br>
Email Id :- vinoo160496@gmail.com </br>
DevOps Engineer  

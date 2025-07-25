# How to create agent flows with a local Flowise environment

## Requirements

### Homebrew (MacOS)

Paste that in a macOS Terminal or Linux shell prompt:<br>
`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`
<br>
For more informations visit [Homebrew](https://brew.sh)

### Chocolatey (Windows)

Paste that in a administrative shell:<br>
`Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))`
<br>
For more informations visit [Chocolatey](https://chocolatey.org/install)

### Podman Desktop (Docker Desktop)

Make sure that you have installed Docker or Podman.<br> If not use one of the following commands:<br><br>
**For Windows:**<br>
`choco install podman-desktop`<br>
`choco install docker-desktop`
<br><br>
**For MacOS:**<br>
`brew install --cask podman-desktop`<br>
`brew install --cask docker-desktop`<br><br>
**NOTE:** If you don´t want to use the desktop version of docker or podman just make sure that you have installed docker or podman. That should be fine.

---

## Pulling necessary container

Next Step is to pull the necessary container. You can use the `docker-compose.yml` file from that project. It will pull the following container:

| Container | Description                                                                                                                             |
| --------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| ollama    | Ollama is a tool that lets you run and manage large language models locally on your computer with simple commands.                      |
| flowise   | Flowise is an open‑source, low‑code visual platform that enables users to design, build, and deploy LLM-based applications and AI flows |

You should see these container up and running:

![Overview Container](/img/podman_overview_container.png)

---

## Pulling LLMs for local development

With the following command you can download a LLM and host it with Ollama:

**Docker:**<br>
`podman  exec -it ollama ollama pull mistral`<br><br>
**Podman**<br>
`podman  exec -it ollama ollama pull mistral`

In this tutorial i will use [Mistral](https://mistral.ai). You can use whatever [Ollama](https://ollama.com/search) supports.

### Check if everything is set up correctly

| URL                                              | Description                     |
| ------------------------------------------------ | ------------------------------- |
| [http://localhost:11434](http://localhost:11434) | Ollama should be up and running |
| [http://localhost:3000](http://localhost:3000)   | You should see the flowise UI   |

---

## Connect local LLM with Flowise

After creating a local flowise account you should be able to connect your local LLM with flowise.

Go to "Assistants" and click on "Custom Assistant"
![Step 1](/img/flowise_1.png)
<br><br>
Now you should see the configuration view, where you are able to connect your local LLM:
![Step 2](/img/flowise_2.png)<br><br>
| Menu | Description |
| ----------- | ----------- |
| Select Model | ChatOllama |
| Base URL | host.docker.internal |
| Model Name | Name of the LLM container (e.g. mistral)|

After a click on "Save Assistant" you can test the success of your configuration by using the "Preview" on the right. You should be able to interact with your local LLM.

---

## Creating an Agent flow using your local LLM

Now you can get started and build a number of agent flows that will make your life easier. I built a research flow that lets two agents discuss things iteratively to achieve the best possible result.
You can import the `research_agents.json` play around with it.
Just click on "Settings" -> "Import" to import the flow.

---

## Start the flow

Click on "Chat" to write down your prompt:
![Chat](/img/flowise_3.png)

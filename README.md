

HOW TO INSTALL DATADOG

DD_API_KEY=c16de9f41ea2b3159394fb679fa8c6f0 bash -c "$(curl -L https://raw.githubusercontent.com/DataDog/dd-agent/master/packaging/datadog-agent/source/install_agent.sh)"

This will install the APT packages for the Datadog Agent and will prompt you for your password. If the Agent is not already installed on your machine and you don't want it to start automatically after the installation, just prepend DD_INSTALL_ONLY=true to the above script before running it.

1 Set up apt so that it can download through https: sudo apt-get update sudo apt-get install apt-transport-https

2 Set up the Datadog deb repo on your system and import Datadog's apt key: sudo sh -c "echo 'deb https://apt.datadoghq.com/ stable main' > /etc/apt/sources.list.d/datadog.list" sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys C7A7DA52

3 Update your local apt repo and install the Agent: sudo apt-get update sudo apt-get install datadog-agent

4 Copy the example config into place and plug in your API key (c16de9f41ea2b3159394fb679fa8c6f0): sudo sh -c "sed 's/api_key:.*/api_key: c16de9f41ea2b3159394fb679fa8c6f0/' /etc/dd-agent/datadog.conf.example > /etc/dd-agent/datadog.conf" 5 Start the Agent: sudo /etc/init.d/datadog-agent start

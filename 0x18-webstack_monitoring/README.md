#!/usr/bin/env bash


# Function to install the Datadog agent
install_datadog_agent() {
    # Install the Datadog agent
    DD_AGENT_MAJOR_VERSION=7 DD_API_KEY=$API_KEY DD_INSTALL_ONLY=true bash -c "$(curl -L https://raw.githubusercontent.com/DataDog/datadog-agent/master/cmd/agent/install_script.sh)"

    # Start the Datadog agent
    sudo systemctl start datadog-agent

    # Enable the Datadog agent to start on boot
    sudo systemctl enable datadog-agent
}

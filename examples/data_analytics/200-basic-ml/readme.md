
```bash
# Set the following variable environment
export example="200-basic-ml"

# Hub networking
rover -lz /tf/caf/landingzones/caf_networking/ -var-file /tf/caf/landingzones/caf_networking/scenario/200-single-region-hub/configuration.tfvars -tfstate networking_hub.tfstate -a apply

# Dap spoke network
rover -lz /tf/caf/landingzones/caf_networking/ -var-file /tf/caf/examples/data_analytics/${example}/networking_spoke.tfvars -tfstate ${example}-networking_spoke.tfstate -a apply

# Data Analytics Platform
rover -lz /tf/caf/examples -var-file /tf/caf/examples/data_analytics/${example}/configuration.tfvars -tfstate ${example}.tfstate -a apply

```
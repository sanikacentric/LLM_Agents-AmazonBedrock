User Request → Agent Core → Planning → Tools Core → Memory +Guardrails → Final Response.

Bedrock-flavored version of the same simple agent, with:

Tools Core → “Action Groups”

call() simulates Lambda invocation

Alias / InvokeAgent / ODT / PT as config objects

Guardrails included (safety + plan validation + output sanitization)

How this maps to Bedrock terminology (simple)

Tools Core → ActionGroupsCore (each tool is an ActionGroup)

Lambda invocation → ActionGroupsCore.call() triggers lambda_handler(event)

Alias → BedrockAgentAlias("v1-prod") (deployed snapshot)

InvokeAgent → BedrockInvokeAgent.invoke() (application entry point)

ODT/PT → ThroughputConfig(mode="ODT" or "PT")

Guardrails → blocks unsafe requests + validates tool usage + sanitizes output


[ ]
from dataclasses import dataclass, field
from typing import Dict, Any, List, Callable, Optional


# -------------------------
# Bedrock Deployment Config
# -------------------------
@dataclass
class ThroughputConfig:
    """

Colab paid products - Cancel contracts here


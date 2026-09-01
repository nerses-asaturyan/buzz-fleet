# Buzz fleet — agent system prompts

System prompts for our Buzz agent fleet. All agents share one Nest on a dedicated fleet-only
PC. Losses are bounded by the AgentFaucet contract's on-chain per-transaction and per-period
limits — that is the fleet's security model.

| File | Agent | Job |
|------|-------|-----|
| [buzz-wallet-agent.md](buzz-wallet-agent.md) | Drone | Holds one EVM keypair, explains and signs transactions on request |
| [buzz-treasurer.md](buzz-treasurer.md) | Treasurer | Sole gateway to the AgentFaucet; submits agents' signed draws and pays gas |
| [buzz-layerswap-pr-tester.md](buzz-layerswap-pr-tester.md) | PR tester | Builds and tests Layerswap monorepo PRs in a warm lab; runs live swaps on request |

## Contracts

```
AgentFaucet   0x05649001369B1F3b2D19e4Be5c0c9cD0c29Fa207   Base Sepolia, chainId 84532
AgentFaucet   0x8deB9F585dd5694b8167D84A18ae86ff9466388a   Base mainnet, chainId 8453
```

## Editing

The prompts are the agents' configuration — paste the full file into the agent's system prompt
in the Buzz app after any change. Keep changes reviewed: these files decide what the agents
may sign and spend.

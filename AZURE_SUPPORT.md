# Azure OpenAI Support for Memory Plugin

This branch (`feat/azure-openai-support`) implements native Azure OpenAI support for the memory-lancedb-pro plugin.

## Changes
- Modified `src/embedder.ts` to detect Azure endpoints.
- Injected `api-key` header and `api-version` query param when Azure is detected.

## Why?
- Allows users to use Azure OpenAI embeddings directly without an intermediate proxy.
- Hardcodes `api-version` to `2024-02-01` for now (stable release).

## Usage
Configure `memory.embedding.baseURL` to your Azure endpoint (e.g., `https://your-resource.openai.azure.com/openai/deployments/your-deployment/embeddings`).
The code automatically detects `.openai.azure.com` and applies the necessary headers.

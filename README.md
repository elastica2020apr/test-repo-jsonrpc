# MCP Traffic Playground

This repository is a sandbox used to exercise file upload and download
operations through the GitHub MCP server, so the resulting API traffic can
be captured and inspected with Fiddler Classic.

## Purpose

- Trigger `create_or_update_file`, `push_files`, and `get_file_contents`
  tool calls from GitHub Copilot Chat.
- Observe how file content is base64-encoded in request and response
  bodies sent to `api.githubcopilot.com`.
- Compare single-file updates against batch commits to see how many
  round trips each operation generates.

## Usage

1. Open this repo in VS Code with the `github` MCP server configured.
2. Ask Copilot Chat to create, update, or read files in this repo.
3. Watch the captured traffic in Fiddler for the JSON-RPC payloads.

## Notes

This file is padded to roughly one kilobyte so it is easy to spot in a
traffic capture and compare against the encoded payload size. It is
not meant to be functional code — it exists to generate a
predictable, inspectable network request.

# statistics-mcp-server

A standalone C++20 Model Context Protocol (MCP) server for descriptive statistics, arithmetic, and means.

## Tools

The server provides 27 statistical and arithmetic tools, including descriptive statistics, arithmetic operations, arithmetic/geometric/harmonic/generalized means, weighted means, variance, and standard deviation.

## Dependency

The shared MCP implementation is provided by [mcpxx](https://github.com/pooriayousefi/mcpxx), pinned as a Git submodule at commit `0ec0e6ac04acc46fb7c6160f1a16a2ead19ee4a0` under `external/mcpxx`.

## Clone and build

```sh
git clone --recurse-submodules https://github.com/pooriayousefi/statistics-mcp-server.git
cd statistics-mcp-server
make
```

Or compile directly:

```sh
clang++ -std=c++20 -O2 -pthread -I external/mcpxx/include src/statistics_mcp_tool_server.cpp -o bin/statistics_mcp_tool_server
```

On Windows with MinGW, add `-lws2_32`.

## Run

Stdio (default): `./bin/statistics_mcp_tool_server`

Streamable HTTP: `./bin/statistics_mcp_tool_server http 127.0.0.1 8096`

The HTTP endpoint is `/mcp`. Bind to loopback unless suitable network controls are configured.

## License

Apache-2.0. See [LICENSE](LICENSE).

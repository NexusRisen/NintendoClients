
# Module: <code>nintendo.nex.debug</code>

Provides a client and server for the `DebugProtocol`. This page was generated automatically from `debug.proto`.

<code>**class** [DebugClient](#debugclient)</code><br>
<span class="docs">The client for the `DebugProtocol`.</span>

<code>**class** [DebugServer](#debugserver)</code><br>
<span class="docs">The server for the `DebugProtocol`.</span>

<code>**class** [ApiCall](#apicall)([Structure](common.md))</code><br>
<code>**class** [ApiCallSummary](#apicallsummary)([Structure](common.md))</code><br>

## DebugClient
<code>**def _\_init__**(client: [RMCClient](rmc.md#rmcclient) / [HppClient](hpp.md#hppclient))</code><br>
<span class="docs">Creates a new [`DebugClient`](#debugclient).</span>

<code>**async def enable_api_recorder**() -> None</code><br>
<span class="docs">Calls method `1` on the server.</span>

<code>**async def disable_api_recorder**() -> None</code><br>
<span class="docs">Calls method `2` on the server.</span>

<code>**async def is_api_recorder_enabled**() -> bool</code><br>
<span class="docs">Calls method `3` on the server.</span>

<code>**async def get_api_calls**(pids: list[int], start: [DateTime](common.md#datetime), end: [DateTime](common.md#datetime)) -> list[[ApiCall](#apicall)]</code><br>
<span class="docs">Calls method `4` on the server.</span>

<code>**async def get_api_call_summary**(pid: int, start: [DateTime](common.md#datetime), end: [DateTime](common.md#datetime), only_limit_exceeded: bool) -> list[[ApiCallSummary](#apicallsummary)]</code><br>
<span class="docs">Calls method `7` on the server.</span>

## DebugServer
<code>**def _\_init__**()</code><br>
<span class="docs">Creates a new [`DebugServer`](#debugserver).</span>

<code>**async def logout**(client: [RMCClient](rmc.md#rmcclient)) -> None</code><br>
<span class="docs">Called whenever a client is disconnected. May be overridden by a subclass.</span>

<code>**async def enable_api_recorder**(client: [RMCClient](rmc.md#rmcclient)) -> None</code><br>
<span class="docs">Handler for method `1`. This method should be overridden by a subclass.</span>

<code>**async def disable_api_recorder**(client: [RMCClient](rmc.md#rmcclient)) -> None</code><br>
<span class="docs">Handler for method `2`. This method should be overridden by a subclass.</span>

<code>**async def is_api_recorder_enabled**(client: [RMCClient](rmc.md#rmcclient)) -> bool</code><br>
<span class="docs">Handler for method `3`. This method should be overridden by a subclass.</span>

<code>**async def get_api_calls**(client: [RMCClient](rmc.md#rmcclient), pids: list[int], start: [DateTime](common.md#datetime), end: [DateTime](common.md#datetime)) -> list[[ApiCall](#apicall)]</code><br>
<span class="docs">Handler for method `4`. This method should be overridden by a subclass.</span>

<code>**async def get_api_call_summary**(client: [RMCClient](rmc.md#rmcclient), pid: int, start: [DateTime](common.md#datetime), end: [DateTime](common.md#datetime), only_limit_exceeded: bool) -> list[[ApiCallSummary](#apicallsummary)]</code><br>
<span class="docs">Handler for method `7`. This method should be overridden by a subclass.</span>

## ApiCall
<code>**def _\_init__**()</code><br>
<span class="docs">Creates a new `ApiCall` instance. Required fields must be filled in manually.</span>

The following fields are defined in this class:<br>
<span class="docs">
<code>name: str</code><br>
<code>time: [DateTime](common.md#datetime)</code><br>
<code>pid: int</code><br>
</span><br>

## ApiCallSummary
<code>**def _\_init__**()</code><br>
<span class="docs">Creates a new `ApiCallSummary` instance. Required fields must be filled in manually.</span>

The following fields are defined in this class:<br>
<span class="docs">
<code>name: str</code><br>
<code>limit_exceeded: int</code><br>
<code>duration: int</code><br>
<code>limit: int</code><br>
<code>start: [DateTime](common.md#datetime)</code><br>
<code>limit_exceeded_count: int</code><br>
<code>total_count: int</code><br>
</span><br>


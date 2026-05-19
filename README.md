# COMSOL-Codex-MCP
# Fordring COMSOL Codex MCP  

这是一个COMSOL GUI MCP 包。它通过 Windows GUI 自动化把 COMSOL Java API 代码粘贴到当前打开模型的 Java Shell，并用 Ctrl+Enter 执行。

## 需要的环境

- Windows
- COMSOL Desktop 6.3 或更新版本
- Python 3.10 或更新版本
- 已经手动打开 COMSOL Desktop、目标模型和 Java Shell

## 直接运行

在本目录运行：

```powershell
.\start_server.ps1
```

如果 PowerShell 执行策略拦截，也可以运行：

```bat
start_server.bat
```

第一次运行会自动创建 `.venv` 并安装依赖；之后会直接复用本目录环境。

## Codex MCP 配置示例

把路径换成对方解压后的实际路径：

```toml
[mcp_servers.comsol_gui]
command = "powershell.exe"
args = ["-NoProfile", "-ExecutionPolicy", "Bypass", "-File", "C:\\path\\to\\Fordring-comsol-codex-MCP\\start_server.ps1"]
```

## 工具

- `gui_status`
- `ensure_java_shell`
- `execute_java_shell`
- `set_global_parameter`
- `get_java_shell_output`
- `capture_comsol_window`
- `capture_graphics_panel`
- `list_comsol_reference_tables`
- `search_comsol_physics_ids`
- `search_comsol_physics_feature_ids`
- `search_comsol_boundary_feature_ids`

## 注意

这个 MCP 不会自动保存 COMSOL 模型。修改模型后请在 COMSOL Desktop 里手动保存。

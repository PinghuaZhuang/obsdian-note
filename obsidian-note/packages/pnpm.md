## 使用 workspace
1. 添加文件 `pnpm-workspace.yaml`
2. 添加 `workspace` 依赖.
	1. packages/\*: `pnpm add @pn/xx -r`
	2. 根目录下: `pnpm add @pn/xx -w`
### pnpm-workspace.yaml
```yaml
packages:
  - 'packages/*'
```
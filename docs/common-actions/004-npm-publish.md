# npm publish

```yaml
- uses: actions/setup-node@v1
  with:
    node-version: 12
    registry-url: https://registry.npmjs.org/
- run: npm install
- run: npm run build
- run: npm publish --access public
  env:
    NODE_AUTH_TOKEN: ${{secrets.NPM_AUTH_TOKEN}}
```

## usage
1. NPM_AUTH_TOKEN 这个需要配置到项目的 secrets 里去
2. 针对存在 scope 的情况就需要加这个参数 `--access public`

## X 自定义拦截规则说明

你现在可以在以下 4 个文件里维护自己的规则：

- `share/keywords/X自定义.txt`：新增拦截关键词/表达式
- `share/keywords_delete/X自定义.txt`：从关键词库中排除（误伤回退）
- `share/blacklist/X自定义.txt`：按用户 ID 精准拦截（一行一个 ID）
- `share/whitelist/X自定义.txt`：白名单放行（一行一个 ID）

### 推荐维护顺序

1. 先在 `keywords` 增加规则
2. 发现误伤后，把对应规则或关键字放到 `keywords_delete`
3. 遇到反复出现的账号，加入 `blacklist`
4. 误封账号加入 `whitelist`

### 规则示例（keywords）

```txt
(foc<20&cd<6m)&(txt*=兼职|txt*=返利|txt*=带赚)
(txt*=私信我|txt*=加我)&(@*=tg|@*=telegram|@*=电报)
url=/t\.me\/|url=/discord\.gg\/
```

### 使用建议

- 每次先少量新增 3~10 条规则，观察误伤率
- 优先写“组合条件”，避免只用单一敏感词
- `blacklist` / `whitelist` 只放纯数字 ID，不要带 `@` 或备注

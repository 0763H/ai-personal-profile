## 版本与回退

每次修改都是一次提交，历史只增不改，所以任何一版都能查、能回退。

```bash
git log --oneline -- README.md    # 只看 README 的改动历史
git show <sha>                    # 看某次改了什么

git revert <sha>                  # 推荐：生成一次反向提交，历史完整保留
git checkout <sha> -- README.md   # 只把 README 恢复到某版本（不提交历史）
git tag -a v0.1.1 -m "补充第 3 节" && git push --tags   # 给当前状态打标签
```

> 规则：**不要用 `git push --force` 覆盖历史**；要撤销就走 `revert`。

---

## 本地同步

```bash
# 首次
git clone https://github.com/0763H/ai-personal-profile.git
cd ai-personal-profile

# 之后每次
git pull --rebase
# 编辑 README.md
git add README.md
git commit -m "docs(profile): 补充第 3 节沟通偏好"
git push
```

---

<sub>本仓库为公开仓库，请勿写入密钥、客户名称、未公开的内部数据。</sub>

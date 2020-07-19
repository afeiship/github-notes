# git commit

```yaml
- uses: github-actions-x/commit@v2.6
  with:
    github-token: ${{ secrets.GITHUB_TOKEN }}
    push-branch: master
    force-add: 'true'
    commit-message: 'auto: add url spider to db_urls tables.'
    rebase: 'true' # pull abd rebase before commit
    name: aric-docify
    email: 1290657123@qq.com
```

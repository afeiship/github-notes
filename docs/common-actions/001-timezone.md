# timezone

## solution1
```yaml
- name: Setup timezone
  uses: zcong1993/setup-timezone@master
  with:
    timezone: Asia/Shanghai
```

## solution2
> 这个方案测试下来，要20s差不多，所以，一般情况下，并不推荐使用。
```yaml
- run: echo "::set-env name=TIMEZONE::$(curl https://ipapi.co/timezone)"
- run: echo "Timezone is ${{ env.TIMEZONE }}."
```



## resources
- https://github.com/zcong1993/setup-timezone
- https://github.com/marketplace/actions/setup-timezone
- https://github.com/actions/starter-workflows/issues/80

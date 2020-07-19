# timezone

## solution1
```yaml
- name: Setup timezone
  uses: zcong1993/setup-timezone@master
  with:
    timezone: Asia/Shanghai
```

## solution2
```yaml
- run: echo "::set-env name=TIMEZONE::$(curl https://ipapi.co/timezone)"
- run: echo "Timezone is ${{ env.TIMEZONE }}."
```



## resources
- https://github.com/zcong1993/setup-timezone
- https://github.com/marketplace/actions/setup-timezone
- https://github.com/actions/starter-workflows/issues/80

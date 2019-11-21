# workflow

## 定义
- GitHub Actions 的配置文件叫做 workflow 文件
- 存放在代码仓库的.github/workflows目录


## 基本规则
- workflow 文件采用 YAML 格式，文件名可以任意取
- 但是后缀名统一为.yml，比如foo.yml
- 一个库可以有多个 workflow 文件
- GitHub 只要发现.github/workflows目录里面有.yml文件，就会自动运行该文件

## 基本字段
- name: 字段是 workflow 的名称。如果省略该字段，默认为当前 workflow 的文件名
- on: 触发 workflow 的条件，通常是某些事件
  - on: 也可以是数组[push, pull_request]
  - on.<push|pull_request>.<tags|branches>
- jobs.<job_id>.name
  - jobs.<job_id>.needs
  - jobs.<job_id>.runs-on

### on 指定触发事件时，可以限定分支或标签
```yml
# 上面代码指定，只有master分支发生push事件时，才会触发 workflow。
on:
  push:
    branches:    
      - master
```

### jobs
```yml
jobs:
  my_first_job:
    name: My first job
  my_second_job:
    name: My second job
```

### jobs.needs
> 字段指定当前任务的依赖关系，即运行顺序

```yml
jobs:
  job1:
  job2:
    needs: job1
  job3:
    needs: [job1, job2]
```

### runs-on:
> runs-on字段指定运行所需要的虚拟机环境。它是必填字段。目前可用的虚拟机如下
```conf
ubuntu-latest，ubuntu-18.04或ubuntu-16.04
windows-latest，windows-2019或windows-2016
macOS-latest或macOS-10.14
```

### jobs.<job_id>.steps

```conf
jobs.<job_id>.steps.name：步骤名称。
jobs.<job_id>.steps.run：该步骤运行的命令或者 action。
jobs.<job_id>.steps.env：该步骤所需的环境变量
```


```yml
name: Greeting from Mona
on: push

jobs:
  my-job:
    name: My Job
    runs-on: ubuntu-latest
    steps:
    - name: Print a greeting
      env:
        MY_VAR: Hi there! My name is
        FIRST_NAME: Mona
        MIDDLE_NAME: The
        LAST_NAME: Octocat
      run: |
        echo $MY_VAR $FIRST_NAME $MIDDLE_NAME $LAST_NAME.
```
